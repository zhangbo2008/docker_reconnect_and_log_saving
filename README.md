# docker_reconnect_and_log_saving
自动化重连docker和日志宿主机保存. 工业级部署方案分享



#docker 自动化重连和日志配置
# 注意事项. 容器里面要有目录/yyzzocr-tr/rizhi





#部署命令
docker run -ti --user root -p 10022:22   -p  8080:8080  -v /home/troila/log:/yyzzocr-tr/rizhi  --restart=always  ocr_yyzz2     sh -c  "cd /yyzzocr-tr&&python3 server_for_old_yolov4.py  "

#进入容器查看用于debug
docker run -ti --user root -p 10022:22   -p  8080:8080  -v /home/troila/log:/mnt   --restart=always ocr_yyzz2    /bin/bash  

亲测有效.不管容器启动多少次,日志都往/home/troila/log目录里面写.追加模式

docker run -ti --user root -p 10022:22   -p  8081:8081  -v /home/troila/log:/mnt   --restart=always cd8876bb979e    /bin/bash  


进入docker 
nohup python3 informateion_extract_server.py &

然后输入ctrl+p+q 退出即可.
