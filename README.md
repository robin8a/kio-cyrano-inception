- https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install-advanced.html
- https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/ruby-development-environment.html#ruby-development-environment-ruby
- https://www.engineyard.com/blog/running-rails-in-aws-elastic-beanstalk-tutorial/
- https://mouhadiouf.medium.com/how-to-use-ruby-on-rails-on-aws-cloud-9-daed898c71d1
- https://youtu.be/YJzYmhxB8rE
- https://rvm.io/rvm/basics
- https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb3-cmd-commands.html
- https://www.atomic14.com/2017/05/01/deploying-a-rails-app-to-elastic-beanstalk.html
- https://www.youtube.com/watch?v=b-eGC3uCHxI
- https://medium.com/@manishyadavv/how-to-deploy-ruby-on-rails-apps-on-aws-ec2-7ce55bb955fa
- https://aws.amazon.com/ec2/pricing/on-demand/
- https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_Ruby.rds.html
- https://devcenter.heroku.com/articles/getting-started-with-rails7
- https://medium.com/@zulhhandyplast/how-to-create-a-non-expiring-heroku-token-for-daemons-ops-work-da08346286c0
- https://www.digitalocean.com/community/tutorials/how-to-use-postgresql-with-your-ruby-on-rails-application-on-ubuntu-20-04

kio-cyrano-app


# Ubuntu

```sh
# add user deploy
sudo adduser deploy
# set as a sudo
adduser deploy sudo
# change to user and folder
su deploy
cd ../deploy/
```


```sh
ssh-keygen -t rsa -b 4096 -C "robin8a@gmail.com"

sudo nano .ssh/authorized_keys

```

# EBS 
```sh
bundle lock --add-platform x86_64-linux
eb init
eb create staging-test -db.engine postgres -db.i db.t3.micro
rake secret
eb setenv SECRET_KEY_BASE=
```



# Category

```sh
# rails generate scaffold Post name:string title:string content:text

rails generate scaffold Category name:string
rails generate scaffold Problem question:string generalScore:float category:references


```



# Heroku
## postgres

- https://devopscube.com/install-configure-postgresql-amazon-linux/


```sh
sudo postgresql-setup initdb
WARNING: using obsoleted argument syntax, try --help
WARNING: arguments transformed to: postgresql-setup --initdb --unit postgresql
 * Initializing database in '/var/lib/pgsql/data'
 * Initialized, logs are in /var/lib/pgsql/initdb_postgresql.log
 ```

 ```sh
sudo -u postgres createuser -s cyrano -P
sudo -u postgres psql


sudo -u postgres createuser -s cyrano -P
sudo -u postgres psql

 ```


 # Go Rails Ubuntu

 - https://www.digitalocean.com/?refcode=87fcb9dab7a3