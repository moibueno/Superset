# Superset

### Update SO
```bash
sudo apt update -y && sudo apt upgrade -y
```
```bash
wget https://download.nus.edu.sg/mirror/ubuntu/ubuntu/pool/main/n/netplan.io/netplan.io_0.99-0ubuntu1_amd64.deb
```

### Set timezone
```sh
sudo timedatectl set-timezone America/Sao_Paulo
```
### Instala dependências
```sh
sudo apt remove python3.8 python3.9 -y
```
```sh
sudo apt-get install build-essential libssl-dev libffi-dev python3-dev python3-pip libsasl2-dev libldap2-dev default-libmysqlclient-dev -y
```
```sh
sudo apt install netplan.io -y
```
```sh
pip install --upgrade pip
```
```sh
sudo rm -rf /usr/lib/python3/dist-packages/OpenSSL
```
```sh
sudo pip install -U pyopenssl
```
```sh
sudo pip install Flask
```
## Instala Superset
```sh
sudo pip install apache-superset
```

```sh
echo "export FLASK_APP=superset" >> ~/.bashrc
```
```sh
sudo su
echo "export FLASK_APP=superset" >> /etc/profile
exit
```

echo "export FLASK_APP=superset" >> ~/.bashrc
vi /etc/profile
```
export FLASK_APP=superset

```sh
sudo superset fab create-admin
```



## Setup Superset
```sh
sudo superset db upgrade
```




```sh

```

```sh

```

```sh

```

```sh

```

```sh

```

```sh

```

https://musaamin.web.id/install-superset-data-visualization-ubuntu/
https://superset.apache.org/docs/installation/installing-superset-from-scratch/
