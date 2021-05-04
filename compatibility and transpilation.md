How to transpile one code to another.

1. place your ES6 JavaScript file in a directory called src.   
> From your root directory, the path to the ES6 file is ./src/main.js  

2. `npm init` Before we install Babel, we need to setup our project to use the node package manager (npm). Developers use npm to access and manage Node packages. Node packages are directories that contain JavaScript code written by other developers.  

* The npm init command creates a package.json file in the root directory.  
* A package.json file contains information about the current JavaScript project. Some of this information includes:  

  - Metadata — This includes a project title, description, authors, and more.  
  - A list of node packages required for the project — If another developer wants to run your project, npm looks inside package.json and downloads the packages in this list.  
  - Key-value pairs for command line scripts — You can use npm to run these shorthand scripts to perform some process. In a later exercise, we will add a script that runs Babel and transpiles ES6 to ES5.  

3. `npm install babel-cli -D`
4. `npm install babel-preset-env -D`
  * The babel-cli package includes command line Babel tools, and the babel-preset-env package has the code that maps any JavaScript feature, ES6 and above (ES6+), to ES5.  
  * The -D flag instructs npm to add each package to a property called devDependencies in package.json. Once the project’s dependencies are listed in devDependencies, other developers can run your project without installing each package separately. Instead, they can simply run npm install — it instructs npm to look inside package.json and download all of the packages listed in devDependencies.  
  
5. specify the version of the source JavaScript code.
> You can specify the initial JavaScript version inside of a file named .babelrc. In your root directory, you can run `touch .babelrc` to create this file.  
> To specify that we are transpiling code from an ES6+ source, we have to add the following JavaScript object into .babelrc:  
> ```
>{  
>  "presets": ["env"]  
> }
>```

6. specify a script in package.json that initiates the ES6+ to ES5 transpilation.  
* Inside of the package.json file, there is a property named "scripts" that holds an object for specifying command line shortcuts.
```
...
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1"
},...
```
* Below the "test" property, we will add a script that runs Babel like this:
```
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
  "build": "babel src -d lib"
}
```
*  The property’s value, "babel src -d lib", is a command line method that transpiles ES6+ code to ES5.  
7. `call "build"` from the command line to transpile and write ES5 code to a directory called lib.

Babel writes the ES5 code to a file named main.js (it’s always the same name as the original file), inside of a folder called lib. The resulting directory structure is:
```
project
|_ lib
|___ main.js
|_ node_modules
|___ .bin
|___ ...
|_ src
|___ main.js
|_ .babelrc
|_ package.json
```
