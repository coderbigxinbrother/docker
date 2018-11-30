FROM debian:latest

RUN echo "deb http://deb.debian.org/debian/ unstable main" > /etc/apt/sources.list.d/unstable.list && \ 
    printf 'Package: *\nPin: release a=unstable\nPin-Priority: 90\n' > /etc/apt/preferences.d/limit-unstable && \
    apt update && \
    apt install linux-headers-$(uname -r) -y && \
    apt install wireguard -y
    
ADD wg0.conf /etc/wireguard/

EXPOSE 38945/udp

CMD ["wg-quick", "up", "wg0"]
