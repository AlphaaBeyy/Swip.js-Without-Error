
This is a project organized by Paul Sonnentag and Tim Großmann.

The Latest Version of the Shared Project is Incorrect and Since the Project is No longer Developed Errors Fixed and Published Here

The project is Open Source. You can develop and use it without any charge

Step By Step Setup

###### Setup
```bash
npm install webpack webpack-cli -g
npm install
npm install babel-loader@7 babel-core -D

Then modify your webpack.config.js so that it looks like this:

const path = require('path');

module.exports = {
  entry: {
    app: './src/client/index.js',
  },
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /(node_modules|bower_components)/,
        loader: 'babel-loader', // It seems that we need to use babel-loader 
      },
      {
        test: /\.css$/,
        loader: 'style-loader!css-loader',
      },
    ],
  },
};

cd examples/golf
npm install
cd ../particles
npm install
cd ../..
npm run build
```

###### Run the demos
```bash
npm run golf
npm run particles
```
