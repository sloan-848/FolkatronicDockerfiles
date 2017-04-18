FROM ubuntu:trusty

MAINTAINER Will Sloan <sloan.848@osu.edu>

RUN apt-get update && \
apt-get install -y wget

RUN cd /root && \
wget https://dl.eff.org/certbot-auto && \
chmod a+x certbot-auto 

CMD sh /root/certbot-auto certonly --standalone -d folkatronic.com -d www.folkatronic.com
