## Setup

TODO:

1. Bump up fonts
2. Test internet
3. Prepare json

Note:
test
asdf

===

## Cross Platform Tools with NodeJS

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

## What about platforms?

- Python
- Ruby
- C#
- Java
- etc...

===

## But I'm not a NodeJS/Javascript developer?

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

## Less awesome - but shameless plug

- staxmanade/[skypeit](https://github.com/staxmanade/skypeit)
- staxmanade/[diffxcodetargets](https://github.com/staxmanade/diffxcodetargets)
- togglejs/[toggle](https://github.com/togglejs/toggle)
- approvals/[approvals.nodejs](https://github.com/approvals/approvals.nodejs)

===

## Cool-kid libraries?

> Pick the big name projects and inspect their package.js dependencies.

===

## npm module best practices

    npm install -g module-best-practices

- [https://www.npmjs.com/package/module-best-practices](https://www.npmjs.com/package/module-best-practices)
- [https://devcenter.heroku.com/articles/node-best-practices](https://devcenter.heroku.com/articles/node-best-practices)

===

## \Paths/

`*nix paths !== Windows paths`

https://gist.github.com/domenic/2790533

==

## Path manipulation

<img src="/images/thumbsDown.png" class='emoji' />

    var path = "foo" + "/" + "bar";

<hr>

<img src="/images/thumbsUp.png" class='emoji' />

    var path = path.join("foo", "bar");

==

# path module


    path.normalize(...)
    path.resolve(...)
    path.join(...)

Note: path.resolve

===

## Testing

Running unit tests on Travic-CI for mac & linux and AppVeyor for Windows

===

## Testing Tools

 - Mocha
 - Approvals
    - Show how they can be used to test CLI

## References

- [Tips for Writing Portable Node.js Code](https://gist.github.com/domenic/2790533)
- [Writing cross-platform Node.js](http://shapeshed.com/writing-cross-platform-node/)
