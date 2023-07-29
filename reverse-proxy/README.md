# Reverse-Proxy

## Sources

### Foundation Info
Using Jason Wilder's Automated Nginx Reverse Proxy for Docker
http://jasonwilder.com/blog/2014/03/25/automated-nginx-reverse-proxy-for-docker/

### Linux Handbook 
This is the primary post I've followed to get this working
https://linuxhandbook.com/nginx-reverse-proxy-docker/



        environment:
            - MYSQL_ROOT_PASSWORD
            - MYSQL_RANDOM_ROOT_PASSWORD
            - MYSQL_DATABASE
            - MYSQL_USER
            - MYSQL_PASSWORD