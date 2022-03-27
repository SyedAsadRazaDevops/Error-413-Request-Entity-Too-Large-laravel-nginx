# Error 413-Request-Entity-Too-Large-laravel-nginx
**laravel when i posted data to server i get this error 413 Request Entity Too Large.**
![413](https://user-images.githubusercontent.com/71556060/160275841-f7476ecf-4b10-43b5-921f-984d7b6b762f.png)


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
