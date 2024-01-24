---
title: python requests库 flask库(未完)
date: 2024-01-21 23:16:26
tags:
---
                   
        HTTP协议：超文本传输协议，是一个基于“请求于响应”模式的，无状态的应用层协议。
        HTTP协议采用URL作为定位网络资源的标识。
        URL格式：http://host[:port][path]
        Host:合法的internet主机域名或IP地址
        Port：端口号，可以省略，省略则是80
        Path:请求资源的路径。 
Request库的常见用法：
r = requests.get(url,params=None,**kwargs)
（url：拟获取页面的url链接；params:url中的额外参数，字典或字节流格式，可选，**kwargs:12个控制访问的参数）
两个对象：
1.reponse:是上文requests的位置；request是上文的get的位置。
属性	             说明
r.status_code	HTTP请求的返回状态，200表示链接成功，404表示失败。
r.text	HTTP响应内容的字符串形式，即,url对应的页面内容
r.encodiing	从HTTP header中猜测的响应内容编码方式
r.apparent_encoding	从内容中分析出的响应内容编码方式（备选编码方式）
r.content	HTTP响应内容的二进制形式


requests库的异常：
       异常	说明
requests.ConnectionError	网络连接错误异常，如DNS查询失败，拒接链接等
requests.HTTPError	HTTP错误异常
requests.URLRequired	URL缺失异常
requests.TooManyRedirects	超过最大重定向次数，产生重定向异常
requests.ConnectTimeout	连接远程服务器超市异常
requests.Timeout	请求URL超时，产生超时异常
r.raise_for_status()	如果不是200，产生异常requests.HTTPError

requests库的7个主要方法：
                 方法	                  说明
requests.request()	构建一个请求，支持一下个方法的基础方法
requests.get()	获取HTML网页的主要方法，对应于HTTP
requests.head()	获取HTML网页头信息的方法，对应于HTTP的HEAD
requests.post()	向HTML网页提交POST请求的方法，对应于HTTP的POST
requests.put()	向HTML网页提交PUT请求的方法，对应与HTTP的PUT
requests.patch()	向HTML网页提交局部修改请求，对应于HTTP的PATCH
requests.delete()	向HTML页面提交删除请求，对应于HTTP的DELETE

（1）requests.request()
函数原型：requests.request(method，url，**kwargs)  //method就是单引号中写下表的操作
delete是小写，其他都是大写
**kwargs:(可选)
1.params:字典或字节序列，作为参数增加到url中。
2.data：字典，字节寻猎或文件对象，作为requests的内容。
3.Json: JSON格式的数据。作为request的内容。
4.Header:字典，HTTP定制头。
以上要掌握。
5.Cookies：字典或CookieJar，Request中的cookie。
6.auth：元组，支持HTTP认证功能。
7.Files：字典类型，传输文件。
8.Timeout:设定超时时间，秒为单位。
9.Proxies：字典类型，设定访问代理服务器，可以增加登录认证。
其他高级选项：
10.allow_redirects: True/False,默认为True，重定义开关。
11.Stream: True/False,默认为True，获取内容立即下载开关。
12.Verify：True/False，默认为True，认证SSL证书开关。
13.cert：本地SSL证书路径。
（2）requests.post()：
函数原型：requests.post(url,data=None,json=None,**kwargs)


HTTP协议对资源的操作：
               方法	               说明
GET	请求获取URL位置的资源
HEAD	请求获取URL位置资源的响应消息报告，即获得该资源的头部信息
POST 	请求向URL位置的资源后附加新的数据
PUT	请求向URL位置存储一个资源，覆盖原URL位置的资源
PATCH	请求局部更新URL位置的资源，即改变该处资源的部分内容
DELETE	请求删除URL位置存储的资源

               HTTP协议方法	      Requests库方法	      功能一致性
GET	requests.request()	一致
HEAD	requests.get()	一致
POST 	requests.head()	一致
PUT	requests.post()	一致
PATCH	requests.put()	一致
DELETE	requests.patch()	一致


爬取网页的通用代码框架：
try:
   r=requests.get(url,timeout=30)
   r.raise_for_status()
   r.encoding=r.apparent_encoding
   return r.text
except:
   return “产生异常” 

                               Python flask框架
基本的框架：（创建了一个网页，写着Hello World）
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
   return 'Hello World'

if __name__ == '__main__':
   app.run()

可以于html一起使用。

-------------------------------------------------------
app.route(rule, options)
rule 参数表示与该函数的URL绑定。
@app.route('/hello') 
def hello_world(): 
return 'hello world'
URL'/ hello'规则绑定到hello_world()函数。 
因此，如果用户访问http://localhost:5000/hello URL，
hello_world()函数的输出将在浏览器中呈现。
-------------------------------------------------------------------------------
options 是要转发给基础Rule对象的参数列表。
在上面的示例中，’/ ’ URL与hello_world()函数绑定。因此，当在浏览器中打开web服务器的主页时，将呈现该函数的输出。
最后，Flask类的run()方法在本地开发服务器上运行应用程序。

app.run(host, port, debug, options)
host：要监听的主机名。 默认为127.0.0.1（localhost）。设置为“0.0.0.0”以使服务器在外部可用
port ：默认值为5000
debug：默认为false。 如果设置为true，则提供调试信息，可以自动重载代码并显示调试信息
options：要转发到底层的Werkzeug服务器。
                          Flask 变量规则
#!/usr/bin/python
# -*- coding: UTF-8 -*-
"""
@author:chenshifeng
@file:flask_demo.py
@time:2021/03/01
"""
from flask import Flask

app = Flask(__name__)


@app.route('/hello/<name>')
def hello_name(name):
    return 'Hello %s!' % name


if __name__ == '__main__':
    app.run(debug=True)
