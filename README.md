����gpssh-exkeys
��greenplum-db-4.3.8.2-build-1-RHEL5-x86_64 �����һ�����
Exchanges SSH public keys between hosts
https://github.com/apache/incubator-hawq/blob/master/tools/bin/gpssh-exkeys

http://hdb.docs.pivotal.io/130/docs-hawq/docs-hawq-shared/utility_guide/admin_utilities/gpssh-exkeys.html

�°汾��hawq ssh-exkeys
http://hdb.docs.pivotal.io/211/hawq/reference/cli/admin_utilities/hawqssh-exkeys.html



���ܣ�������֮���໥����


1��װ
./greenplum-db-4.3.8.2-build-1-RHEL5-x86_64.bin 

һ·Ĭ�ϣ�yes

·���� /usr/local/greenplum-db-4.3.8.2

##########
���߸����Ѿ���װ�õģ��Լ�������ȡ�����������
tar -xvf gpssh-exkeys-v2.tar -C /usr/local/

chmod -R 777 /usr/local/greenplum-db-4.3.8.2/
#############

2Ȼ��ִ��
source /usr/local/greenplum-db-4.3.8.2/greenplum_path.sh

3 ���ú����л�����
vi /etc/hosts
���� 
192.168.184.73  test73
192.168.184.74  test74

4 �ڰ�װ��greenplum-db�Ļ����ϣ�����һ���ļ�,ֻҪд������ ������
���� vi /tmp/hosts_all
test73
test74

5 ssh����
gpssh-exkeys --version

 gpssh-exkeys -f /tmp/hosts_all

6 ж��
 rm -rf /usr/local/greenplum-db-4.3.8.2