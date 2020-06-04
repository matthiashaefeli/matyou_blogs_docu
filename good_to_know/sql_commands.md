# Sql commands used in a stored procedure
```
SET ANSI_NULLS ON
```
When ANSI_NULLS is ON, a SELECT statement that uses WHERE column_name = NULL returns zero rows even if there are null values in column_name. A SELECT statement that uses WHERE column_name <> NULL returns zero rows even if there are nonnull values in column_name.

```
SET QUOTED_IDENTIFIER ON
```
When SET QUOTED_IDENTIFIER is ON, identifiers can be delimited by double quotation marks, and literals must be delimited by single quotation marks. When SET QUOTED_IDENTIFIER is OFF, identifiers cannot be quoted and must follow all Transact-SQL rules for identifiers

```
SET NOCOUNT ON;
```
When SET NOCOUNT is ON, the count is not returned. When SET NOCOUNT is OFF, the count is returned.
