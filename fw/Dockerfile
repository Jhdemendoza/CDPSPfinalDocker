FROM ubuntu:16.04

RUN apt-get update 
RUN apt-get install -y git
RUN apt-get install -y apt-utils
RUN apt-get install -y iptables
RUN git clone https://github.com/Jhdemendoza/firewall.git
WORKDIR /firewall
EXPOSE 80
CMD ./fw.fw start

## No se puede utilizar iptables porque necesita /sbin/modprobe, del kernel de Linux. He encontrado la manera de compartir los recursos del host con el contenedor, mediante los flags --privileged y --cap-add=ALL para permitir acceso total, pero mi máquina no es Linux.
#
#    fw:
#        build: ./fw/
#        depends_on:
#            - lb
#        ports: 
#            - "80:80"
#        networks:
#            LAN3:
#                ipv4_address: 10.1.2.1
#
## En docker-compose habría que añadir el servicio indicado arriba.