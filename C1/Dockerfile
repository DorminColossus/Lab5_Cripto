FROM ubuntu:16.10

# Cambia a los repositorios de "old-releases"
RUN sed -i 's/archive.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list && \
    sed -i 's/security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list

# Actualiza paquetes e instala el cliente OpenSSH
RUN apt update && apt upgrade -y && apt install -y openssh-client

CMD ["bash"]
