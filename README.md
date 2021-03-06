## Virtual host configuration
```
cd /etc/apache2/vhosts

<sudo> vi <domain>.conf

<VirtualHost *:80>
        DocumentRoot "/Users/<username>/Sites/<domain.name>/htdocs"
        ServerName local.<domain.name>
        ErrorLog "/private/var/log/apache2/local.<domain.name>-error_log"
        CustomLog "/private/var/log/apache2/local.<domain.name>-access_log" common

        <Directory "/Users/<username>/Sites/<domain.name>/htdocs">
            AllowOverride All
            Require all granted
        </Directory>
</VirtualHost>

<sudo> apachectl restart
```

## Mapping the virtual domain extension

```
vi /etc/hosts

127.0.0.1       <domain.name>

dscacheutil -flushcache

```
## A note about permissions

```
chmod 755 some/web/directory/

```
