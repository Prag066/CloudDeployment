# CloudDeployment
for deployment on cloud

sudo ufw allow 8000

gunicorn --bind 0.0.0.0:8000 myproject.wsgi

sudo systemctl start gunicorn.socket
sudo systemctl enable gunicorn.socket

sudo systemctl daemon-reload
sudo systemctl restart gunicorn



sudo ln -s /etc/nginx/sites-available/project /etc/nginx/sites-enabled/

sudo nginx -t
sudo systemctl restart nginx

sudo ufw delete allow 8000
sudo ufw allow 'Nginx Full'
