# angular2-apache2-htaccess
.htaccess with Enabled mod_rewrite setting for deploy ng2 app on apache2

1. Installed dependencies using npm install.
2. Used ng build --prod command and it created a dist directory.
3. Move dist/* to public dir
4. Enabled mod_rewrite, restarted apache and added this .htaccess in my dist directory.
```
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteBase /
    RewriteRule ^index\.html$ - [L]
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule . /index.html [L]
</IfModule>
```
5. Set/Check ```<base href="/demo/dist/">``` Base Path
