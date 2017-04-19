FROM eboraas/apache-php
# Add rm of .pid file because apache is very touchy about .pid files existing from previous runs
COPY ./apache2/ /etc/apache2/
CMD rm -f /var/run/apache2/apache2.pid && exec apache2ctl -DFOREGROUND
