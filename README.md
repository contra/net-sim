[![Build Status](https://travis-ci.org/wearefractal/net-sim.png?branch=master)](https://travis-ci.org/wearefractal/net-sim)

If this is failing it is because travis-ci doesn't allow firewall manipulation.

[![NPM version](https://badge.fury.io/js/net-sim.png)](http://badge.fury.io/js/net-sim)

## Information

<table>
<tr> 
<td>Package</td><td>net-sim</td>
</tr>
<tr>
<td>Description</td>
<td>Simulate network conditions</td>
</tr>
<tr>
<td>Node Version</td>
<td>>= 0.8</td>
</tr>
</table>

You need to run this as root. This project aims to be cross-platform but so far only supports BSD/OSX using `ipfw`. I will add support on an as needed basis but PRs for this are welcome.

## Usage

```javascript
var sim = require('net-sim');

sim.addLatency('127.0.0.1', 25, function(err){
  // run some tests here

  sim.clear(function(err){

  });
});
```

#### sim.addLatency(ip/host, ms, cb)

Latency is added both ways so if you say 250 then a ping will take 500ms (round trip). Adding latency multiple times is supported so make sure you .clear() if you are trying to reset it to another value.

#### sim.clear(cb)

Clear out all rules added to the OS. Removes any latency added.

## Examples

You can view more examples in the [example folder.](https://github.com/wearefractal/net-sim/tree/master/examples)

## LICENSE

(MIT License)

Copyright (c) 2013 Fractal <contact@wearefractal.com>

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
