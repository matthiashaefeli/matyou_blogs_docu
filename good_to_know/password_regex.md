## Password checker with regex

Check if a given string contains at least one lowercase letter, one upercase letter, one digit, and has min 8 chars
```
passoword.match?(/^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9]).{8,}$/)
```
