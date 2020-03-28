# ELK
1、编辑 haproxy 服务配置文件
log 127.0.0.1 local6 info 
2、编辑 rsyslog 服务配置文件
# vim /etc/rsyslog.conf 
$ModLoad imudp
$UDPServerRun 514 
$ModLoad imtcp 
$InputTCPServerRun 514 
local6.*     /var/log/haproxy.log #测试可以正常将日志写入本地自定义文件 
local6.*     @@192.168.134.190:516   #最后面一行添加，local6 对应 haproxy 配置文件定义的 local 级别 
3、编辑 logstash 配置文件
配置 logstash 监听一个本地端口作为日志输入源，haproxy 服务器的 rsyslog 输 出 IP 和端口要等同于 logstash 服务器监听的 IP:端口，本次的配置是在 Host1 上 开启 logstash，在 Host2 上收集 haproxy 的访问日志并转发至 Host1 服务器的 logstash 进行处理
