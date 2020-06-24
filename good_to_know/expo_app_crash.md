# Expo app crashes on touch event
If uou work with the expo app, and the app crashes everytime on a touch event.

Add code below to app.json, restart and that's it

```
"packagerOpts": { "sourceExts": [ "expo.ts", "expo.tsx", "expo.js", "expo.jsx", "ts", "tsx", "js", "jsx", "json", "wasm", "svg" ] }
```

