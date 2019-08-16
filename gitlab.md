1. 安装Centos7
2. 下载gitlab，清华大学开源镜像源https://mirrors.tuna.tsinghua.edu.cn/gitlab-ee/yum/el7/
3. 安装gitlab
```
# 安装依赖项 
# 来源：https://blog.csdn.net/misxu890312/article/details/85880229
sudo yum install -y curl policycoreutils-python openssh-server
sudo systemctl enable sshd
sudo systemctl start sshd
sudo firewall-cmd --permanent --add-service=http
sudo systemctl reload firewalld
```
```
# 安装Postfix以发送通知电子邮件
# 来源：https://blog.csdn.net/misxu890312/article/details/85880229
sudo yum install postfix
sudo systemctl enable postfix
sudo systemctl start postfix
```
```
# 安装gitlab安装包
# 来源：https://blog.csdn.net/misxu890312/article/details/85880229
rpm -i  gitlab-ee-11.6.2-ee.0.el7.x86_64.rpm
```
```
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
```
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
```
浏览器输入修改好的external_url地址即可
```
