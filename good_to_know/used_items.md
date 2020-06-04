# Table most used Items should not show FRT_FREE items

In Microsoft SQL Server Management Studio

bti db => Programmability => Stored Procedures => dbo.generate_top_items_for_customer

Right click => Modify, change to code below:
```
SE [bti_test]
GO
/****** Object:  StoredProcedure [dbo].[generate_top_items_for_customer]    Script Date: 01/03/2019 14:39:35 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
-- =============================================
-- Author:		<Author,,Name>
-- Create date: <Create Date,,>
-- Description:	<Description,,>
-- =============================================
ALTER PROCEDURE [dbo].[generate_top_items_for_customer] @custid char(10)
AS
BEGIN
	-- SET NOCOUNT ON added to prevent extra result sets from
	-- interfering with SELECT statements.
	SET NOCOUNT ON;

    DELETE customer_top_items
	WHERE customer_id = @custid

	DECLARE @rn int, @ly_id char(20), @ly_name char(90), @ly_qty int, @ty_id char(20), @ty_name char(90), @ty_qty int

	DECLARE tiCursor CURSOR
	FOR
	SELECT rn.rn, 
	ly.id AS ly_item_id,
	ly.name AS ly_item_name, 
	ly.qty AS ly_qty, 
	ytd.id AS ty_item_id,
	ytd.name AS ty_item_name, 
	ytd.qty AS ty_qty
	FROM (
		SELECT 1 AS rn
		UNION 
		SELECT 2
		UNION 
		SELECT 3
		UNION 
		SELECT 4
		UNION 
		SELECT 5
	) AS rn
	LEFT JOIN (
		SELECT TOP 5 ROW_NUMBER() OVER(order by SUM(allitrsallcol.nshipqty) desc) AS rn, 
		inventory.id,
		RTRIM(inventory.manufacturer_name) + ' ' + inventory.name AS name,
		CAST(SUM(allitrsallcol.nshipqty) AS int) AS qty
		FROM allinvcallcol
		INNER JOIN allitrsallcol ON allitrsallcol.cinvno = allinvcallcol.cinvno
		INNER JOIN inventory ON inventory.id = allitrsallcol.citemno
		WHERE allinvcallcol.dinvoice BETWEEN '1/1/' + CAST(DATEPART(yy, GETDATE()) AS char(4)) AND GETDATE()
		AND allinvcallcol.lvoid = 0
		AND allinvcallcol.nsalesamt > 0
		AND allinvcallcol.ccustno = @custid
		AND inventory.id NOT IN ('AARUP', 'COD', 'FRARS', 'SC1', 'FRT_FREE')
		GROUP BY inventory.id, RTRIM(inventory.manufacturer_name) + ' ' + inventory.name
	) AS ytd ON ytd.rn = rn.rn
	LEFT JOIN (
		SELECT TOP 5 ROW_NUMBER() OVER(order by SUM(allitrsallcol.nshipqty) desc) AS rn, 
		inventory.id,
		RTRIM(inventory.manufacturer_name) + ' ' + inventory.name AS name, 
		CAST(SUM(allitrsallcol.nshipqty) AS int) AS qty
		FROM allinvcallcol
		INNER JOIN allitrsallcol ON allitrsallcol.cinvno = allinvcallcol.cinvno
		INNER JOIN inventory ON inventory.id = allitrsallcol.citemno
		WHERE allinvcallcol.dinvoice BETWEEN '1/1/' + CAST(DATEPART(yy, GETDATE()) - 1 AS char(4)) AND '1/1/' + CAST(DATEPART(yy, GETDATE()) AS char(4))
		AND allinvcallcol.lvoid = 0
		AND allinvcallcol.nsalesamt > 0
		AND allinvcallcol.ccustno = @custid
		AND inventory.id NOT IN ('AARUP', 'COD', 'FRARS', 'SC1', 'FRT_FREE')
		GROUP BY inventory.id, RTRIM(inventory.manufacturer_name) + ' ' + inventory.name
	) AS ly ON ly.rn = rn.rn
	ORDER BY rn.rn

	OPEN tiCursor
	FETCH NEXT FROM tiCursor INTO @rn, @ly_id, @ly_name, @ly_qty, @ty_id, @ty_name, @ty_qty
	WHILE @@FETCH_STATUS = 0
	BEGIN
		INSERT INTO customer_top_items (customer_id, rank, ly_item_id, ly_item_name, ly_qty, ty_item_id, ty_item_name, ty_qty)
		VALUES (@custid, @rn, @ly_id, @ly_name, @ly_qty, @ty_id, @ty_name, @ty_qty)

		FETCH NEXT FROM tiCursor INTO @rn, @ly_id, @ly_name, @ly_qty, @ty_id, @ty_name, @ty_qty
	END

	CLOSE tiCursor
	DEALLOCATE tiCursor

END
```

Save it with Execute.Close Query Window.
