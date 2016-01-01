# firebase-cron [![NPM version](https://img.shields.io/npm/v/firebase-cron.svg)](https://www.npmjs.com/package/firebase-cron)

> Store and run cron jobs with firebase.

## Install
Install with [npm](https://www.npmjs.com/)

```sh
$ npm i firebase-cron --save
```

## Usage

```js
var Cron = require('firebase-cron');
```

## API

### [Cron](index.js#L31)
Main `Cron` class for creating a new instance to manage cron jobs.


**Params**

* `ref` **{Object}**: Instance of a [firebase][] reference pointing to the root of a [firebase][].    
* `queue` **{Object}**: Instance of a [firebase][] refernece pointing to a [firebase-queue][].    
* `options` **{Object}**: Options specifying where the cron jobs are stored.    
* `options.endpoint` **{String}**: Specific endpoint relative to the `ref` where the cron jobs are stored (defaults to `jobs`.    

**Example**



```js
var Firebase = require('firebase');
var ref = new Firebase('https://{your-firebase}.firebaseio.com');
var queueRef = new Firebase('https://{your-firebase}.firebaseio.com/queue');
var options = {endpoint: 'jobs'};

var cron = new Cron(ref, queueRef, options);
```


### [.addJob](index.js#L61)

Add a new cron job.

**Params**

* `name` **{String}**: Name of the cron job.    
* `tab` **{String}**: Cron job schedule. See [cron job patterns]() for specifics.    
* `data` **{Object}**: Data to be pushed onto the [firebase-queue][] when job is run.    
* `cb` **{Function}**: Callback function that is called after the job is added to the database.    



### [.updateJob](index.js#L82)

Update a cron job.

**Params**

* `name` **{String}**: Name of the cron job.    
* `tab` **{String}**: Cron job schedule. See [cron job patterns]() for specifics.    
* `data` **{Object}**: Data to be pushed onto the [firebase-queue][] when job is run.    
* `cb` **{Function}**: Callback function that is called after the job is updated in the database.    



### [.deleteJob](index.js#L101)

Remove a cron job.

**Params**

* `name` **{String}**: Name of the cron job.    
* `cb` **{Function}**: Callback function that is called after the job is removed from the database.    



### [.getJob](index.js#L113)

Get a cron job.

**Params**

* `name` **{String}**: Name of the cron job.    
* `cb` **{Function}**: Callback function that is called with any errors or the job.    



### [.getJobs](index.js#L126)

Get all of the cron jobs.

**Params**

* `cb` **{Function}**: Callback function that is called retrieving all of the jobs.    



### [.waitingJobs](index.js#L140)

Get all of the scheduled/waiting jobs.

**Params**

* `cb` **{Function}**: Callback function that is called after retrieveing all of the waiting jobs.    



### [.run](index.js#L158)

Start running the cron manager.

**Params**

* `cb` **{Function}**: Callback function that is called each time manager checks for jobs to run.    
* `error` **{Function}**: Callback function that is called if an error occurrs.    




## Related projects
* [firebase](https://www.npmjs.com/package/firebase): Firebase library for Node.js | [homepage](undefined)
* [firebase-queue](https://www.npmjs.com/package/firebase-queue): A fault-tolerant, multi-worker, multi-stage job pipeline built on Firebase | [homepage](https://github.com/firebase/firebase-queue)

## Running tests
Install dev dependencies:

```sh
$ npm i -d && npm test
```

## Contributing
Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/doowb/firebase-cron/issues/new).

## Author
**Brian Woodward**

+ [github/doowb](https://github.com/doowb)
+ [twitter/doowb](http://twitter.com/doowb)

## License
Copyright © 2016 [Brian Woodward](https://github.com/doowb)
Released under the MIT license.

***

_This file was generated by [verb](https://github.com/verbose/verb) on January 01, 2016._

[firebase]: https://www.firebase.com/
[firebase-queue]: https://github.com/firebase/firebase-queue
