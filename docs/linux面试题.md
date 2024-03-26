### 常用的Linux命令

- shutdown -h now 立刻关机
- shutdown -h 5 5分钟后关
- poweroff 立刻关机
- shutdown -r now 立刻重启
- shutdown -r 5 5分钟后重启
- reboot 立刻重启
- cd / 切换到根目录cd
- /usr 切换到根目录下的usr目录
- cd …/ 切换到上一级目录 或 cd … cd ~ 切换到home目录
- cd - 切换到上次访问的目录
- ls 查看当前目录下的所有目录和文件
- ls -a查看当前目录下的所有目录和文件（包括隐藏的文件）
- ls -l 列表查看当前目录下的所有目录和文件（列表查看，显示更多信息）
- ls / 查看指定目录下的所有目录和文件
- 查找命令
- grep 命令是一种强大的文本搜索工具
- find 命令在目录结构中搜索文件，并对搜索结果执行指定的作。
- locate 让使用者可以很快速的搜寻某个路径。
- whereis 命令是定位可执行文件、源代码文件、帮助文件在文件系统中的位置。
- which 命令的作用是在PATH变量指定的路径中，搜索某个系统命令的位置，并且返回第一个搜索结果。
- 命令格式
- crontab [-u user] file
- crontab [-u user] [ -e | -l | -r ]
    参数说明：
    -u user：用来设定某个用户的crontab服务
    file：file是命令文件的名字,表示将file做为crontab的任务列表文件并载入crontab。
    -e：编辑某个用户的crontab文件内容。如果不指定用户，则表示编辑当前用户的crontab文件。
    -l：显示某个用户的crontab文件内容。如果不指定用户，则表示显示当前用户的crontab文件内容。
    -r：删除定时任务配置，从/var/spool/cron目录中删除某个用的crontab
    文件，如果不指定用户，则默认删除当前用户的crontab文件。
- pwd 查看当前目录路径
- ps -ef 查看所有正在运行的进程
- kill pid 或者 kill -9 pid(强制杀死进程) pid:进程号
- ifconfig：查看网卡信息
- ifconfig 或 ifconfig | more
- ping：查看与某台机器的连接情况
- ping ip
- netstat -an：查看当前系统端口
- netstat -an
- netstat -an | grep 8080 搜索指定端口

