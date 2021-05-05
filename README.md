# mongo-trouble
#ExecStart=/usr/bin/mongod --config /etc/mongod.conf (code=exited, status=14)
##After googling around for a while. I found that that is because the permission setting on 
##/var/lib/mongodb and /tmp/mongodb-27017.lock are wrong. You will have to change the owner to monogdb user
``` bash
chown -R mongodb:mongodb /var/lib/mongodb
chown mongodb:mongodb /tmp/mongodb-27017.sock

sudo service mongod restart 
```
