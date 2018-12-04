### webpack_template
source: https://medium.com/jeremy-gottfrieds-tech-blog/tutorial-how-to-build-a-webpack-app-with-vanilla-js-or-react-72ca2cc7e14

# Geting Started

mkdir my-webpack-app && cd my-webpack-app && touch README.md && npm init && git init && touch .gitignore && mkdir public && mkdir src && touch src/index.css && touch src/index.js && touch webpack.config.js && touch index.html && touch server.js

my-webpack-app
├── README.md
├── node_modules
├── package.json
├── .gitignore
├── public
│   ├── favicon.ico
├── src
│   ├── index.css
│   ├── index.js
├── webpack.config.js
├── index.html
├── server.js

## Webpack

# Config

npm install -save webpack webpack-cli webpack-dev-server style-loader css-loader script-loader

// webpack.config.js
module.exports = {
  entry: [
    './src/index.js',
    './src/index.css'
  ],
  output: {
    path: __dirname,
    publicPath: '/',
    filename: 'bundle.js'
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: "script-loader"
        }
      },
      {
        test: /\.css$/,
        use: [
          {
            loader: "style-loader"
          },
          {
            loader: "css-loader",
            options: {
              modules: true,
              importLoaders: 1,
              localIdentName: "[name]_[local]_[hash:base64]",
              sourceMap: true,
              minimize: true
            }
          }
        ]
      }
    ]
  }
};

# Loaders
https://webpack.js.org/loaders/

