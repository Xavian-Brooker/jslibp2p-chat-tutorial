Create a basic libp2p node
==========================

Hello & Welcome back. This is the segment where we'll actually be getting our hands on code! So lets get started. What we'll actually be doing in this segment is creating a `libp2p node`.  

Lets understand step by step, what is happening under the hood as we create a `libp2p node`:
```javascript
// 'use strict' is always a good practice to use
'use strict'

// Importing the util library
const util = require('util')
// Importing the libp2p library
const  { createLibp2p }  = require('libp2p')
```
Here we simply imported the module `libp2p`. 
```javascript
// Creating a Libp2p node

// Method 1 - Currently Default Version 
const libp2p = await Libp2p.create(options)
```
Now let's breakdown what just happened above. Both the methods mentioned could be used to create a Libp2p node. The first method is the default method used in the current versions of [js-libp2p](https://github.com/libp2p/js-libp2p/blob/8bed8f39ff3975850191cec93b7537d1428c8629/doc/API.md#create). 

The `create` method creates an instance of libp2p and requires an object `options` as its parameter. The `options` parameter is nothing but an object where we'll basically declare the different `transports` we'll be using, the specific configurations for our `libp2p node` etc.  *(We'll discuss about it later)*.  This returns a promise and hence is there a presence of the `await` keyword.

The same thing could be done in an another way. This will help us make our code look much cleaner and that's why this method is what we'll be moving towards with. 
```javascript
// Method 2 - What we'll be using
async  function main() {
	// Create a libp2p instance
	let libp2p =  await util.promisify(createLibp2p)(options)
}

// Calling the main function
main()
```
In the second version of doing the same thing, 
> Explain what we are doing 


* Explainig that libp2p-core is just a skeleton.
* All modules could be added through options
* Examples of creating options and setting up config for each options (Refer: https://github.com/libp2p/js-libp2p/blob/8bed8f39ff3975850191cec93b7537d1428c8629/doc/CONFIGURATION.md#configuration-examples
)
* All the fields in the option also gives a breif overview of what libp2p is built of. 
* Tip: I use utils.promisify to convert the createp2p node into promise rather than callback. This makes the code look cleaner. The current latest version by default returns a promise. 
* Your Turn:
    - Include the libp2p core, and utils
    - Declare an empty option map for now. 
    - Create an async main, and inside main, call the create libp2p node and pass options
    - Call main



<!-- tabs:start -->

#### ** Template **

[embedded-code](../assets/1/1.1-template-code.js ':include :type=code embed-template')

#### ** Solution **

[embedded-code-final](../assets/1/1.1-finished-code.js ':include :type=code embed-final')

#### ** Previous Chapter Solution **

[embedded-code-previous](../assets/1/1.0-finished-code.js ':include :type=code embed-previous')

<!-- tabs:end -->