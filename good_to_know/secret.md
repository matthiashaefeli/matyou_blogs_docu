# Secret Key base

Change
```
Rails.application.secrets.secret_key_base
```
to
```
Rails.application.credentials.dig(:secret_key_base)
```
