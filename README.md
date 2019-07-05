# webpack-config
A reference for configuring webpack from scratch

## Environment Variables
### [Webpack docs](https://webpack.js.org/guides/environment-variables/)

Basically 
```js
webpack --env.NODE_ENV=local --env.production
...
// webpack.config.js
console.log('NODE_ENV: ', env.NODE_ENV); // 'local'
console.log('Production: ', env.production) true
```

Consider using [cross-env](https://github.com/kentcdodds/cross-env) if there is a need to support devs with multiple OSs

### [Canopy config](https://github.com/CanopyTax/canopy-webpack-config/blob/master/src/canopy-webpack-config.js)
Just check the arguments for webpack-dev-server

```js
const isDevServer = process.argv.some(arg => arg.includes('webpack-dev-server'))
module.exports={
  mode: env.dev || isDevServer ? 'development' : 'production',
}
```