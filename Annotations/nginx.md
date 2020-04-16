include mime.types;                                     #文件扩展名与文件类型映射表
default_type application/octet-stream;                  #默认文件类型
charset utf-8;                                          #默认编码
server_names_hash_bucket_size 128;                      #服务器名字的hash表大小
client_header_buffer_size 32k;                          #上传文件大小限制
large_client_header_buffers 4 64k;                      #设定请求缓
client_max_body_size 8m;                                #设定请求缓
sendfile on;                                            #开启高效文件传输模式，sendfile指令指定nginx是否调用sendfile函数来输出文件，对于普通应用设为 on，如果用来进行下载等应用磁盘IO重负载应用，可设置为off，以平衡磁盘与网络I/O处理速度，降低系统的负载。注意：如果图片显示不正常把这个改成off。
autoindex on;                                           #开启目录列表访问，合适下载服务器，默认关闭。
tcp_nopush on;                                          #防止网络阻塞
tcp_nodelay on;                                         #防止网络阻塞
keepalive_timeout 120;                                  #长连接超时时间，单位是秒
