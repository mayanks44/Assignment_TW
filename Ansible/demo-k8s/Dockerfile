FROM msaraswat/lamp
RUN apt-get update -y && apt-get install wget -y

COPY start-script.sh .
RUN chmod +x start-script.sh
RUN rm /sbin/init && ln -s /lib/systemd/systemd /sbin/init
CMD start-script.sh

RUN wget https://releases.wikimedia.org/mediawiki/1.35/mediawiki-1.35.0.tar.gz
RUN tar -zxpvf mediawiki-1.35.0.tar.gz
RUN mkdir /var/www/html/mediawiki
RUN ln -s mediawiki-1.35.0/ mediawiki
# RUN mv mediawiki-1.35.0 /var/www/html/mediawiki
RUN chmod 755 /var/www/html/mediawiki/
