oracle���������ټܹ�����������������ص�ҵ��
���ú�oracle�ķ������ƣ�
���ú�oracle��dblink���ƺ�ν����ƣ�

1.�ӹ����������°��oracle12c;
2.ִ��install_oracle����Ĭ�ϰ�װ������
3.���.bash_profile������������ļ��Ƿ�һ�£�
4.���ա�oracle�ľ�Ĭ��װ.txt���Ĳ�����о�Ĭ��װ,���Ҵ������ݿ�ͽ������ݿ��û���
https://fastweb-mobile.googlecode.com/svn/trunk/05.common-tools/oracle-install/


mkdir /home/data/
chown oracle:oinstall /home/data/    

./runInstaller oracle.install.option=INSTALL_DB_SWONLY \
    ORACLE_BASE=/home/data/oracle/product/base \
    ORACLE_HOME=/home/data/oracle/product/base/12.1.0.1 \
    UNIX_GROUP_NAME=oinstall \
    oracle.install.db.DBA_GROUP=dba \
    oracle.install.db.OPER_GROUP=oper \
    oracle.install.db.BACKUPDBA_GROUP=dba \
    oracle.install.db.DGDBA_GROUP=dba \
    oracle.install.db.KMDBA_GROUP=dba \
    oracle.install.db.config.starterdb.characterSet=AL32UTF8 \
    oracle.install.db.config.starterdb.memoryOption=true \
    FROM_LOCATION=../stage/products.xml \
    INVENTORY_LOCATION=/home/data/oracle/oraIventory \
    SELECTED_LANGUAGES=en,zh_CN \
    oracle.install.db.InstallEdition=EE \
    DECLINE_SECURITY_UPDATES=true  -silent -ignoreSysPrereqs -ignorePrereq -waitForCompletion
 
 
    sed -n '/^[^#]/p' response/netca.rsp


        1. /home/data/oracle/oraIventory/orainstRoot.sh
        2. /home/data/oracle/product/base/12.1.0.1/root.sh
��װ����
netca -silent -responseFile /home/oracle/database/response/netca.rsp  
��װʵ�����ݿ�
dbca -silent -createDatabase -responseFile /home/oracle/database/response/dbca.rsp 
sys/sys  system/system

ȫ�����ݿ���:orcl12c.us.oracle.com
ϵͳ��ʶ�� (SID):orcl12c


lsnrctl status
 


