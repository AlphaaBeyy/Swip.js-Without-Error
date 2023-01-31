
Bu, Paul Sonnentag ve Tim Großmann tarafından düzenlenen bir projedir. Düzenleme ve Ek Hata Düzeltmeleri Tarafımca Yapılmıştır.

Paylaşılan Projenin Son Versiyonu Hatalı ve Proje Artık Geliştirilmediğinden Hatalar Düzeltilip Burada Yayınlanmaktadır

Proje Açık Kaynaklıdır. Herhangi bir ücret ödemeden geliştirebilir ve kullanabilirsiniz.

Adım Adım Kurulum

###### Setup
```bash
npm install webpack webpack-cli -g
npm install
npm install babel-loader@7 babel-core -D
```
Then modify your webpack.config.js so that it looks like this:
```bash
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
```
```bash
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
