
1. Create a folder to create our command in.
- Create `bin/index.js`

  ```
  #!/usr/bin/env node
  console.log("HI");
  ```

- Add some code to the file, ex: `console.log('sample-cli!')`
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
