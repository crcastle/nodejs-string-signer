# string-signer [![Build Status](https://secure.travis-ci.org/crcastle/nodejs-string-signer.png?branch=master)](http://travis-ci.org/crcastle/nodejs-string-signer)
*A node.js cryptographic string signing library.*

---

## Install
Requires

* Node.js >= 0.6.x
* npm

###### Node Package Manager
```
$ npm install git://github.com/crcastle/nodejs-string-signer.git
```
###### Github
```
$ git clone https://github.com/crcastle/nodejs-string-signer.git
$ cd nodejs-string-signer
$ npm install
```
## Use
##### Create a signature
```
var stringSigner = require('string-signer');

var message = 'this is an official message. it must not be tampered with!';
var secret = 's3cr3t';

var signature = stringSigner.getSignature(stringToBeSigned, secret);
```
`signature` will be a string that is the hex representation of the hmac256 hash of `message`.  You can change this from hex to either binary or base64 within the lib/string-signer.js file.  At some point I'll make this a configuration parameter instead of hard-coding it in the file.
##### Verify a signature
```
var stringSigner = require('string-signer');

var message = 'this is an official message. it must not be tampered with!';
var signature = 'b0319d11150e57d6dd8894b7d447f1f073e65fe85db1a83221f91dd3d4fecfdb';
var secret = 's3cr3t';

var isValid = stringSigner.isValidSignature(signature, message, secret);
```
`isValid` will be either `true` or `false`.

## Run tests
```
$ npm test
```
## Issues
Create an [issue](https://github.com/crcastle/nodejs-string-signer.git) or make a pull request.
## Credit
* Based on [nshah](https://github.com/nshah)'s [nodejs-signed-request](https://github.com/nshah/nodejs-signed-request) library ([Apache licensed](http://www.apache.org/licenses/LICENSE-2.0.html))
* Contributions from [dcarney](https://github.com/dcarney)

## License
This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors of this software dedicate any and all copyright interest in the software to the public domain. We make this dedication for the benefit of the public at large and to the detriment of our heirs and successors. We intend this dedication to be an overt act of relinquishment in perpetuity of all present and future rights to this software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org/>

![unlicense](http://unlicense.org/pd-icon.png "unlicense")
