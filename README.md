# webpack-config
A reference for configuring webpack from scratch

## Environment Variables
### [Webpack docs](https://webpack.js.org/guides/environment-variables/)

Basically 
```js
webpack --env.NODE_ENV=local --env.production
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

## HTML file
Configure webpack to inject the path to our JS bundle directly into HTML

[HTML Webpack Plugin](https://github.com/jantimon/html-webpack-plugin)

Generates a dist/index.html with a script src pointing to ouptut JS

```js
plugins: [
  new HtmlWebpackPlugin({
    template:'./src/template.html'
  })
],
  ```

## Cache Busting
use a unique file version identifier to tell the browser that a new version of the file is available

## Clean build folder
[Clean Webpack Plugin](https://github.com/johnagan/clean-webpack-plugin)
```js
plugins: [
  new CleanWebpackPlugin()
]
