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

# Creamos una carpeta para subir los addons
```linux
mkdir /etc/extra-addons
chown odoo: /etc/extra-addons -R
```
# Descargamos y Subimos al servidor el addons con rsync
```linux
rsync --info=progress2 rowno_in_tree.zip  root@192.81.217.46:/etc/extra-addons/rowno_in_tree.zip
cd /etc/extra-addons/
apt-get install unzip
unzip rowno_in_tree.zip
rm rowno_in_tree.zip
```

# Abrimos el Archivo de configuracion
```linux
addons_path = /usr/lib/python3/dist-packages/odoo/addons,/etc/extra-addons
logrotate = True
```

# Reiniciamos Odoo
```linux
aservice odoo restart
```
