# docker-guacamole

[Guacamole](https://guacamole.incubator.apache.org/) is a really useful tool,
but can be difficult to setup properly. The deployment  process can be greatly
simplified using docker containers, and orchestrated using `docker-compose`.

This was forked from @BrowncoatShadow's compose-guacamole project and updated slightly to add
Duo MFA extension.

Using @aeboccia's nginx configuration to proxy traffic to tomcat: https://github.com/aeboccia/docker/blob/master/Guacamole/web/guacamole_revproxy.conf

## Usage

* Clone the project

```
git clone https://github.com/slackr/docker-guacamole
cd docker-guacamole
```

* Create ./config/guacamole.properties from sample and add duo config data if needed 
* Modify ./.env and update passwords

* Generate nginx certificates

```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout ./nginx/ssl/web.key -out ./nginx/ssl/web.crt
chmod 600 ./ssl/web.key
```

* Bring it all up 

```docker-compose up -d```

Give it a few seconds to initialize and then you can access guacamole
at `http://docker-host/` (or whatever you specified in the nginx .conf). The default username and password are
both `guacadmin` (go to your user preferences to change it, and then create another user for regular use).
