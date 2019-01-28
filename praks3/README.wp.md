# Ülessanne
>Ülesandeks on instaleerida php 5 ja 7 
> Selleks kasutan apt-get install php5-common libapache2-mod-php5 php5-cli
> apt install php 7.2 ja  apt install php7.2-cli php7.2-common php7.2-curl php7.2-gd php7.2-json php7.2-mbstring php7.2-mysql php7.2-xml
# Mysql instaleerimine
Selleks kasutasin käsku apt-get install mysql-server php5-mysql
# Graafilise keskonna instaleerimine

>apt get install phpmyadmin - instaleerib phpmyadmin graafilise keskkonna.
# php töö kontrollimine
php töö kontrollimiseks koostasin lühikese skripti kus saan vaadata kas php töötab

#HTTPS Protokoll
Turvalise ühenduse saamiseks sisestasin sellised käsud
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt
genereerib turvalised võtmed
openssl dhparam -out /etc/ssl/certs/dhparam.pem 2048
cp /etc/apache2/sites-available/default-ssl.conf /etc/apache2/sites-available/default-ssl.conf.bak backup faili tegemine
Muutsin /etc/apache2/sites-available/default-ssl.conf sisu 
Panid moodulid tööle
a2enmod ssl
a2enmod headers
a2ensite default-ssl
apache2ctl configtest
ning tegin restardi apache2 serverile
systemctl restart apache2
täielik juhend leitav siit: https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-apache-in-ubuntu-16-04
# Kahes virtuaalmasinas wordpressi käivitamine
Et saada kahes eraldi masinas wordpressi käivitada muutsin ma mysql kasutajat tehes ja õigusi muutes localhosti osa oma wordpressi serveri ip-ks 
