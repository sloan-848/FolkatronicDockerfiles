FROM stilliard/pure-ftpd:hardened
RUN useradd -g ftpgroup -d /home/folkatronic brock && echo "brock:***REMOVED***" | chpasswd
RUN useradd -g ftpgroup -d /home/folkatronic will && echo "will:***REMOVED***" | chpasswd

# Generate and configure SSL key
RUN mkdir -p /etc/ssl/private &&\
openssl dhparam -out /etc/ssl/private/pure-ftpd-dhparams.pem 1024 &&\
openssl req -x509 -nodes -newkey rsa:1024 -sha256 -keyout \
  /etc/ssl/private/pure-ftpd.pem \
  -out /etc/ssl/private/pure-ftpd.pem -subj "/C=US/ST=Ohio/L=Columbus/O=Folkatronics/OU=IT Department/CN=folkatronics.com" &&\
chmod 600 /etc/ssl/private/*.pem

CMD /usr/sbin/pure-ftpd -c 50 -C 10 -E -j -R -P $PUBLICHOST -p 30000:30009 
#--tls 1

