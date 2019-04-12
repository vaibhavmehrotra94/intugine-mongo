# @intugine-technologies/mongodb

A mongo envelope specifically designed in house for Intugine Technologies.

## Installation

First install Node.js and Mongodb. Then:

```
npm i --save @intugine-technologies/mongodb
```

## Importing

```
// Using Node.js `require()`
const mongo = require("@intugine-technologies/mongodb");

// Using ES6 imports
import mongo from "@intugine-technologies/mongodb";
```

## Overview

### Connecting to MongoDB

First, we need to define a connection.

```
const mongo = require("@intugine-technologies/mongodb");

mongo("MongoDB Connection URI here", "DB_Name here", {useNewUrlParser: true});
```

**Note-** If the Given DB doesn't exist in the provided URI then a new DB gets created automatically when the first document entry is made in a collection.

Once connected the mongo function returns a promise. So, any further operations can be done use **.then()** function.

### Create a new collection

```
const mongo = require("@intugine-technologies/mongodb");
let db;

mongo("MongoDB Connection URI here", "DB_Name here", {useNewUrlParser: true})
.then(res => {
    db = res;

/**
*@params {Object} data - document data to be stored in collection
*/

    db.create("collection_name", data);
})
.then(res => {
    db.close();
    db = null;
});
```

### Read from Database

```
const mongo = require("@intugine-technologies/mongodb");
let db;


mongo("MongoDB Connection URI here", "DB_Name here", {useNewUrlParser: true})
.then(res => {
    db = res;

/**
* All the options follow standard MongoDB syntax
* @params {Object} query - Standard MongoDB query.
* @params {Number} limit - If any certain number of documents are needed.
* @params {Number} offset - To skip some number of documents from beginning.
* @params {Object} projection - standard MongoDB projections.
* @params {Object} sort - Any sorting options will go in here.
*/


    db.read("collection_name", [query], [limit], [offset], [projection], [sort]);
})
.then(res => {
    db.close();
    db = null;
});
```

**Note-** By default sort option is set to `{_id:-1}`

### Update any Document

```
const mongo = require("@intugine-technologies/mongodb");
let db;


mongo("MongoDB Connection URI here", "DB_Name here", {useNewUrlParser: true})
.then(res => {
    db = res;

/**
* All the options follow standard MongoDB syntax
* @params {Object} query - Standard MongoDB query.
* @params {Object} change - standard MongoDB projections.
* @params {Object} options - Any sorting options will go in here.
*/

    db.update("collection_name", [query], [change], [options]);
})
.then(res => {
    db.close();
    db = null;
});
```
