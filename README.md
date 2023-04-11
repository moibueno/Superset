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
```sh
echo "export FLASK_APP=superset" >> ~/.bashrc
vi /etc/profile
```

```sh
cd /usr/local/lib/python3.8/dist-packages/superset
```
```sh
sudo mkdir /opt/superset
sudo chown 
openssl rand -base64 42
```
```sh
sudo vi /usr/local/lib/python3.8/dist-packages/superset/superset_config.py
```
## Setup Superset

```sh
# Superset specific config
ROW_LIMIT = 5000

SUPERSET_WEBSERVER_PORT = 8088

# Flask App Builder configuration
# Your App secret key will be used for securely signing the session cookie
# and encrypting sensitive information on the database
# Make sure you are changing this key for your deployment with a strong key.
# You can generate a strong key using `openssl rand -base64 42`.
# Alternatively you can set it with `SUPERSET_SECRET_KEY` environment variable.
SECRET_KEY = 'YOUR_OWN_RANDOM_GENERATED_SECRET_KEY'

# The SQLAlchemy connection string to your database backend
# This connection defines the path to the database that stores your
# superset metadata (slices, connections, tables, dashboards, ...).
# Note that the connection information to connect to the datasources
# you want to explore are managed directly in the web UI
SQLALCHEMY_DATABASE_URI = 'sqlite:////opt/superset/superset.db'

# Flask-WTF flag for CSRF
WTF_CSRF_ENABLED = True
# Add endpoints that need to be exempt from CSRF protection
WTF_CSRF_EXEMPT_LIST = []
# A CSRF token that expires in 1 year
WTF_CSRF_TIME_LIMIT = 60 * 60 * 24 * 365

# Set this API key to enable Mapbox visualizations
MAPBOX_API_KEY = ''```sh
```

```sh
export SUPERSET_SECRET_KEY="BYnGB/xrhU9jhOzFvOP6dqdue10ycBo6+jXe748bgwyuQp7fNg8ySLbH"
```

```sh
sudo superset db upgrade
```

```sh
sudo superset fab create-admin
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
