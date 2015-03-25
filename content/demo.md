
1. Create a folder to create our command in.
- Create `bin/index.js`

  ```
  #!/usr/bin/env node
  console.log("HI");
  ```

- Create package.json with `npm init`
- Add bin section

  ```
  "bin": {
    "sample-cli": "./bin/index.js"
  },
  ```

- set it executable so we can run it directly

    chmod +x ./bin/index.js

- `npm install -g`
  - to remove 'npm uninstall -g sample-cli'

- create `.npmignore`
- `npm install --save liftoff` [liftoff](https://www.npmjs.com/package/liftoff)
- `npm install msee` for generating markdown-based console help output
- Consider either `minimist` or `commander` for command line args parsing


```
#!/usr/bin/env node

var path = require('path');
var argv = require('minimist')(process.argv.slice(2));

var getVersion = function() {
  var packagePath = path.join(__dirname, '../package.json');
  var version = require(packagePath).version;
  return version;
}

var printHelpMessage = function() {
  var helpFile = path.join(__dirname, 'help.md');
  var output = require('msee').parseFile(helpFile);
  var version = getVersion();
  output = output.replace('{{version}}', version);

  // Some spacing formatting cleanup
  output = output.replace(/&nbsp;/g, ' ');
  console.log(output);
};

if (argv.help) {
  return printHelpMessage();
}

if (argv.version) {
  console.log(getVersion());
  return;
}

console.log(argv);

```
