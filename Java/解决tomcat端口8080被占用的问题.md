**解决tomcat端口8080被占用的问题**

`1.以管理员身份运行cmd，在dos下：`

`2.输入 netstat -ano|findstr 8080 回车 //说明：查看占用8080端口的进程`

`3.输入 taskkill /pid xxxx /f 回车 //说明，运行windows自带taskkill命令，将上面显示的进程号，结束掉。`

