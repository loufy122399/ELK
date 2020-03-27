# ELK
logstash收集java日志,多行合并成一行
使用 codec 的 multiline 插件实现多行匹配，这是一个可以将多行进行合并的插件，而且可以使用 what 指定将匹配到的行与前面的行合并还是和后面的行合并， https://www.elastic.co/guide/en/logstash/current/plugins-codecs-multiline.html 
