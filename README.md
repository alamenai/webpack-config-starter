<h1 align="center">Webpack Starter</h1>
<h5 align="center">Learn step by step by doing how to use Webpack configuration in your projects</h5>

### First Setup

First your need to create a directory, clone the project and install the dependencies.
```
   → mkdir webpack-starter
   → git clone https://github.com/MenaiAla/webpack-config-starter
   → npm install
```
### Without webpack

Inside [`index.html`](index.html), there are implicit dependencies between the `<script>`.  [`index-no-module.js`](index-no-module.js)  depends on `lodash` being 
included before it runs. This is because  [`index-no-module.js`](index-no-module.js)  never explicitly declared a need for lodash; it just assumes that the global variable _ exists.
>This is traditional way for managing legacy JavaScript projects and web projects in general.

There are problems with managing JavaScript projects this way:

* It is not immediately apparent that the script depends on an external library.
* If a dependency is missing, or included in the wrong order, the application will not function properly.
* If a dependency is included but not used, the browser will be forced to download unnecessary code.

#### How you run it 


* Check and read [`index.html`](index.html).
* Open [`index.html`](index.html) in your browser.

### Without webpack.config.js
>Webpack +4 does not require webpack.config.js for basic configuration

* Check and read [`index.js`](index.js).
* Notice that I added `import _ from "lodash"` in the script.
* Check and read [`index.html`](dist/index.html) in `dist` folder.
* Notice that I removed `lodash` script from [`index.html`](index.html).

#### How you run it 
``` 
    npx webpack
```
>> ```npx webpack ``` takes the script [`index.js`](index.js) and generate a [`main.js`](dist/main.js) as the output in [`dist`](dist) folder.

### With webpack.config.js

Most of Javascript projects need complex webpack configuration.

* Check and read [`webpack.config.js`](webpack.config.js).
* run ```npx webpack --config webpack.config.js``` in your terminal.
>If a <i>webpack.config.js</i> is present, the webpack command picks it up by default. I used the <i>--config</i>option here only to show that you can pass a configuration of any name. This will be useful for more complex configurations that need to be split into multiple files.

#### With NPM scripts

It's bad practice to run long command ```npx webpack --config webpack.config.js``` each time. For that reason, we created a shortcut in [package.json](package.json) like this :

 ```"build": webpack```

 #### How you run it 

 ``` 
    npm run build
```