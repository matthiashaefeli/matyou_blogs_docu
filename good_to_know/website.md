# Rails URL validation

```
validates :website, format: { with: URI::regexp(%w(http https)) }
```
