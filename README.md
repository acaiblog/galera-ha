>### 部署前准备

1.配置yum源
```
wget http://mirrors.aliyun.com/repo/Centos-7.repo /etc/yum.repos.d/
wget http://mirrors.aliyun.com/repo/Centos-7.repo /etc/yum.repos.d/
```
```
cat >/etc/yum.repos.d/mariadb.repo <<EOF
[mariadb]
name=mariadb
baseurl=https://mirrors.tuna.tsinghua.edu.cn/mariadb//mariadb-10.3.11/yum/centos73-amd64/
gpgcheck=0
enabled=1
EOF
```
2.安装ansible
```
yum install ansible
```
3.下载playbook到本地
```
git clone https://github.com/acaiblog/galera-ha.git
```
4.修改`group_vars/all`和`inventory/hosts `配置

5.部署mariadb galera HA集群
```
ansible-playbook -i inventory/hosts deploy.yml
```
