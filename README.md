# NGINX

---

NGINX is a free, open-source software that can be used for a variety of purposes, including:

- Web server: NGINX is a web server that can deliver content quickly, reliably, and securely.
- Load balancer: NGINX can be used as a load balancer for HTTP, TCP, and UDP servers.
- Reverse proxy: NGINX can be used as a reverse proxy for HTTP, TCP, and UDP servers.
- Content cache: NGINX can be used as a content cache.
- API gateway: NGINX can be used as an API gateway.

Email proxy: NGINX can be used as a proxy server for email communications protocols, such as IMAP, POP3, and SMTP.

- Email proxy: NGINX can be used as a proxy server for email communications protocols, such as IMAP, POP3, and SMTP.

# Documentation

---

# Installation

---

Install via nginx

```jsx
sudo apt-get install nginx
```

nginx is now running on Port 80. 

Go to your root folder and open it in terminal in mac or command prompt on windows and run a few commands. 

```jsx
sudo vi /etc/nginx/nginx.conf
```

To delete the existing file in nginx.conf

```jsx
sudo rm /etc/nginx/nginx.conf
```

reopen the nginx.conf 

```jsx
sudo vi /etc/nginx/nginx.conf
```

```jsx
events {
    worker_connections 1024;
}

http {
    server {
        listen 80;
        server_name todo-app-backend.100xdevs.com;

        location / {
            proxy_pass http://localhost:3000;
            proxy_http_version 1.1;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection 'upgrade';
            proxy_set_header Host $host;
            proxy_cache_bypass $http_upgrade;
        }
    }
}
```
Then, restart the server again 

```jsx
sudo nginx -s reload
```
