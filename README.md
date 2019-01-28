1. Setup Project Folder

```shell
npm init -y
```

2. install development dependencies

```shell
npm install --save-dev bable-cli babel-preset-es2015 rimraf
```

[babel-cli](https://babeljs.io/docs/usage/cli/)Compile files from the command line using babel
[babel-preset-es2015](https://www.npmjs.com/package/babel-preset-es2015)Babel preset for all es2015 plugins
[rimraf](https://github.com/isaacs/rimraf)Run the unix command **rm -rf** in Node.js

3. Configuration File in the Your Project

```
touch .babelrc
```

```js
{
  "presets": ["es2015"]
}
```

4. Use Babel To Compile Javascript Files

```js
// package.json
{
  // ...
  "scripts" : {
    // ...
  "build": "rimraf dist/ && babel ./ --out-dir dist/ --ignore ./node_modules,./.babelrc,./package.json,./npm-debug.log --copy-files",
  "start": "npm run build && node dist/index.js"
  }
}
```
