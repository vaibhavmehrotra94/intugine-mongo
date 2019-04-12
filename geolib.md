# @intugine-technologies/geolib

A Geo Library for calculating center Coordinates and distance between two coordinated.

## Installation

First install Node.js and Mongodb. Then:

```
npm i --save @intugine-technologies/geolib
```

## Importing

```
// Using Node.js `require()`
const geolib = require("@intugine-technologies/geolib");

// Using ES6 imports
import geolib from "@intugine-technologies/geolib";
```

## Overview

### Center Calculation

```
const geolib = require("@intugine-technologies/geolib");

/**
* @params {Array} data - array of coordinates which itself is an Array containing lat,long.
*/

const centerCoordinates = geolib.center(data); // returns [lat, long]
```

### Distance Calculation

```
const geolib = require("@intugine-technologies/geolib");

/**
 * Calculates distance between 2 Geo cordinates
 * @param {Number[]} src - Source coordinates
 * @param {Number[]} dest - Destination coordinates
 */

const distance = geolib.distance(src, dest);
```
