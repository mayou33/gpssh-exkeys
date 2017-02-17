神器gpssh-exkeys
是greenplum-db-4.3.8.2-build-1-RHEL5-x86_64 里面的一个命令。

Exchanges SSH public keys between hosts
https://github.com/apache/incubator-hawq/blob/master/tools/bin/gpssh-exkeys

http://hdb.docs.pivotal.io/130/docs-hawq/docs-hawq-shared/utility_guide/admin_utilities/gpssh-exkeys.html

新版本是hawq ssh-exkeys
http://hdb.docs.pivotal.io/211/hawq/reference/cli/admin_utilities/hawqssh-exkeys.html



功能：许多机器之间相互互信


1安装
./greenplum-db-4.3.8.2-build-1-RHEL5-x86_64.bin 

一路默认，yes

路径在 /usr/local/greenplum-db-4.3.8.2

##########
或者复制已经安装好的，自己单独提取命令，做个简洁版
tar -xvf gpssh-exkeys-v2.tar -C /usr/local/

chmod -R 777 /usr/local/greenplum-db-4.3.8.2/
#############

2然后执行
source /usr/local/greenplum-db-4.3.8.2/greenplum_path.sh

3 配置好所有机器的
vi /etc/hosts
比如 
192.168.184.73  test73
192.168.184.74  test74

4 在安装了greenplum-db的机器上，新增一个文件,只要写主机名 就行了
比如 vi /tmp/hosts_all
test73
test74

5 ssh互信
gpssh-exkeys --version

 gpssh-exkeys -f /tmp/hosts_all

6 卸载
 rm -rf /usr/local/greenplum-db-4.3.8.2
