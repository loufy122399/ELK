# ELK

通过 logstash 的 tcp/udp 插件收集日志，通常用于在向 elasticsearch 日志补录丢 失的部分日志，可以将丢失的日志写到一个文件，然后通过 TCP 日志收集方式直 接发送给 logstash 然后再写入到 elasticsearch 服务器
https://www.elastic.co/guide/en/logstash/5.6/input-plugins.html 
