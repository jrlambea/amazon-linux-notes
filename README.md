# amazon-linux-notes

Amazon Linux 2022 notes

## Install Java Coretto 11

```bash
sudo yum install java-11-amazon-corretto-headless
```

Verify:

```bash
sudo alternatives --config java
```

## Install MySQL 8

```bash
sudo yum install openssl-devel
sudo yum localinstall http://dev.mysql.com/get/mysql80-community-release-el9-1.noarch.rpm
sudo yum install mysql-community-server

sudo systemctl enable mysqld
sudo systemctl start  mysqld

sudo cat /var/log/mysqld.log | grep root
```

## SWAP

https://repost.aws/es/knowledge-center/ec2-memory-swap-file

```bash
sudo dd if=/dev/zero of=/swapfile bs=128M count=32
sudo chmod 600 /swap/swapfile
sudo mkswap /swap/swapfile
sudo swapon /swap/swapfile
```
