FROM ubuntu:16.04

RUN apt-get update 
RUN apt-get install -y crossroads
EXPOSE 80
CMD xr --verbose --server tcp:0:80 --backend crm:3000:1 --backend crm2:3000:1 --backend crm3:3000:1 --web-interface 0:8001 -S -dr
