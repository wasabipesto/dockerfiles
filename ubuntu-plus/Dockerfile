FROM ubuntu:bionic

RUN apt-get update -y && \
    apt-get install -y bash-completion command-not-found mtr-tiny dnsutils net-tools && \
    apt-get install -y nmap traceroute netcat iproute2 tcpdump iputils-ping isc-dhcp-client && \
    apt-get install -y curl nano wget && \
    apt-get clean -qy

ENTRYPOINT ["/bin/bash"]