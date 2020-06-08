# ab-result

[![Build Status](https://travis-ci.org/aquilax/ab-result.svg?branch=master)](https://travis-ci.org/aquilax/ab-result)
[![Try ab-result on RunKit](https://badge.runkitcdn.com/ab-result.svg](https://npm.runkit.com/ab-result)

Apache Benchmark result parser

## Installation

```bash
npm install --save ab-result-parser
```

## Usage

```js
const abResultParser = require('ab-result-parser');

const data  = `This is ApacheBench, Version 2.3 <$Revision: 1826891 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking 127.0.0.1 (be patient)
Completed 1000 requests
Completed 2000 requests
Completed 3000 requests
Completed 4000 requests
Completed 5000 requests
Completed 6000 requests
Completed 7000 requests
Completed 8000 requests
Completed 9000 requests
Completed 10000 requests
Finished 10000 requests


Server Software:
Server Hostname:        127.0.0.1
Server Port:            8000

Document Path:          /
Document Length:        16 bytes

Concurrency Level:      20
Time taken for tests:   2.073 seconds
Complete requests:      10000
Failed requests:        0
Total transferred:      2230000 bytes
HTML transferred:       160000 bytes
Requests per second:    4822.95 [#/sec] (mean)
Time per request:       4.147 [ms] (mean)
Time per request:       0.207 [ms] (mean, across all concurrent requests)
Transfer rate:          1050.31 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   5.3      0     263
Processing:     0    4  10.7      3     266
Waiting:        0    4  10.7      3     266
Total:          1    4  11.9      3     266

Percentage of the requests served within a certain time (ms)
  50%      3
  66%      4
  75%      4
  80%      5
  90%      6
  95%      8
  98%     13
  99%     16
 100%    266 (longest request)`;

const result = abResultParser(data);
console.log(result);
```
