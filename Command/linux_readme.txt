(1)查看局域网ip ：sudo apt-get install nmap
                 nmap -sP 192.168.1.162/24   (Replace 10.1.1.0 with yours IP)

                 sudo arp-scan -l   (也可应用，但有时不稳定)
(1-1)临时修改主机ip：ping 192.168.1.180
                    sudo ifconfig eth0 192.168.1.180
                    

(2)多PC资源下载 ： scp -r iRabbit gongwenbo@192.168.1.132:~/

(3)linux 突破权限删除和复制文件：sudo nautilus

(4)===== Terminal终端 =====
   CTRL + ALT + T: 打开终端
   TAB: 自动补全命令或文件名
   CTRL + SHIFT + V: 粘贴（Linux中不需要复制的动作，文本被选择就自动被复制）
   CTRL + SHIFT + T: 新建标签页
   CTRL + D: 关闭标签页
   CTRL + R + 文本: 在输入历史中搜索
   CTRL + A: 移动到行首
   CTRL + E: 移动到行末
   CTRL + C: 终止当前任务
   CTRL + Z: 把当前任务放到后台运行（相当于运行命令时后面加&）
   Ctrl+U 删除单签光标之前的所有字符
   Ctrl+K 删除光标后所有字符
(5)ubuntu 永久分配swap分区：sudo dd if=/dev/zero of=/mnt/4096Mb.swap bs=1M count=4096  //分配4096Mb
                           sudo mkswap 4096Mb.swap  //初始化
                           sudo swapon /mnt/4096Mb.swap  //临时挂载分区

                           sudo vi /etc/fstab  //永久挂载swap分区
                           /mnt/4096Mb.swap  none  swap  sw  0 0  //添加到/etc/fstab即可

(6)查看ubuntu swap 内存： free -l
(7)路由器组建局域网：切换为client+AP   开启dhcp服务(自动获取分配IP)
(8)文件.tar.gz 和 .tgz
    解压：tar zxvf FileName.tar.gz
    压缩：tar zcvf FileName.tar.gz DirName
(9)ubuntu终端配色：将 alias ls='ls --color=auto'添加 sudo vi .bashrc 即可；
  (
    蓝色代表目录；
    绿色代表可执行文件；
    红色表示压缩文件；
    浅蓝色表示链接文件；
    灰色表示其他文件；
    红色闪烁表示链接的文件有问题了
    黄色表示设备文件
   )
(10)service network restart   //重启网卡

(11)文件系统：  $ll
               比如：drwxr-xr-x   3 root root  4096  5月 21  2015 x86_64-linux-gnu/
               第一列：文件类型。（-普通文件，b块设备，c字符设备，d目录文件）
               第二列：表示文件个数。如果是文件，那么就是1；如果是目录，那么就是该目录中文件的数目。
               第三列：文件的所有者，即文件的创建者。
               第四列：文件所有者所在的用户组。在Linux中，每个用户都隶属于一个用户组。
               第五列：文件大小（以字节计）。
               第六列：文件被创建或上次被修改的时间。
               第七列：文件名或目录名。

（12）改变权限：chmod 777 filename
 (13) 环境变量： 
（14）进程：$top  查看进程COMMAND   
            $killall -9 COMMAND   //可以杀死进程；   
 (15)ssh:  sudo apt-get install ssh
           sudo service ssh status
              








                             
                           
