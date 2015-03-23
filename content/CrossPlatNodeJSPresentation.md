## Cross Platform Tools with NodeJS

Note:

1. Bump up fonts
- Check for internet
  - bring up https://www.npmjs.com/package/module-best-practices
- Prepare json for demo-ing json cli
- Use `s`

===
### Presented By
# Jason Jarrett
> * [staxmanade.com](http://staxmanade.com)
> * Twitter: [@staxmanade](https://twitter.com/staxmanade)
> * Github: [@staxmanade](http://github.com/staxmanade)
> * Day Job: [Vertigo](http://vertigo.com)

===

## Why is cross platform needed?

===

## What not use

- C
- Python
- Ruby
- C#
- Java
- etc...

===

## Awesome Node-Based CLI tools

- npm
- json
- gulp or grunt
- bower
- cordova, ionic
- istanbul
- mocha, vows
- ... too many to list ...
===

## Less awesome - but built by yours truly

- staxmanade/[skypeit](https://github.com/staxmanade/skypeit)
- staxmanade/[diffxcodetargets](https://github.com/staxmanade/diffxcodetargets)
- approvals/[approvals.nodejs](https://github.com/approvals/approvals.nodejs)
- togglejs/[toggle](https://github.com/togglejs/toggle)

===

## Over 134,447+ packages on NPM
## Which should I use?

> Pick the big name projects and inspect their package.js dependencies.

Note:

Every time I run across a package (especially a popular one), I like to review the package.json list of dependencies.

===

## npm module best practices

    npm install -g module-best-practices

Note:
- [https://www.npmjs.com/package/module-best-practices](https://www.npmjs.com/package/module-best-practices)
- [https://devcenter.heroku.com/articles/node-best-practices](https://devcenter.heroku.com/articles/node-best-practices)

===

Enough setup on Node & NPM.

Let's talk about cross-plat Node.

===

## \Paths/

`*nix paths !== Windows paths`

==

## Path manipulation

<img src="/images/thumbsDown.png" class='emoji' />

    var path = "foo" + "/" + "bar";

<hr>

<img src="/images/thumbsUp.png" class='emoji' />

    var path = path.join("foo", "bar");

==

# path module

    var path = require('path');

    path.normalize(...)
    path.resolve(...)  // like using "cd"
    path.join(...)


===

## Case-sensitive file names

<img src="/images/thumbsDown.png" class='emoji' />

    var path = require('Path');
<hr>

<img src="/images/thumbsUp.png" class='emoji' />

    var path = require('path');

Note:

Windows and OSX use case-insinsitive file systems, while linux is case-sensitive. Be careful with this the casings.

===

# Environment Vars

Not all environment variable exist or are consistently named across platforms.

EX:

    var home = process.env.USERPROFILE || process.env.HOME;

===


## Avoid static new lines characters

<img src="/images/thumbsDown.png" class='emoji' /> `\n` <img src="/images/thumbsDown.png" class='emoji' />

```
    console.log('first line\nSecond line!'); // NOOOO
```

==

## <img src="/images/thumbsUp.png" class='emoji' /> Newline Characters <img src="/images/thumbsUp.png" class='emoji' />

Use the `os` module's `EOL` property.

    var os = require('os');
    console.log('first line' + os.EOL + 'Second line!'); // YES!

===

## Temp files

    var os = require('os');
    var tmp = os.tmpdir();
    console.log(tmp);

===

## Determine platform?

    var os = require('os');
    console.log(os.platform());

OR

    console.log(process.platform);

Note:

If you need to get platform specific operations, you can use

'darwin', 'freebsd', 'linux', 'sunos' or 'win32'

===

## Avoid calling shebang from NPM scripts

    #!/usr/bin/env node
    console.log('sample-cli now installed!');

<img src="/images/thumbsDown.png" class='emoji' />

    {
      "name": "sample-cli",
      "version": "0.0.1",
      "scripts": {
        "postinstall": "./bin/npm-postinstall"
      }
    }

==

## Call with Node


    #!/usr/bin/env node
    console.log('sample-cli now installed!');

<img src="/images/thumbsUp.png" class='emoji' />

    {
      "name": "sample-cli",
      "version": "0.0.1",
      "scripts": {
        "postinstall": "node ./bin/npm-postinstall"
      }
    }

===

## Fancy Text Output or Colors

<img src="/images/thumbsUp.png" class='emoji' />
<img src="/images/thumbsDown.png" class='emoji' />
<img src="/images/thumbsUp.png" class='emoji' />

===

## Testing

Running unit tests on Travic-CI for mac & linux and AppVeyor for Windows

===

## Testing Tools

 - Mocha or Vows
 - Approvals (for testing CLI results?)

===

## Let's go build a CLI tool...

Note:

see... [/demo/README.md](/demo/README.md)

===

## References

- [node path docs](https://nodejs.org/api/path.html)
- [node os docs](https://nodejs.org/api/os.html)
- [Tips for Writing Portable Node.js Code](https://gist.github.com/domenic/2790533)
- [Writing cross-platform Node.js](http://shapeshed.com/writing-cross-platform-node/)
