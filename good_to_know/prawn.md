# Prawn: Check values on table

Sometimes you have to do some special things with a specific cell.

```
class PdfInvoice < Prawn::Document
  def initialize
    super()
    ....
    table_content
    ...
  end

  def table_content
    data = [ ["Item", "Jan Sales", "Feb Sales"],
             ["Oven", 17, 89],
             ["Fridge", 62, 30],
             ["Microwave", 71, 47]
           ]

    table(data) do
      values = cells.columns(1..-1).rows(1..-1)

      bad_sales = values.filter do |cell|
        cell.content.to_i < 40
      end

      bad_sales.background_color = "FFAAAA"

      good_sales = values.filter do |cell|
        cell.content.to_i > 70
      end

      good_sales.background_color = "AAFFAA"
    end
  end
end
```

This would show the cells with a value < 40 with a red background, and the cells with a value > 70 with a green background.



