1.GitHub简介
Git是一个分布式版本控制系统，与其相对的是CVS、SVN等集中式的版本控制系统。

2.Git安装
runhao@runhao-X550ZE:~$ git --version
Command 'git' not found, but can be installed with: sudo apt install git
runhao@runhao-X550ZE:~$ sudo apt-get install git
[sudo] runhao 的密码： 
正在读取软件包列表... 完成
正在分析软件包的依赖关系树       
正在读取状态信息... 完成       
升级了 0 个软件包，新安装了 3 个软件包，要卸载 0 个软件包，有 7 个软件包未被升级。
需要下载 4,741 kB 的归档。
解压缩后会消耗 34.0 MB 的额外空间。
您希望继续执行吗？ [Y/n] y
正在处理用于 man-db (2.8.3-2ubuntu0.1) 的触发器 ...
runhao@runhao-X550ZE:~$ git --version
git version 2.17.1

3.GitHub账号注册


4.生成添加公钥
runhao@runhao-X550ZE:~$ cd ~/.ssh
bash: cd: /home/runhao/.ssh: 没有那个文件或目录
runhao@runhao-X550ZE:~$ ssh-keygen -t rsa -C "1549971272@qq.com" 
Generating public/private rsa key pair.
Enter file in which to save the key (/home/runhao/.ssh/id_rsa): 
Created directory '/home/runhao/.ssh'.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/runhao/.ssh/id_rsa.
Your public key has been saved in /home/runhao/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:si9fQZBqWkshk4k5/+SWv1rpNLbwyi18MQ15f4BZVxw 1549971272@qq.com
The key's randomart image is:
+---[RSA 2048]----+
|   o o  ..     Eo|
|  + = . ..  . . .|
|   o o o ..+ .   |
|    . * o.+ .    |
|     O.oS+.. .   |
|    . *oo.... .  |
|     oo.*o.  .   |
|     .+Xo+       |
|      +BO.       |
+----[SHA256]-----+
runhao@runhao-X550ZE:~/.ssh$ sudo cat id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDP8kQ5wnuKWnwRm6HRbN+/OI4tVx5EdUMQnkluj8NIMgSKOTBJ7jGYxILBiQg4BTiFylULhM4pcQxoYDra+atr6RyPicAlKc2LmYf2vqJx2AjIO3CyHNU/YUV27tJ6XDVHgnORoM04awXj0+SRKXPS/krLx27AcxDTPBcVmngxt5DtMdGTlFJm0NE7NMzCOVKWUyjwzQTWJ5gGrBUtD2GI4tVYYtTvktG4flmiyjiyGlMpJsyRdZzfdHYJL0RbvkVXLjuY12jqkLilWIUxToiNkVUv+TMG6Jfrs4V1ZVzwbV2CPpmJn8FbFOnK5Uw7wFLbtEylGf9h+SqNABAfh7sZ 1549971272@qq.com
runhao@runhao-X550ZE:~$ ssh -T git@github.com
The authenticity of host 'github.com (13.250.177.223)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'github.com,13.250.177.223' (RSA) to the list of known hosts.
Hi runhao! You've successfully authenticated, but GitHub does not provide shell access.
runhao@runhao-X550ZE:~$ git config --global user.name "runhao"
runhao@runhao-X550ZE:~$ git config --global user.email "1549971272@qq.com"
5.目录文件上传同步
runhao@runhao-X550ZE:~$ mkdir github
runhao@runhao-X550ZE:~/github$ git init
已初始化空的 Git 仓库于 /home/runhao/github/.git/
runhao@runhao-X550ZE:~/github$ git status
位于分支 master
尚无提交
无文件要提交（创建/拷贝文件并使用 "git add" 建立跟踪）
runhao@runhao-X550ZE:~/github$ git --bare init
已初始化空的 Git 仓库于 /home/runhao/github/
runhao@runhao-X550ZE:~/github$ git remote add origin git@github.com:runhao/github.git
runhao@runhao-X550ZE:~/github$ git add README
runhao@runhao-X550ZE:~/github$ git commit -m "for classwork"
[master （根提交） 64fdb07] for classwork
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README
runhao@runhao-X550ZE:~/github/.git$ git push -u origin master
对象计数中: 3, 完成.
写入对象中: 100% (3/3), 207 bytes | 207.00 KiB/s, 完成.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:runhao/management.git
 * [new branch]      master -> master
分支 'master' 设置为跟踪来自 'origin' 的远程分支 'master'。













