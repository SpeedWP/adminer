# Adminer ISPConfig 3 Plugin

Authenticate and auto-check host by ISPConfig Remote API

Your ISPConfig Remote User needs the following functions:

Sites database functions
Server functions

In Datei /plugins/AdminerISPConfig.php muss ab Zeile 32 folgendes angepasst werden:

        $this->ISPConfigRemoteUser = $username;
        $this->Password = $password;
        $this->https://server.domain.tld:8080/remote/ = $soap_uri;
        $this->false = $check_ssl;
       
Im letzten Fall (check_ssl) steht "true" für eine trusted Zertifikat und "false" für die selbst signierten.

Einrichten unter Ubuntu oder Debian:

cd /usr/share
git clone https://github.com/SpeedWP/adminer.git
cd adminer
wget https://www.adminer.org/latest-de.php
mv latest-de.php adminer.php


Als letztes müsst Ihr noch die Datei /etc/nginx/sites-available/ispconfig.vhost ergänzen. Dazu einfach den kompletten Inhalt von Adminer.conf nach /etc/nginx/sites-available/ispconfig.vhost kopieren.

More info:

https://www.adminer.org/plugins/#use
https://www.ispconfig.org
