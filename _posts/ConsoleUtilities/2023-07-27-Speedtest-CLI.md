---
layout: post
title:  Speedtest-CLI - Интерфейс командной строки
category: ConsoleUtilities
---

#speedtest

Интерфейс командной строки для тестирования пропускной способности интернета с помощью speedtest.net

## Installation

---

sudo apt install speedtest-cli

---

- pip / easy_install

- pip install speedtest-cli

or:

- easy_install speedtest-cli

## Github

- pip install git+https://github.com/sivel/speedtest-cli.git

or:

- git clone https://github.com/sivel/speedtest-cli.git

- cd speedtest-cli

- python setup.py install

## Just download (Like the way it used to be)

- wget -O speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py

- chmod +x speedtest-cli

or:

- curl -Lo speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py

- chmod +x speedtest-cli

---

## Usage

---

- $ speedtest-cli --simple

- $ speedtest-cli

- $ speedtest-cli -h

## usage: 

- speedtest-cli [-h] [--no-download] [--no-upload] [--single] [--bytes]

                     [--share] [--simple] [--csv]

                     [--csv-delimiter CSV_DELIMITER] [--csv-header] [--json]

                     [--list] [--server SERVER] [--exclude EXCLUDE]

                     [--mini MINI] [--source SOURCE] [--timeout TIMEOUT]

                     [--secure] [--no-pre-allocate] [--version]

Command line interface for testing internet bandwidth using speedtest.net.

---

- https://github.com/sivel/speedtest-cli

---

## optional arguments:
```
  -h, --help            show this help message and exit

  --no-download         Do not perform download test

  --no-upload           Do not perform upload test

  --single              Only use a single connection instead of multiple. This
                        simulates a typical file transfer.

  --bytes               Display values in bytes instead of bits. Does not
                        affect the image generated by --share, nor output from
                        --json or --csv

  --share               Generate and provide a URL to the speedtest.net share
                        results image, not displayed with --csv

  --simple              Suppress verbose output, only show basic information

  --csv                 Suppress verbose output, only show basic information
                        in CSV format. Speeds listed in bit/s and not affected
                        by --bytes

  --csv-delimiter CSV_DELIMITER                   Single character delimiter to use in CSV output.Default ","
                        
  --csv-header          Print CSV headers

  --json                Suppress verbose output, only show basic information
                        in JSON format. Speeds listed in bit/s and not
                        affected by --bytes

  --list                Display a list of speedtest.net servers sorted by
                        distance
  --server SERVER       Specify a server ID to test against. Can be supplied
                        multiple times

  --exclude EXCLUDE     Exclude a server from selection. Can be supplied
                        multiple times

  --mini MINI           URL of the Speedtest Mini server

  --source SOURCE       Source IP address to bind to

  --timeout TIMEOUT     HTTP timeout in seconds. Default 10

  --secure              Use HTTPS instead of HTTP when communicating with
                        speedtest.net operated servers

  --no-pre-allocate     Do not pre allocate upload data. Pre allocation is
                        enabled by default to improve upload performance. To
                        support systems with insufficient memory, use this
                        option to avoid a MemoryError

  --version             Show the version number and exit
  ```