# RSpec create random id

```
FactoryBot.define do
  sequence(:random_id) { |n| @random_ids ||= (6...1000000).t_a.shuffle; @random_ids[n] }
  factory :user do
    id{ FactoryBot.generate(:random_id) }
    ...
    ...
  end
end
```
