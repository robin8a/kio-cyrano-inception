# Starting React App

- https://dev.to/awscommunity-asean/create-and-deploy-python-django-application-in-aws-ec2-instance-4hbm
- https://pythoncircle.com/post/697/hosting-django-app-for-free-on-amazon-aws-ec2-with-gunicorn-and-nginx/
- https://stackoverflow.com/questions/34731832/log-in-to-github-from-the-command-line-with-multiple-accounts
- https://dev.to/cindyledev/remote-development-with-visual-studio-code-on-aws-ec2-4cla
- https://www.digitalocean.com/community/tutorials/how-to-create-django-models

```sh
npx create-react-app kio-cyrano-rjs-app
gunicorn --workers 3 --bind 0.0.0.0:8000 cyrano.wsgi:application

sudo nano /etc/nginx/sites-available/cryano
```


```js
server {
    listen 80;
    server_name 184.73.137.238;

    # to avoid any error while fetching fevicon
    location = /favicon.ico { access_log off; log_not_found off; }

    location /static/ {
        root /home/ubuntu/cyrano;
    }

    location / {
        include proxy_params;
        # communicate via socket file created by Gunicorn
        proxy_pass http://unix:/home/ubuntu/cyrano/cyrano.sock;
    }
}
```

```sh

sudo ln -s /etc/nginx/sites-available/cyrano /etc/nginx/sites-enabled


gunicorn --workers 3 --bind unix:/home/ubuntu/cyrano/cyrano.sock cyrano.wsgi:application
```