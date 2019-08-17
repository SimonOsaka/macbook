##安装和使用
1. 安装Centos7
2. 下载gitlab，清华大学开源镜像源https://mirrors.tuna.tsinghua.edu.cn/gitlab-ee/yum/el7/
3. 安装gitlab
```shell
# 安装依赖项 
# 来源：https://blog.csdn.net/misxu890312/article/details/85880229
sudo yum install -y curl policycoreutils-python openssh-server
sudo systemctl enable sshd
sudo systemctl start sshd
sudo firewall-cmd --permanent --add-service=http
sudo systemctl reload firewalld
```
```shell
# 安装Postfix以发送通知电子邮件
# 来源：https://blog.csdn.net/misxu890312/article/details/85880229
sudo yum install postfix
sudo systemctl enable postfix
sudo systemctl start postfix
```
```shell
# 安装gitlab安装包
# 来源：https://blog.csdn.net/misxu890312/article/details/85880229
rpm -i  gitlab-ee-11.6.2-ee.0.el7.x86_64.rpm
```
```shell
# 配置文件
# 来源：https://blog.csdn.net/misxu890312/article/details/85880229
vi /etc/gitlab/gitlab.rb
# 将external_url "http://gitlab.example.com" 修改为指定的地址
# 如external_url "http://192.168.1.100"
# 让配置生效
sudo gitlab-ctl reconfigure
# 重新配置过程较长，等待中...
# 直到看到如下信息，说明配置成功
Running handlers:
Running handlers complete
Chef Client finished, 457/679 resources updated in 10 minutes 25 seconds
gitlab Reconfigured!
```
```shell
# gitlab服务的基本命令
# 启动所有组件
# Start all GitLab components
sudo gitlab-ctl start
# 停止所有组件
# Stop all GitLab components
sudo gitlab-ctl stop
# 重启所有组件
# Restart all GitLab components
sudo gitlab-ctl restart
```
4. 访问gitlab
浏览器输入修改好的external_url地址即可
在`/etc/gitlab/gitlab.rb`服务输入域名`external_url="http://gitlab.xxxx.com"`
在客户端绑定hosts`192.168.1.100 gitlab.xxxx.com`

## 升级

1. 下载高版本gitlab，清华大学开源镜像源https://mirrors.tuna.tsinghua.edu.cn/gitlab-ee/yum/el7/

2. 升级gitlab

   ```shell
   # 执行升级命令
   # 在执行过程中，会升级postgresql，最好开着gitlab服务升级
   rpm -Uvh gitlab-ee-12.0.6-ee.0.el7.x86_64.rpm
   # 执行完成后
   sudo gitlab-ctl reconfigure
   sudo gitlab-ctl restart
   ```

   

## 常见问题

首次访问出现502页面

- 可能是启动完成后，后台服务还在运行中，执行`top`命令，待服务cpu平稳后再次访问。
- 可能是执行启动过程中出现错误，执行`sudo gitlab-ctl status`查看各个服务是否正常启动，如果某个服务有问题，进入相对于的日志`/var/log/gitlab/服务名/current`查看问题，解决后即可正常启动。