# vestacp-nextcloud-template
Web templates for Vesta Control Panel to run Nextcloud or Owncloud under Apache. Works with nginx proxy too. 

Download these files into /usr/local/vesta/data/templates/web/apache2 eg. 
```
cd /usr/local/vesta/data/templates/web/apache2
wget https://raw.githubusercontent.com/plutocrat/vestacp-nextcloud-template/master/nextcloud.tpl
wget https://raw.githubusercontent.com/plutocrat/vestacp-nextcloud-template/master/nextcloud.stpl
```

Then select them from the Control Panel > Domains > Domainname.com > Templates

Make sure to enable the Apache headers module using `a2enmod headers` or else Apache will not start.

If you have enabled SSL, then also put this in your .htaccess file, which will force an SSL connection. 

```
   <IfModule mod_rewrite.c>
         RewriteEngine On
       RewriteCond %{HTTPS} !=on
       RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [R=301,L]
    </IfModule>
```
