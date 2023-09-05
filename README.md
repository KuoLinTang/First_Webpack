# First_Webpack

## Webpack
Helps manage dependency graphs when importing multiple modules which are related to each other.

## Installation and Basic Usage
### Create or modify the package.json file
Package.json is used to save installed node.js packages
* Create a package.json file using npm (node package manager)
-> ***npm init***

### Install webpack using npm 
* --save will save this module into the package.json file
-> ***npm install webpack webpack-cli --save***
* It also create a folder named **node_modules**

### Create a Webpack configuration file (webpack.config.js)
* entry: the entry of the app
-> Should be the js file that relates to all other modules
* output: define output path and name 

### Configure package.json file
* Add a new line so that we can directly compile the code using Webpack and build a bundle
-> Add ***"build": "webpack"*** inside the script object

### Build the bundle with Webpack
-> ***npm run build***

### Use the built bundle
-> Import the **bundle.js** file into HTML using a script tag and its src attribute

## Bundle CSS files
* Webpack originally can only bundle JS files
    * But we can use loaders to bundle other types of files
    * For example, we use CSS-loader to integrate CSS files
    * Install CSS-loader: ***npm install --save css-loader style-loader*** (style-loader is also needed)

* We can include our installed loaders in the ***module -> rules*** in our Webpack configuration file

* In order to include the CSS file in the app, we need to import it in the main.js (entry)
-> Example: ***import './style.css'***

* Finally, we can build the bundle
-> ***npm run build***


## Using Webpack DevServer for Development
* Install Webpack-dev-server
-> ***npm install webpack-dev-server --save***
* We also have to add DevServer configuration in webpack.config.js
* Then, we must modify package.json so that we can use npm command to start our server
-> Add ***"start": "webpack-dev-server --open"*** in the script object <br/>
-> Use ***npm run start*** or ***npm start*** to start the development web server
* Webpack DevServer will seamlessly monitor any change in our app
-> It doesn't need to be compiled into a bundle file <br/>
-> In fact, when running the Dev Server, we do not need to compile the bundle.js file before