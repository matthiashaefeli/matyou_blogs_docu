# How to add an env file to create react app

create a new file in the root directory: env.development

```
REACT_APP_API_SPACE: here_comes_my_space_or_key
REACT_APP_API_TOKEN: here_comes_my_token
```

access this variables

```
space: process.env.REACT_APP_API_SPACE,
token: process.env.REACT_APP_API_TOKEN
```

important: add this file to gitignore and restart server
