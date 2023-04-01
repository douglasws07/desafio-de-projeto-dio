# desafio-de-projeto-dio
#!/bin/bash

echo 'criando diretorios'

mkdir /publico
mkdir /adm
mkdir /ven
mkdir /sec

echo 'criando grupos'

groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC

echo 'criando usuarios'

useradd carlos -m -s /bin/bash -p $(openssl passwd senha123) -G GRP_ADM
useradd maria -m -s /bin/bash -p $(openssl passwd senha123) -G GRP_ADM
useradd joao -m -s /bin/bash -p $(openssl passwd senha123) -G GRP_ADM

useradd debora -m -s /bin/bash -p $(openssl passwd senha123) -G GRP_VEN
useradd roberta -m -s /bin/bash -p $(openssl passwd senha123) -G GRP_VEN
useradd camila -m -s /bin/bash -p $(openssl passwd senha123) -G GRP_VEN

useradd diego -m -s /bin/bash -p $(openssl passwd senha123) -G GRP_SEC
useradd matheus -m -s /bin/bash -p $(openssl passwd senha123) -G GRP_SEC
useradd lucas -m -s /bin/bash -p $(openssl passwd senha123) -G GRP_SEC


echo 'especificando permissões dos diretorios'

chown root:GRP_ADM /adm
chown root:GRP_VEN /ven
chown root:GRP_SEC /sec

chmod 770 /adm
chmod 770 /ven
chmod 770 /sec
chmod 777 /publico

echo 'fim'
