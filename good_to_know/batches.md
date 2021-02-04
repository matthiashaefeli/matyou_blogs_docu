# ActieveRecord::Batches

Looping through a collection of records from the database is very inefficent since it will try to instantiate all the objects at once.

In that case, batch processing methods allow you to work with the records in batches, thereby greatly reducing memory consumption.

The find_each method uses find_in_batches with a batch size of 1000 (or as specified by the :batch_size option)

```
Order.find_each do |order|
  order.do_something
end

Order.where(status: 'completed').find_each do |order|
  order.do_something
end
```

define options:

```
Order.find_each(start: 2000, batch_size: 2000) do |order|
  order.do_something
end
```
