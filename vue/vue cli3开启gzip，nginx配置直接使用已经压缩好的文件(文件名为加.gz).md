**vue cli3开启gzip，nginx配置直接使用已经压缩好的文件(文件名为加.gz)**

*https://www.liangzl.com/get-article-detail-134882.html*



**怎么看nginx的gzip_static是否生效**

*https://segmentfault.com/q/1010000000125365*



```txt
gzip_static 生效的前提是nginx开启了gzip_static压缩并且请求目录下存在名称相同且以.gz 结尾的文件。

使用 gzip_static 压缩的话要先准备好压缩后的 gz 文件，并且服务器会消耗更多的空间来存储压缩文件和原文件，这个有利有弊要自己衡量。

在 linux 下可以使用命令来创建压缩文件：
tar -zcvf xx.gz xx

tar -zxvf xx.gz 这个是解压文件

如何查看gzip_static on命令是否生效呢?

配置：

server {
    gzip on;
    gzip_static on; #开启
    gzip_http_version 1.1;
    gzip_disable "MSIE [1-6]\.";
    gzip_vary on;
    gzip_proxied expired no-cache no-store private auth;
    gzip_types text/css; #这里text/css必须有，其他的按需要添加
    
    # ...其他配置
}
准备文件：

$ ls -l *0c3628cca1*
-rw-r--r--  1 djw  staff  308698  4 11 20:29 styles-0c3628cca1.css
-rw-r--r--  1 djw  staff   49123  4 28 14:15 styles-0c3628cca1.css.gz
发起请求：

curl -I -H "Accept-Encoding: gzip, deflate" http://test.local/styles-0c3628cca1.css

HTTP/1.1 200 OK
Server: nginx/1.13.12
Date: Sat, 28 Apr 2018 06:30:33 GMT
Content-Type: text/css
Content-Length: 49123
Last-Modified: Sat, 28 Apr 2018 06:15:43 GMT
看下面的：
Content-Type: text/css
Content-Length: 49123
是不是跟这个一样：-rw-r--r-- 1 djw staff 49123 4 28 14:15 styles-0c3628cca1.css.gz


=====================================================================================================


首先判断`content-encoding: gzip`
有表示开启了gzip;没有表示没开启gzip;

有的情况下
再看看`Etag`有没有`W\`,
有:代表服务器在线压缩
没有:表示拿了.gz,说明gzip_static生效了
```

