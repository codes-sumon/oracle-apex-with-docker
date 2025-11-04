# oracle-apex-with-docker
docker login container-registry.oracle.com
docker-compose up -d
docker exec -it oracle19c bash
docker cp "E:\OracleApex\oracle-apex19c\apex_24.1.zip" oracle19c:/home/oracle/
cd /home/oracle
unzip apex_24.1.zip
cd apex


sqlplus / as sysdba

alter session set container=ORCLPDB1;
@apexins.sql SYSAUX SYSAUX TEMP /i/
@apxchpwd.sql
@apex_rest_config.sql


--Static path config
ords --config /etc/ords/config config set standalone.static.path /ords/apex/images
