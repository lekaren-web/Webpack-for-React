For future reference!

1. INSTALL WEBPACK:

npm install webpack webpack-cli webpack-dev-server --save-dev


2. MAKE webpack.config.js file:

touch webpack.config.js 

3. PASTE THIS IN BUT REPLACE WITH YOUR ENTRY POINT:
module.exports = {
  entry: ['./src/index.js'],
  output: {
    path: __dirname,
    filename: './public/bundle.js',
  },
  devtool: 'source-map',
  module: {
    rules: [
      {
        test: /\.jsx?$/,
        exclude: /node_modules/,
        loader: 'babel-loader',
        options: {
          presets: ['@babel/preset-react'],
        },
      },
      {
        test: /\.css$/i,
        use: ['style-loader', 'css-loader'],
      },
    ],
  },
};

4. WHEN YOU WANT THE APP TO RUN. RUN 'npm run build' before 'npm run dev'