# CloudDeployment
for deployment on cloud

sudo ufw allow 8000

gunicorn --bind 0.0.0.0:8000 project.wsgi

sudo systemctl start gunicorn.socket
sudo systemctl enable gunicorn.socket


sudo ln -s /etc/nginx/sites-available/project /etc/nginx/sites-enabled/


sudo systemctl restart nginx