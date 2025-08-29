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

#javascript #modules #esm #webpack #comparison #build-tools
# **Comparison**

| Feature         | ESM (Native)                            | Webpack (Bundler)                 |
| --------------- | --------------------------------------- | --------------------------------- |
| Standard        | Yes, part of JS spec                    | No, external tool                 |
| Usage           | Directly in browsers/Node               | Needs build step                  |
| Module Syntax   | `import` / `export`                     | Supports ESM, CommonJS, etc.      |
| Tree-Shaking    | Yes (native, limited)                   | Yes (more powerful)               |
| Code Splitting  | Limited                                 | Full support                      |
| Asset Handling  | No (JS only)                            | Yes (CSS, images, etc.)           |
| Config Required | Minimal (just `<script type="module">`) | Often complex (webpack.config.js) |

---


## **ESM (ECMAScript Modules)**

- **What it is**:
    - A **native JavaScript module system** built into modern browsers and Node.js.
- **Syntax**:
    
```js
// Import
import { readFile } from "fs";
import MyComponent from "./MyComponent.js";
    
// Export
export function greet() { ... }
export default class User { ... }
```
    
- **Key Features**:
    - Standardized (`import` / `export`).
    - Supported directly in browsers (with `<script type="module">`).
    - Tree-shaking possible (unused code is not loaded).
    - Static analysis → dependencies are known at compile time.
        
- **Limitations**:
    - No advanced features like code splitting, bundling, or asset handling.
    - For large projects, may require tooling for optimization.
        

---

## **Webpack**

- **What it is**:
    - A **module bundler** for JavaScript (and more).
- **How it works**:
    - Takes many files (JS, CSS, images, etc.).
    - Bundles them into fewer optimized files for browsers.
- **Key Features**:
    - Supports ESM **and** CommonJS.
    - Bundles and optimizes code (minification, tree-shaking).
    - Supports **loaders** (handle non-JS like CSS, images).
    - Supports **plugins** (e.g., environment variables, compression).
    - Code splitting & lazy loading for performance.
        
- **Limitations**:
    - Requires setup/configuration.
    - Adds build step (not native).

---
### **When to Use**

- **ESM**:
    - Small to medium projects.
    - Modern browsers only.
    - Simpler setup (no bundling needed).
- **Webpack**:
    - Large/complex apps.
    - Need to support older browsers.
    - Want advanced features (code splitting, CSS/image bundling, plugins).

---

👉 In short:

- **ESM is the standard** → use it when you can.
    
- **Webpack is a power tool** → use it when you need optimization, legacy support, or advanced features.
    

---

Do you want me to also show you a **real example project** using ESM only vs one using Webpack, so you can see the difference in practice?