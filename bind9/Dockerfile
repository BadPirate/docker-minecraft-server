FROM ubuntu/bind9:9.16-20.04_beta

# Copy BIND configuration and zones from repo into the image
COPY bind9/ /etc/bind/

# Ensure readable by named and owned by bind user
RUN chown -R bind:bind /etc/bind \
    && chmod -R 644 /etc/bind/*

EXPOSE 53/tcp 53/udp

CMD ["named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]


