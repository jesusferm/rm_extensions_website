# rm_extensions_website

##### Este proyecto es una manera simple ocultar las extenciones en la barra de direcciones, es decir, en lugar de mostrar index.php ==> index

##### Entonces, al ocultar estas extensiones, en el código, se debe utilizar sin extensión también.


Para lograra esto, se modifca o se gregan el archivo .htaccess en el hosting que se utilize. Para este ejemplo se utilizó XAMPP 7.1.9, en Fedora 26.

El código siguiente debe ir entre las etiquetas <b>IfModule mod_rewrite.c</b> y <b>IfModule</b>, del archivo htaccess.

<pre>
RewriteEngine on

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME}.php -f
RewriteRule ^(.*)$ $1.php

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME}.html -f
RewriteRule ^(.*)$ $1.html
</pre>