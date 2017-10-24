# Udacity Linux Server Configuration Project
## Chris Dunleavy
### Host Name: ec2-34-212-234-169.us-west-2.compute.amazonaws.com
### IP: 34.212.234.169
### SSH Port: 2200
Log in to the server as grader with 
>ssh grader@34.212.234.169 -p 2200 -i ~/.ssh/linuxCourse
### Installed Software
##### Software installed on Ubuntu server:
- apache2
- mod_wsgi
- ntp
- postgresql
- python-dev
- python-pip
- virtualenv

##### Software installed in virtual environment:
- Flask
- requests
- httplib2
- oauth2client
- sqlalchemy
- Flask-SQLAlchemy
- psycopg2

## Configurations:
- changed port from 22 to 2200 in sshd_config
- Created Linux user "grader" with password "grader"
- Gave sudo access to "grader" by creating a grader file in /etc/sudoers.d
- Created ssh key pair with password "linuxCourse" and installed public key on server using /home/grader/.ssh/authorized_keys file
- chmod 700 .ssh
- chmod 644 .ssh/authorized_keys
- Firewall configurations: deny incoming, allow incoming, allow ssh, allow 2200/tcp, allow www
- Configure time zone using ntp
- create linux user "catalog" with password "catalog"
- create postgresql role "catalog" and database "catalog"
- create virtual environment for application, chmod -R 777 venv
- export PATH=/usr/share/nano/postgresql/.nanorc:"$PATH"
- created BoardGames.conf apache configuration file
- created BoardGames.wsgi
- Edited python files to connect to the new postgres database as the catalog user
- Updated client secret files for Google and Facebook login with current ip address
- Added current Javascript origins and authorized redirect URI's to Google and Facebook's web app pages

## Resources
- [DigitalOcean: How To Secure PostgreSQL on an Ubuntu VPS](https://www.digitalocean.com/community/tutorials/how-to-secure-postgresql-on-an-ubuntu-vps)
- [DigitalOcean: How To Deploy a Flask Application on an Ubuntu VPS](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps)
- [Udacity forums: Project 5 Resources](https://discussions.udacity.com/t/project-5-resources/28343)
- [Udacity forums: Facebook Auth Not Redirecting](https://discussions.udacity.com/t/facebook-auth-not-redirecting/39772/4)
- [Udacity forums: Tips for configuring Postgresql and Setting up Item catalog project](https://discussions.udacity.com/t/tips-for-configuring-postgresql-and-setting-up-item-catalog-project/223436)
- [Udacity forums: Deploying Item Catalog Project](https://discussions.udacity.com/t/deploying-item-catalog-project/227189)
- [Time Synchronisation with NTP](https://help.ubuntu.com/lts/serverguide/NTP.html)
- [Dillinger.io: Free online markdown tool](dillinger.io)
