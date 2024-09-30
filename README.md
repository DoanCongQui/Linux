# Fix update Centos7
Mở terminal vào quyền root sau đó nhập lệnh `vim /etc/yum.repos.d/CentOS-Base.repo` chọn tất cả và thay thế bằng dòng sau và lưu lại 
```
[base]
name=CentOS-$releasever - Base
baseurl=http://vault.centos.org/7.9.2009/os/$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7

[updates]
name=CentOS-$releasever - Updates
baseurl=http://vault.centos.org/7.9.2009/updates/$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7

[extras]
name=CentOS-$releasever - Extras
baseurl=http://vault.centos.org/7.9.2009/extras/$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
```
Sau đó chạy lệnh 
```
yum clear all
yum update 
```
# V Remote Telnet
Sau khi download telnet và xinetd chạy lần lược 2 lệnh này
```
sudo systemctl start xinetd
sudo systemctl status telnet.socket 
```
```
firewall-cmd --add-service=telnet --zone=public --permanent
firewall-cmd --reload
```

# VI Remote control Desktop
```
sudo yum install epel-release
```
```
sudo yum install xrdp tigervnc-server
```
```
sudo systemctl start xrdp.service
sudo systemctl enable xrdp.service
```
```
sudo firewall-cmd --permanent --add-port=3389/tcp
sudo firewall-cmd --reload
```

# VII Remote SSH
```
sudo systemctl start sshd
sudo systemctl status sshd
```
