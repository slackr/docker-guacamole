# docker-guacamole

[Guacamole](https://guacamole.incubator.apache.org/) is a really useful tool,
but can be difficult to setup properly. The deployment  process can be greatly
simplified using docker containers, and orchestrated using `docker-compose`.

This was forked from @BrowncoatShadow's compose-guacamole project and updated slightly to add
Duo MFA extension.

## Usage

* Clone the project

```
git clone https://github.com/slackr/docker-guacamole
cd docker-guacamole
```

* Create ./config/guacamole.properties from sample and add duo config data if needed 
* Modify ./.env and update passwords

* Bring it all up 

```docker-compose up -d```

Give it a few seconds to initialize and then you can access guacamole
at `http://docker-host:8080/guacamole/`. The default username and password are
both `guacadmin` (go to your user preferences to change it, and then create another user for regular use).
