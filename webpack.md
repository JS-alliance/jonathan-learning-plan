Webpack
=======
Webpack is used to automate your build process.

check out the [getting started guide here](https://webpack.github.io/docs/usage.html)

Initialize your node package file:

    npm init

Fill out your project information at the prompt.
Now install your dependancies.  The following is an example:

    npm install --save-dev babel-loader

Create a webpack config file:

    touch webpack.config.js

This file will include all of the config information about the website.

	{
	  entry: {
	    app: './src/app.js',
	    search: './src/search.js'
	  },
	  output: {
	    filename: '[name].js',
	    path: __dirname + '/build'
	  }
	}

The script will package all of your assets and output to the file designated `output` `filename` and `path`.

once your file is created, run `webpack` from command line.

Now that your files are packaged, go back to your `index.html` file and update your script tag. Replace `script.js` with `bundle.js`

    <script src="bundle.js"></script>

