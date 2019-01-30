FROM resin/rpi-raspbian
RUN apt-get update && apt-get install -y \
        curl \
        wget \
        vim
# Install Resilio Sync
ENV INITSYSTEM on
WORKDIR /opt/resilio/bin
COPY mnt-barra2tb.mount /etc/systemd/system/
RUN systemctl enable mnt-barra2tb.mount
# there should be a way to check the hash of this file
RUN wget https://download-cdn.resilio.com/stable/linux-arm/resilio-sync_arm.tar.gz
RUN tar xf resilio-sync_arm.tar.gz
RUN ln -sf /lib/ld-linux-armhf.so.3 /lib/ld-linux.so.3 # Fix
RUN chmod +x ./rslsync
EXPOSE 8888
# Need's more work to get the container to run with this
CMD ["./rslsync", "--nodaemon", "--storage", "/data", "--webui.listen", "0.0.0.0:8888"] 
