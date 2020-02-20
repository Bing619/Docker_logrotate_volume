Docker_logrotate_volume
====

1. create docker-container file in the /etc/logrotate.d/
-------  
```   
/var/lib/docker/volumes/railsapi_prod_log/_data/production.log {        
    daily       
    rotate 30       
    copytruncate        
    missingok       
    dateext     
    dateformat -%Y-%m-%d        
    create 0644 root root       
}       
```
test:       
logrotate -vf /etc/logrotate.d/docker-container

2. Containers log cp to host
-------
docker cp 9cc3c726a750:/surflock/log/production.log /logs/2.log

3. The final result
-------
![](https://github.com/Bing619/Docker_logrotate_volume/blob/master/img/rails_volume.png)         
![](https://github.com/Bing619/Docker_logrotate_volume/blob/master/img/volume.png)      
![](https://github.com/Bing619/Docker_logrotate_volume/blob/master/img/daily.png)       

4. remark
-------
        Produce one a day
