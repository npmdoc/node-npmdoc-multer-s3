# api documentation for  [multer-s3 (v2.5.0)](https://github.com/badunk/multer-s3#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-multer-s3.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-multer-s3) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-multer-s3.svg)](https://travis-ci.org/npmdoc/node-npmdoc-multer-s3)
#### Streaming multer storage engine for AWS S3

[![NPM](https://nodei.co/npm/multer-s3.png?downloads=true)](https://www.npmjs.com/package/multer-s3)

[![apidoc](https://npmdoc.github.io/node-npmdoc-multer-s3/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-multer-s3_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-multer-s3/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-multer-s3/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-multer-s3/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "badunk"
    },
    "bugs": {
        "url": "https://github.com/badunk/multer-s3/issues"
    },
    "dependencies": {
        "file-type": "^3.3.0",
        "run-parallel": "^1.1.6"
    },
    "description": "Streaming multer storage engine for AWS S3",
    "devDependencies": {
        "aws-sdk": "^2.2.32",
        "concat-stream": "^1.5.1",
        "express": "^4.13.1",
        "form-data": "^1.0.0-rc3",
        "mocha": "^2.2.5",
        "multer": "^1.1.0",
        "on-finished": "^2.3.0",
        "standard": "^5.4.1",
        "xtend": "^4.0.1"
    },
    "directories": {},
    "dist": {
        "shasum": "3541c46ed44a0e777bef3d2042cf115afcc1dfcf",
        "tarball": "https://registry.npmjs.org/multer-s3/-/multer-s3-2.5.0.tgz"
    },
    "gitHead": "40508a3a7a930e91715686ba1777552be1ef12c9",
    "homepage": "https://github.com/badunk/multer-s3#readme",
    "keywords": [
        "multer",
        "s3",
        "amazon",
        "aws"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "badunk",
            "email": "baduncaduncan@gmail.com"
        }
    ],
    "name": "multer-s3",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/badunk/multer-s3.git"
    },
    "scripts": {
        "test": "standard && mocha test/basic.js"
    },
    "version": "2.5.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module multer-s3](#apidoc.module.multer-s3)
1.  [function <span class="apidocSignatureSpan">multer-s3.</span>AUTO_CONTENT_TYPE (req, file, cb)](#apidoc.element.multer-s3.AUTO_CONTENT_TYPE)
1.  [function <span class="apidocSignatureSpan">multer-s3.</span>DEFAULT_CONTENT_TYPE (req, file, cb)](#apidoc.element.multer-s3.DEFAULT_CONTENT_TYPE)



# <a name="apidoc.module.multer-s3"></a>[module multer-s3](#apidoc.module.multer-s3)

#### <a name="apidoc.element.multer-s3.AUTO_CONTENT_TYPE"></a>[function <span class="apidocSignatureSpan">multer-s3.</span>AUTO_CONTENT_TYPE (req, file, cb)](#apidoc.element.multer-s3.AUTO_CONTENT_TYPE)
- description and source-code
```javascript
function autoContentType(req, file, cb) {
  file.stream.once('data', function (firstChunk) {
    var type = fileType(firstChunk)
    var mime = (type === null ? 'application/octet-stream' : type.mime)
    var outStream = new stream.PassThrough()

    outStream.write(firstChunk)
    file.stream.pipe(outStream)

    cb(null, mime, outStream)
  })
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.multer-s3.DEFAULT_CONTENT_TYPE"></a>[function <span class="apidocSignatureSpan">multer-s3.</span>DEFAULT_CONTENT_TYPE (req, file, cb)](#apidoc.element.multer-s3.DEFAULT_CONTENT_TYPE)
- description and source-code
```javascript
DEFAULT_CONTENT_TYPE = function (req, file, cb) {
  cb(null, value)
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
