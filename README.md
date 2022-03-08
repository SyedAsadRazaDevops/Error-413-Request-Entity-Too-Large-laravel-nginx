# Error-413-Request-Entity-Too-Large-laravel-nginx
laravel when i posted data to server i get this error 413 Request Entity Too Large.

# solution are in nginx.config file

Add ‘client_max_body_size xxM’ inside the http section in **/etc/nginx/nginx.conf**,
where xx is the size (in megabytes) that you want to allow.
```
http {
      client_max_body_size 20M;         
}
```
>I think you need to restart ngnix 
```
sudo service nginx restart 
```
