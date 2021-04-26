#  Google font with react

yarn add webfontloader

add code below to index.js
```
import WebFont from 'webfontloader';

WebFont.load({
  google: {
    families: ['Titillium Web:300,400,700', 'sans-serif']
  }
});
```

add code below to index.css
```
font-family: 'Titillium';
```
