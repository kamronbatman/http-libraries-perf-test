# HTTP libraries performance test (3/2020)

Forked from [nik-kor/http-libraries-perf-test](https://github.com/nik-kor/http-libraries-perf-test)

Includes:
* http.request - But who really wants to use that?
* axios
* node-fetch
* got
* phin
* request
* requestify
* simpleget
* superagent
* unirest

My results:
```bash
➜  http-libraries-perf-test git:(master) ✗ node index.js
http.request GET request x 41,763 ops/sec ±14.06% (79 runs sampled)
http.request POST request x 39,168 ops/sec ±3.17% (76 runs sampled)
axios GET request x 10,994 ops/sec ±3.78% (79 runs sampled)
axios POST request x 11,617 ops/sec ±2.81% (79 runs sampled)
got GET request x 2,282 ops/sec ±4.53% (73 runs sampled)
got POST request x 2,328 ops/sec ±4.39% (78 runs sampled)
fetch GET request x 18,127 ops/sec ±3.38% (76 runs sampled)
fetch POST request x 17,367 ops/sec ±0.99% (82 runs sampled)
phin GET request x 23,531 ops/sec ±1.88% (79 runs sampled)
phin POST request x 24,186 ops/sec ±4.15% (76 runs sampled)
request GET request x 13,473 ops/sec ±5.74% (75 runs sampled)
request POST request x 12,528 ops/sec ±2.03% (80 runs sampled)
requestify GET request x 14,196 ops/sec ±7.42% (76 runs sampled)
requestify POST request x 13,155 ops/sec ±1.36% (77 runs sampled)
simple-get GET request x 24,040 ops/sec ±0.82% (81 runs sampled)
simple-get POST request x 21,128 ops/sec ±1.81% (78 runs sampled)
superagent GET request x 16,986 ops/sec ±10.93% (71 runs sampled)
superagent POST request x 19,481 ops/sec ±1.21% (81 runs sampled)
unirest GET request x 7,470 ops/sec ±9.27% (71 runs sampled)
unirest POST request x 7,648 ops/sec ±0.72% (80 runs sampled)
urllib GET request x 17,287 ops/sec ±1.90% (80 runs sampled)
urllib POST request x 17,459 ops/sec ±0.52% (82 runs sampled)
fly GET request x 314 ops/sec ±7.22% (72 runs sampled)
fly POST request x 385 ops/sec ±4.82% (69 runs sampled)
Fastest is http.request
```

Test run on: Feb 5th, 2019 @ 7:50p PT with the following specs:
NodeJS: 12.16.1 LTS-Erbium
Operating System: MacOS Mojave 10.14.6
Model: Apple Macbook Pro 15-inch 2019
Processor: 2.3Ghz Intel Core i9
Memory: 32GB 2400 Mhz LPDDR4
Disk: 1TB Flash (Samsung on-board SSD rated 3.5Gbps)

The clear winners are: `phin` and `simple-get` for performance alone.

####Notes
Mime was modified to make unirest work: https://github.com/Kong/unirest-nodejs/pull/129
Fly has specifically terrible performance. Possibly a bad configuration.
Not all libraries have the same feature set and might be missing something.
