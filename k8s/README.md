# yum安装kubernetes

## 1.关闭防火墙

```shell
#关闭selinux
setenforce 0
#关闭firewalld防火墙
systemctl stop firewalld
systemctl disable firewalld
```

## 2.安转ntp同步时间

```sh
yum -y install ntp
ntpdate pool.ntp.org
systemctl start ntpd
systemctl enable ntpd
```

## 3.Kubernetes Master安装与配置

```sh
#安装kubernetes-master，etcd，flannel
yum install kubernetes-master etcd flannel -y
```

----

- 修改/etc/etcd/etcd.conf配置文件的ip地址为master地址

```

```

