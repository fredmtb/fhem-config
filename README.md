FHEM auf Raspberry Pi installieren


1) Grundlegende Updates und Software installien

sudo apt-get update && sudo apt-get -y upgrade && sudo apt-get -y autoremove && sudo reboot


2) FHEM installieren:

wget -qO - https://debian.fhem.de/archive.key | sudo apt-key add - && echo "deb https://debian.fhem.de/stable ./" | sudo tee -a /etc/apt/sources.list && sudo apt-get -y install apt-transport-https && sudo apt-get update && sudo apt-get -y install fhem

Der Code wurde aus dem FHEM-Wiki entnommen und wurde um einige notwendige Pakete ergänzt. Sobald der Code im Terminal abgesetzt wurde sollte nach einiger Zeit der Eintrag "Starting fhem..." erscheinen. Ab jetzt läuft FHEM immer sobald der RPI gestartet wird.

Das Webinterface ist ab sofort auch unter http://192.168.X.XXX:8083 erreichbar. Hier muss natürlich jeder die eigene IP-Adresse ersetzen, der Port 8083 am Schluss bleibt unverändert.

