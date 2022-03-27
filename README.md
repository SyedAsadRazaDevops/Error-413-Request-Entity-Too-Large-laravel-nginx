# Error 413-Request-Entity-Too-Large-laravel-nginx
**laravel when i posted data to server i get this error 413 Request Entity Too Large.**
![413](https://user-images.githubusercontent.com/71556060/160275841-f7476ecf-4b10-43b5-921f-984d7b6b762f.png)


# try these solutions as bellow:

**1- set client_max_body_size 100M; in server and location and http in nginx.conf**

Add ‘client_max_body_size xxM’ inside the http section in **/etc/nginx/nginx.conf**,
where xx is the size (in megabytes) that you want to allow.
```
http {
      client_max_body_size 20M;         
}
```

**2- set upload_max_filesize = 100M in php.ini**

Add ‘set upload_max_filesize xxM’ inside the http section in **/etc/php/7.4/fpm/php.ini**,
where xx is the size (in megabytes) that you want to allow.

>press ctrl+W to search in nano terminal 
```
      set upload_max_filesize = 100M;         
```

**3- set post_max_size = 100M in php.ini**

Add ‘set post_max_size = xxM’ inside the http section in **/etc/php/7.4/fpm/php.ini**,
where xx is the size (in megabytes) that you want to allow.

>press ctrl+W to search in nano terminal 
```
set post_max_size = 100M;
```
>Then, you need to restart ngnix 
```
sudo service nginx restart 
```
**This change did not reflect the domain or endpoint because PHP-fame still need to restart the service**, run:
```
service php7.4-fpm restart
```
I'm using 7.4, you can customize the version as per you need.

# **To avoid these thin in features make phpinfo file:**

1- Navigate to File Manager under the Files section in your hPanel.

2- Once you’re in public_html directory, click the New File button.

3- Name your file phpinfo.php and press Create.

4- Scroll down and locate the new phpinfo file within the directory, then right-click to Edit.

5- Now, copy and paste the following code into the text editor and press Save.
```
 <?php
phpinfo(); ?>
```

You should have a phpinfo.php file in your public_html directory by now. So, all that’s left is to access the file by adding /phpinfo.php at the end of your domain name.
>in laravel project make it in public folder,where the nginx root path is defined.

```
www.mydomain.com/phpinfo.php
```
