# Docker安装Jenkins
## 1.安装docker
```shell
curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun
```
## 2.拉取Jenkins镜像
```shell
docker pull jenkins/jenkins:lts
```
## 3. 启动Jenkins容器
```shell
mkdier -p /date/jenkins
chown -R 1000.1000 /date/jenkins
docker run -d -p 8080:8080 -p 50000:50000 -v /date/jenkins:/var/jenkins_home/ --name jenkins --privileged=true jenkins/jenkins:lts
```
## 4.查看Jenkins初始密码
```shell
cat /date/jenkins/secrets/initialAdminPassword
```
## 5.修改Jenkins的国内源
```shell
sed -i 's/http:\/\/updates.jenkins-ci.org\/download/https:\/\/mirrors.tuna.tsinghua.edu.cn\/jenkins/g' /date/jenkins/updates/default.json
sed -i 's/http:\/\/www.google.com/https:\/\/www.baidu.com/g' /date/jenkins/updates/default.json
```
