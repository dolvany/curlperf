# curlperf
A shell tool for ad hoc http performance analysis. Measures dns, tcp, ssl, first byte, last byte and total. Depends on curl, jq, parallel and column. All metrics are deltas, except for total. Error samples are excluded from measurment. Measurements are in milliseconds. Requires a version of curl that supports json write out.
```
% ./perf
Usage: ./perf [url] [sample count]
```
```
% ./perf https://nuc1/ 1000
100% 1000:0=5s curl -sko /dev/null -w "%{json}" https://nuc1/
error:  0
msec    min  avg  p95  max
dns     1    2    3    5
tcp     2    4    6    11
ssl     12   16   20   42
ttfb    3    5    7    13
ttlb    0    0    0    1
total   21   28   33   58
```
```
% curl -V
curl 8.7.1
```
```
% jq -V
jq-1.7.1
```
```
% parallel --version
GNU parallel 20250222
```
