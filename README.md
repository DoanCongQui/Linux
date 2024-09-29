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
