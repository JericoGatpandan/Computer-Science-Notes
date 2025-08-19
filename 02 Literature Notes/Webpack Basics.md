#javascript #webpack #bundler #build-tools #dev-server

>**webpack** is a _static module bundler_ for modern JavaScript applications.


```bash
npx webpack serve
```

Our site will then be available via [http://localhost:8080/](http://localhost:8080/) by default.

Note that the webpack-dev-server only reads your webpack configuration when you start it. If you change the webpack config file while the dev server is running, it will not reflect those config changes. Use Ctrl + C in the terminal to kill it then rerun `npx webpack serve` to apply the new config.

```js
// webpack.config.js
const path = require("path");
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  mode: "development",
  entry: "./src/index.js",
  output: {
    filename: "main.js",
    path: path.resolve(__dirname, "dist"),
    clean: true,
  },
  devtool: "eval-source-map",
  devServer: {
    watchFiles: ["./src/template.html"],
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: "./src/template.html",
    }),
  ],
  module: {
    rules: [
      {
        test: /\.css$/i,
        use: ["style-loader", "css-loader"],
      },
      {
        test: /\.html$/i,
        loader: "html-loader",
      },
      {
        test: /\.(png|svg|jpg|jpeg|gif)$/i,
        type: "asset/resource",
      },
    ],
  },
};
```

[[webpack Concepts]]
[[09 Webpack  The Odin Project]]
