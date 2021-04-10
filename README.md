<h1 align="center">Welcome to prom2csv 👋</h1>
<p align="center">
  <a href="https://github.com/fin-ger/prom2csv/blob/master/LICENSE">
    <img alt="GitHub" src="https://img.shields.io/github/license/fin-ger/prom2csv.svg">
  </a>
  <a href="http://spacemacs.org">
    <img src="https://cdn.rawgit.com/syl20bnr/spacemacs/442d025779da2f62fc86c2082703697714db6514/assets/spacemacs-badge.svg" />
  </a>
  <a href="http://makeapullrequest.com">
    <img alt="PRs Welcome" src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" target="_blank" />
  </a>
  <br>
  <i>Simple python script to log the output of a prometheus exporter as CSV</i>
</p>

---

This project periodically fetches a Prometheus exporter endpoint and logs selected metrics as CSV to `stdout`.

## How does it look like?

```
$ ./prom2csv -u http://127.0.0.1:34567/metrics \
>            -m rx_bytes \
>            -m tx_bytes > test.csv
    INFO Tip: You can pipe stdout to a file to store the CSV on disk!
    INFO Tip: Press Ctrl+C or send SIGINT to quit!
    INFO Listening on http://127.0.0.1:34567/metrics for 2 metrics...
^C    INFO Quitting...
$ head test.csv
time,rx_bytes,tx_bytes
0,5.456372e+06,3.776076e+06
100,5.456372e+06,3.776076e+06
200,5.456372e+06,3.776076e+06
300,5.456372e+06,3.776076e+06
400,5.456372e+06,3.776076e+06
500,5.456372e+06,3.776076e+06
600,5.456372e+06,3.776076e+06
700,5.456372e+06,3.776076e+06
800,5.456372e+06,3.776076e+06
$
```

## Installation

Just download the script `prom2csv` from this repository, make it executable and run it.

### Dependencies

 - Python 3
 - `requests` module

## Usage

The usage is straightforward, just look at the `help page`:

```
usage: prom2csv [-h] [-l {DEBUG,INFO,WARNING,ERROR,CRITICAL}] [-i INTERVAL]
                [-d DELIMITER] -u URL [-m METRICS] [-s]

Log prometheus metrics as csv

optional arguments:
  -h, --help            show this help message and exit
  -l {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --log-level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        the log level on stderr for this application
  -i INTERVAL, --interval INTERVAL
                        polling interval in ms
  -d DELIMITER, --delimiter DELIMITER
                        CSV delimiter character
  -u URL, --url URL     the prometheus exporter url
  -m METRICS, --metric METRICS
                        the metric names to record
  -s, --show            show available metrics and exit
```

## Troubleshooting

If you find any bugs/unexpected behaviour or you have a proposition for future changes open an issue describing the current behaviour and what you expected.

## Authors

**Fin Christensen**

> [:octocat: `@fin-ger`](https://github.com/fin-ger)  
> [:elephant: `@fin_ger@weirder.earth`](https://weirder.earth/@fin_ger)  

## Show your support

Give a :star: if this project helped you!
