# Reverse Proxy
> A reverse proxy is a server that sits in front of web servers and forwards client (e.g. web browser) requests to those web servers. Reverse proxies are typically implemented to help increase security, performance, and reliability. 

To start hosting web pages from the Pi you have to have the server their content on port `80` for `http` or port `443` for `https`. This works fine if you just have a single webpage but because an issue if you want to host multiple pages. We user a reverse proxy to sit on port 80 and requests to the local ports. To do this we are going to use NGINX


## Install NGINX

First install the nginx package by typing the following command in to the Terminal:

```sh
sudo apt install nginx
```

and start the server with:

```sh
sudo /etc/init.d/nginx start
```

By default, NGINX puts a test HTML file in the web folder. This default web page is served when you browse to `http://localhost/`. Navigate there now to see the landing page
