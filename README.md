# VueFullStackWebPack
Project template for Vue full stack app using WebPack

`npm init`

`npm install --save vue vue-router`

`npm install --save-dev webpack webpack-cli`

Create webpack.config.dev.js. in build directory 

```
'use strict'

const { VueLoaderPlugin } = require('vue-loader')
module.exports = {
  mode: 'development',
  entry: [
    './src/app.js'
  ],
  module: {
    rules: [
      {
        test: /\.vue$/,
        use: 'vue-loader'
      }
    ]
  },
  plugins: [
    new VueLoaderPlugin()
  ]
}
```
Add additional npm dependencies

```
npm install --save-dev vue-loader vue-template-compiler vue-style-loader css-loader
```

Add Npm build script to package.json

```
"build": "webpack --config build/webpack.config.dev.js"
```

Create index.html

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Vue app with web pack</title>
</head>
<body>
    <div id="app"></div>
    <script src="dist/main.js" type="text/javascript"></script>
</body>
</html>
```

```
npm run build
```
Install live server extension to VSCode and browse to the page