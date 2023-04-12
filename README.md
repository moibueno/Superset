# Superset

### Update SO
```bash
sudo apt update -y && sudo apt upgrade -y
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
sudo apt-get install build-essential libssl-dev libffi-dev python3-dev python3-pip libsasl2-dev libldap2-dev default-libmysqlclient-dev libpq-dev -y
```
```sh
sudo apt install netplan.io -y
```
```sh
pip install --upgrade pip
```
```sh
pip install -U pyopenssl
```
```sh
pip install Flask psycopg2
```
## Instala Superset
```sh
pip install apache-superset
```
```sh
vi ~/.bashrc
```
```sh
export FLASK_APP=superset
export SUPERSET_SECRET_KEY="BYnGB/xrhU9jhOzFvOP6dqdue10ycBo6+jXe748bgwyuQp7fNg8ySLbH"
export PATH=$PATH:/home/moibueno/.local/bin
export PYTHONPATH=/home/moibueno/.local/lib/python3.8/site-packages/superset
```
```sh
cd /home/moibueno/.local/lib/python3.8/site-packages/superset
```
```sh
vi /home/moibueno/.local/lib/python3.8/site-packages/superset/superset_config.py
```
```sh
python3 config.py
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
SECRET_KEY = 'BYnGB/xrhU9jhOzFvOP6dqdue10ycBo6+jXe748bgwyuQp7fNg8ySLbH'

# The SQLAlchemy connection string to your database backend
# This connection defines the path to the database that stores your
# superset metadata (slices, connections, tables, dashboards, ...).
# Note that the connection information to connect to the datasources
# you want to explore are managed directly in the web UI
#SQLALCHEMY_DATABASE_URI = 'sqlite:////opt/superset/superset.db'
SQLALCHEMY_DATABASE_URI = 'postgresql://superset:c4rv4lh0@192.168.0.192/superset'

COMPRESS_REGISTER = False

# Flask-WTF flag for CSRF
WTF_CSRF_ENABLED = True
# Add endpoints that need to be exempt from CSRF protection
WTF_CSRF_EXEMPT_LIST = []
# A CSRF token that expires in 1 year
WTF_CSRF_TIME_LIMIT = 60 * 60 * 24 * 365

# Set this API key to enable Mapbox visualizations
MAPBOX_API_KEY = ''
```
```sh
cd /home/moibueno/.local/lib/python3.8/site-packages
```
```sh
superset db upgrade
```

```sh
superset fab create-admin
```
```sh
superset load_examples
```

```sh
superset init
```

```sh
superset run -h 0.0.0.0 -p 8088 --with-threads --reload  
```
```sh
sudo su
cat << EOF > /etc/systemd/system/superset.service 
[Unit]
Description = Apache Superset Webserver Daemon
After = network.target

[Service]
PIDFile = /home/moibueno/superset-webserver.PIDFile
User = moibueno
Group = moibueno
Environment=SUPERSET_HOME=/home/moibueno/.local/bin
Environment=PYTHONPATH=/home/moibueno/.local/lib/python3.8/site-packages/superset
Environment=FLASK_APP=superset
WorkingDirectory = /home/moibueno
ExecStart =/home/moibueno/.local/bin/superset run -p 8088 -h  0.0.0.0 --with-threads
ExecStop = /bin/kill -s TERM $MAINPID

[Install]
WantedBy=multi-user.target
EOF
```
```sh
sudo systemctl start superset
sudo systemctl enable superset
```




https://musaamin.web.id/install-superset-data-visualization-ubuntu/  
https://superset.apache.org/docs/installation/installing-superset-from-scratch/
