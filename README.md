# KnownsecSpider

## 要求

[knownsec-recruitment](http://blog.knownsec.com/2012/02/knownsec-recruitment/)

>使用python编写一个网站爬虫程序，支持参数如下：

>spider.py -u url -d deep -f logfile -l loglevel(1-5)  --testself -thread number --dbfile  filepath  --key=”HTML5”

 

>参数说明：

>-u 指定爬虫开始地址

>-d 指定爬虫深度

>--thread 指定线程池大小，多线程爬取页面，可选参数，默认10

>--dbfile 存放结果数据到指定的数据库（sqlite）文件中

>--key 页面内的关键词，获取满足该关键词的网页，可选参数，默认为所有页面

>-l 日志记录文件记录详细程度，数字越大记录越详细，可选参数，默认spider.log

>--testself 程序自测，可选参数

 

>功能描述：

>1、指定网站爬取指定深度的页面，将包含指定关键词的页面内容存放到sqlite3数据库文件中

>2、程序每隔10秒在屏幕上打印进度信息

>3、支持线程池机制，并发爬取网页

>4、代码需要详尽的注释，自己需要深刻理解该程序所涉及到的各类知识点

>5、需要自己实现线程池

 

>提示1：使用re  urllib/urllib2  beautifulsoup/lxml2  threading optparse Queue  sqlite3 logger  doctest等模块

>提示2：注意是“线程池”而不仅仅是多线程

>提示3：爬取sina.com.cn两级深度要能正常结束

 


## 思路
- 使用 threading 和 Queue 实现自己的线程池类 MyThreadPool 负责线程管理与分配
- 使用 logging 和 logging.config 实现命令行与文件的双重日志记录
- 使用 sqlite3 实现自己的数据库类 MySqlite 负责数据库的管理
- 使用 argparse 解析命令行参数
- 使用 requests 发送页面请求
- 使用 beautifulsoup4 分析提取页面内容
- 使用 doctest 实现自测功能

## 实现历程

http://answerrrrrrrrr.github.io/tags/Spider/

## 用法

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
  --testself            self-test
```

## 第三方库

```shell
pip install beautifulsoup4
```

## 运行截图
```
$ python myspider.py -u www.sina.com.cn -d 2
```

![res](http://7xsrqj.com2.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-04-09%20%E4%B8%8A%E5%8D%888.41.41.png)