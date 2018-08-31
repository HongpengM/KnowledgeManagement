# Block Google Analytics(OS X)
## 问题来源
在爬取一些网页时，网页中存在访问Google Analytics的连接，会直接影响访问速度，导致访问过慢
## 参考链接
http://www.aneasystone.com/archives/2018/02/python-selenium-spider.html

## 解决方法
设置代理服务器过滤非必须请求

## Requirements
```shell
BrowserMob Proxy
browsermob-proxy-py 
```
当然，Selenium和ChromeDriver的部分不再赘述
BrowserMob Proxy-从源码安装
https://github.com/lightbody/browsermob-proxy
mac 安装JDK后
```shell
brew install maven
git clone https://github.com/lightbody/browsermob-proxy .
mvn -DskipTests
```
maven安装后，会在`browsermob-dist/target` 下生成一个`.zip`文件
解压缩即可获取可执行文件
maven第一次安装会很久，这个时候可以干会别的

然后安装其python wrapper
```shell
pip install browsermob-proxy
```

## 使用
```python
from browsermobproxy import Server
 
server = Server("[your BMP executable path]")
server.start()
proxy = server.create_proxy()
 
proxy.blacklist(".*google.*", 404)
proxy.blacklist(".*yahoo.*", 404)
proxy.blacklist(".*facebook.*", 404)
proxy.blacklist(".*twitter.*", 404)
 
chrome_options = webdriver.ChromeOptions()
chrome_options.add_argument("--proxy-server={0}".format(proxy.proxy))
browser = webdriver.Chrome(
    chrome_options = chrome_options
)
```
