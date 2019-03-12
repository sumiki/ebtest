
This project is for testing switching nginx conf using EB environment variable.

Service Mode
```
eb setenv MAINTENANCE_PROVIDER=
eb deploy
```

Maintenanc Mode
```
eb setenv MAINTENANCE_PROVIDER=all
eb deploy
```

## Can we do better

Now there is `service nginx restart` in setup.sh script.  
If we can run setup.sh just before nginx get restarted, we may be able to remove it and it is more straightforward.




## Tried but failed

 1. set_by_lua 

Deploy Failed
directive "set_by_lua" in /etc/nginx/conf.d/webapp_healthd.conf:46
nginx: configuration file /etc/nginx/nginx.conf test failed. 

 2. perl_set  
 
Deploy Failed
nginx: [emerg] unknown directive "perl_set" in /etc/nginx/conf.d/webapp_healthd.conf:46
nginx: configuration file /etc/nginx/nginx.conf test failed
