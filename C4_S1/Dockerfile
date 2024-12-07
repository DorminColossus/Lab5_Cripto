FROM ubuntu:22.10

# Cambia a los repositorios de "old-releases"
RUN sed -i 's/archive.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list && \
    sed -i 's/security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list

# Actualiza paquetes e instala cliente y servidor OpenSSH
RUN apt update && apt upgrade -y && apt install -y openssh-client openssh-server

# Crea el directorio necesario para SSH
RUN mkdir -p /var/run/sshd

# Crea el usuario de prueba con contraseña prueba
RUN useradd -rm -d /home/prueba -s /bin/bash -g root -G sudo -u 1001 prueba && \
    echo 'prueba:prueba' | chpasswd

# Expone el puerto 22
EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
