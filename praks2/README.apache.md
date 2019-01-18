# Ülessanne
>Ülesandeks oli luua apache2 veebiserver ja selle esilehte muuta.
# Instaleerimine
>apt-get install apache2 apache2-doc - Instaleerib apache2 veebiserveri
# Lehe muutmine
> Lehe muutmiseks kustutasin kaustast /var/www/html/index.html ära
> Ning tegin uue index.html kus muutsin esilehte.
# public kausta loomine
> Public kausta loomiseks kasutasin käsku mkdir /home/it/public_html
> Selle linkisin apache kaustaga käsuga ln -s /home/it/public_html/ /var/www/html/
