FROM stilliard/pure-ftpd:latest
RUN useradd -g ftpgroup ftp

# Generate and configure SSL key
CMD /run.sh -c 50 -C 50 -l puredb:/etc/pure-ftpd/pureftpd.pdb -E -R -P $PUBLICHOST -p 30000:30009 
