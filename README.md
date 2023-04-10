# Superset

### Update SO
```bash
sudo apt update -y && sudo apt upgrade -y
```

### Set timezone
```sh
sudo timedatectl set-timezone America/Sao_Paulo
```

sudo apt-get remove python


### Instala dependências
```sh
sudo apt remove python3.8 python3.9
sudo apt-get install build-essential libssl-dev libffi-dev python3-dev python3-pip libsasl2-dev libldap2-dev default-libmysqlclient-dev -y
pip install --upgrade pip
sudo rm -rf /usr/lib/python3/dist-packages/OpenSSL
sudo pip install -U pyopenssl
sudo pip install Flask
```
## Instala Superset
```sh
sudo pip install apache-superset
```

```sh
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
