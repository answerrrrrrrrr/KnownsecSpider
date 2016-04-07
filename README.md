# KnownsecSpider

## Intro

[知道创宇面试题](http://blog.knownsec.com/2012/02/knownsec-recruitment/)

## Usage

```shell 
usage: myspider.py [-h] -u URL [-d DEPTH] [-f LOGFILE] [-l {1,2,3,4,5}] [--dbfile DBFILE] [--thread NUM_THREADS] [--key KEY] [--selftest]

optional arguments:
  -h, --help            show this help message and exit
  -u URL, --url URL     specify the URL to start crawl
  -d DEPTH, --depth DEPTH
                        specify the depth of the spider (default: 1)
  -f LOGFILE, --file LOGFILE
                        specify the path of logfile (default: spider.log)
  -l {1,2,3,4,5}, --level {1,2,3,4,5}
                        specify the verbose level of the log (default: 4)
  --dbfile DBFILE       specify the path of sqlite dbfile (default: spider.db)
  --thread NUM_THREADS  specify the size of thread pool (default: 10)
  --key KEY             specify the keyword (default: )
  --selftest            self-test
```

## Dependency

```shell
pip install beautifulsoup4
```