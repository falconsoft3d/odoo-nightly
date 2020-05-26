# Instalando Odoo 11

```linux
wget -O - https://nightly.odoo.com/odoo.key | apt-key add -
echo "deb http://nightly.odoo.com/11.0/nightly/deb/ ./" >> /etc/apt/sources.list
apt-get update && apt-get install odoo
```

# Archivo de configuracion
```linux
nano /etc/odoo/odoo.conf
```
# Donde estan los addons de Odoo
```linux
/usr/lib/python3/dist-packages/odoo/addons
```
# Instalando nuevas apps
```linux
mkdir /etc/extra-addons
chown odoo: /etc/extra-addons -R
```
