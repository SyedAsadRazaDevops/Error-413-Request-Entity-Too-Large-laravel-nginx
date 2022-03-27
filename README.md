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
