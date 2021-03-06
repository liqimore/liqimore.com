---
author: liqimore
categories:
  - 编程
comments: true
date: 2016-07-31 01:58:00+00:00
link: http://blog.codefog.com/nginxv.html
slug: nginxv
title: Nginx配置文件详解以及含义
---


一. 配置文件结构  

配置——Nginx配置文件解析  

![000.png](http://old.timelovelife.com/usr/uploads/2016/07/2887883292.png)  

二. 全局块详解  

#定义nginx运行的用户和用户组  

user www www;  

#定义nginx进程数（建议设置为CPU数）  

worker_processes 8;  

#全局错误日志定义类型（错误日志类型：[debug|info|notice|warn|error|crit]，从左到右错误信息越来越少；此指令可以在全局、http、server、location块中配置）  

error_log /var/log/nginx/error.log info;  

#定义进程文件  

pid /var/run/nginx.pid;




三. events块详解  

#定义工作模式  

use epoll  

#连接数上限（单个进程的最大连接数，web服务器的最大访问用户数 max clients = worker_processes * worker_connections）  

worker_connections 1024  

#网络连接序列化（为了避免唤醒太多的进程数，会影响系统性能）  

accept_mutex  on  

#工作进程是否允许同时接收多个网络连接  

multi_accept  on  

四. http块详解  

#设定mime类型（MIME-Type类型由mime.type文件定义）  

include /etc/nginx/mime.types;  

default_type application/octet-stream;  

#默认编码  

charset utf-8;  

#定义服务器日志（此处的日志与常规的不同，它记录的是nginx服务器提供服务过程中应答前端请求的日志）  

access_log /var/log/nginx/access.log combined;  

log_format combined  '$remote_addr - $remote_user [$time_local] "$request" '  

'$status $body_bytes_sent "$http_referer" '  

#连接超时时间（单位：秒，可在http、server、location中配置）  

keepalive_timeout 120;  

reset_timeout_connection on;  

#单连接请求数上限 （限制用户通过某一连接项服务器发送请求的次数，可在http、server、location中配置）  

keepalive_requests 100;  

#是否允许sendfile方式传输文件（可在http、server、location中配置）  

sendfile on;  

sendfile_max_chunk 128k   （#如果设置为0，则无限制）




# 




tcp_nopush on;  

#开启gzip压缩  

gzip  on;  

gzip_disable "MSIE [1-6].(?!.*SV1)";  

gzip _min_length  1000;  

gzip_buffers  168k  

#设置负载均衡服务器列表  

upstream mysvr {  

server 192.168.1:80 weight=5;  

server 192.168.1:80 weight=2;  

server 192.168.1:80 weight=8;  

}  

#shorten the timeout period, original one is 300  

fastcgi_connect_timeout 30;  

fastcgi_send_timeout 300;  

fastcgi_read_timeout 300;  

fastcgi_buffer_size 128k;  

fastcgi_buffers 8 128k;  

fastcgi_busy_buffers_size 256k;  

fastcgi_temp_file_write_size 256k;  

fastcgi_intercept_errors on;  

fastcgi_hide_header Pragma;  

# fastcgi cache  

fastcgi_cache_path temp/fastcgi_cache levels=1:2 keys_zone=cache_voice:128m inactive=30m max_size=4G;  

五. server块详解  

#监听端口  

listen 80;  

#服务域名  

server_name www.xxx.com;  

#虚拟主机的访问日志  

access_log /var/log/nginx/www.xxx.com_access.log main;  

#如果指定http错误状态码，则返回客户端指定的url地址  

error_page 500 502 503 504 /50x.html;  

location = 50x.html {  

root /home/xiaoju/webroot;  

}  

六. location块详解  

#定义网站根目录  

root /home/xiaoju/webroot;  

#定义首页索引文件的名称  

index index.php index.html index.htm;




fastcgi_pass  www.xx.com;  

fastcgi_param  SCRIPT_FILENAME  $document_root/$fastcgi_script_name;  

include /etc/nginx/fastcgi_params;  

#引入配置文件（可以放在配置文件的任意位置）  

include /etc/nginx/conf.d/_.conf;  

include /etc/nginx/sites-enabled/_;  

#运行用户  

user www-data;  

#启动进程,通常设置成和cpu的数量相等  

worker_processes  1;  

#全局错误日志及PID文件  

error_log  /var/log/nginx/error.log;  

pid        /var/run/nginx.pid;  

#工作模式及连接数上限  

events {  

use   epoll;             #epoll是多路复用IO(I/O Multiplexing)中的一种方式,但是仅用于linux2.6以上内核,可以大大提高nginx的性能  

worker_connections  1024;#单个后台worker process进程的最大并发链接数  

# multi_accept on;  

}  

#设定http服务器，利用它的反向代理功能提供负载均衡支持  

http {  

#设定mime类型,类型由mime.type文件定义  

include       /etc/nginx/mime.types;  

default_type  application/octet-stream;  

#设定日志格式  

access_log    /var/log/nginx/access.log;  

#sendfile 指令指定 nginx 是否调用 sendfile 函数（zero copy 方式）来输出文件，对于普通应用，  

#必须设为 on,如果用来进行下载等应用磁盘IO重负载应用，可设置为 off，以平衡磁盘与网络I/O处理速度，降低系统的uptime.  

sendfile        on;  

#tcp_nopush     on;  

#连接超时时间  

#keepalive_timeout  0;  

keepalive_timeout  65;  

tcp_nodelay        on;



    
    <code>#开启gzip压缩
    gzip  on;
    gzip_disable "MSIE [1-6]\.(?!.*SV1)";
    #设定请求缓冲
    client_header_buffer_size    1k;
    large_client_header_buffers  4 4k;
    include /etc/nginx/conf.d/*.conf;
    include /etc/nginx/sites-enabled/*;
    #设定负载均衡的服务器列表
     upstream mysvr {
    #weigth参数表示权值，权值越高被分配到的几率越大
    #本机上的Squid开启3128端口
    server 192.168.8.1:3128 weight=5;
    server 192.168.8.2:80  weight=1;
    server 192.168.8.3:80  weight=6;
    }
    </code>




server {  

#侦听80端口  

listen       80;  

#定义使用www.xx.com访问  

server_name  www.xx.com;  

#设定本虚拟主机的访问日志  

access_log  logs/www.xx.com.access.log  main;  

#默认请求  

location / {  

root   /root;      #定义服务器的默认网站根目录位置  

index index.php index.html index.htm;   #定义首页索引文件的名称  

fastcgi_pass  www.xx.com;  

fastcgi_param  SCRIPT_FILENAME  $document_root/$fastcgi_script_name;  

include /etc/nginx/fastcgi_params;  

}  

# 定义错误提示页面  

error_page   500 502 503 504 /50x.html;  

location = /50x.html {  

root   /root;  

}  

#静态文件，nginx自己处理  

location ~ ^/(images|javascript|js|css|flash|media|static)/ {  

root /var/www/virtual/htdocs;  

#过期30天，静态文件不怎么更新，过期可以设大一点，如果频繁更新，则可以设置得小一点。  

expires 30d;  

}  

#PHP 脚本请求全部转发到 FastCGI处理. 使用FastCGI默认配置.  

location ~ .php$ {  

root /root;  

fastcgi_pass 127.0.0.1:9000;  

fastcgi_index index.php;  

fastcgi_param SCRIPT_FILENAME /home/www/www$fastcgi_script_name;  

include fastcgi_params;  

}  

#设定查看Nginx状态的地址  

location /NginxStatus {  

stub_status            on;  

access_log              on;  

auth_basic              "NginxStatus";  

auth_basic_user_file  conf/htpasswd;  

}  

#禁止访问 .htxxx 文件  

location ~ /.ht {  

deny all;  

}



    
    <code> }
    </code>




}  

以上是一些基本的配置,使用Nginx最大的好处就是负载均衡  

如果要使用负载均衡的话,可以修改配置http节点如下：  

#设定http服务器，利用它的反向代理功能提供负载均衡支持  

http {  

#设定mime类型,类型由mime.type文件定义  

include       /etc/nginx/mime.types;  

default_type  application/octet-stream;  

#设定日志格式  

access_log    /var/log/nginx/access.log;  

#省略上文有的一些配置节点  

#。。。。。。。。。。  

#设定负载均衡的服务器列表  

upstream mysvr {  

#weigth参数表示权值，权值越高被分配到的几率越大  

server 192.168.8.1x:3128 weight=5;#本机上的Squid开启3128端口  

server 192.168.8.2x:80  weight=1;  

server 192.168.8.3x:80  weight=6;  

}  

upstream mysvr2 {  

#weigth参数表示权值，权值越高被分配到的几率越大  

server 192.168.8.x:80  weight=1;  

server 192.168.8.x:80  weight=6;  

}  

#第一个虚拟服务器  

server {  

#侦听192.168.8.x的80端口  

listen       80;  

server_name  192.168.8.x;  

#对aspx后缀的进行负载均衡请求  

location ~ ._.aspx$ {  

root   /root;      #定义服务器的默认网站根目录位置  

index index.php index.html index.htm;   #定义首页索引文件的名称  

proxy_pass  http://mysvr ;#请求转向mysvr 定义的服务器列表  

#以下是一些反向代理的配置可删除.  

proxy_redirect off;  

#后端的Web服务器可以通过X-Forwarded-For获取用户真实IP  

proxy_set_header Host $host;  

proxy_set_header X-Real-IP $remote_addr;  

proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;  

client_max_body_size 10m;    #允许客户端请求的最大单文件字节数  

client_body_buffer_size 128k;  #缓冲区代理缓冲用户端请求的最大字节数，  

proxy_connect_timeout 90;  #nginx跟后端服务器连接超时时间(代理连接超时)  

proxy_send_timeout 90;        #后端服务器数据回传时间(代理发送超时)  

proxy_read_timeout 90;         #连接成功后，后端服务器响应时间(代理接收超时)  

proxy_buffer_size 4k;             #设置代理服务器（nginx）保存用户头信息的缓冲区大小  

proxy_buffers 4 32k;               #proxy_buffers缓冲区，网页平均在32k以下的话，这样设置  

proxy_busy_buffers_size 64k;    #高负荷下缓冲大小（proxy_buffers_2）  

proxy_temp_file_write_size 64k;  #设定缓存文件夹大小，大于这个值，将从upstream服务器传  

}  

}  

}


