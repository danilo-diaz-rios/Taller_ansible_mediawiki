FROM ubuntu:16.04

# Actualizamos la  lista de paquetes
RUN apt-get update && apt-get full-upgrade -y

# Instalamos ssh, python, pip
RUN apt-get install -y openssh-server python python-pip

#Configuramos la  llave publica

# - Creamos la ubicacion de  donde se almacenará el socker del servicio ssh

RUN mkdir /var/run/sshd

# - Se anexa la llave publica

COPY authorized_keys /root/.ssh/authorized_keys

# - Proporcionando los permisos pertinentes a la llave [-xw-------]

RUN ["chmod","0600","/root/.ssh/authorized_keys"]

CMD ["/usr/sbin/sshd", "-D"]
