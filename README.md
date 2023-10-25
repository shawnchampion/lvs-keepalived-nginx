lvs+keepalived+nginx 实现负载均衡  
  
参考文章  
https://blog.csdn.net/lupengfei1009/article/details/86514445  
  
RPM包准备
```
repotrack gcc gcc-c++ openssl openssl-devel libnl libnl-devel libnfnetlink-devel net-tools vim wget ipvsadm zlib zlib-devel pcre pcre-devel iptables-services initscripts
```
  
RPM包安装
```
cd packages
rpm -ivh *.rpm --force --nodeps
```
  
keepalived安装
```
tar -xzvf keepalived-2.0.10.tar.gz 
mv keepalived-2.0.10 /usr/local/keepalived
cd /usr/local/keepalived/
./configure
make && make install
mkdir /etc/keepalived
cp keepalived/etc/keepalived/keepalived.conf /etc/keepalived/
cp keepalived/etc/init.d/keepalived /etc/rc.d/init.d/
cp keepalived/etc/sysconfig/keepalived /etc/sysconfig/
cp ../sbin/keepalived /usr/sbin/
/etc/init.d/keepalived start
```