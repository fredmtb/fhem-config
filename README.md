# fhem-config
FHEM auf Raspberry Pi installieren


1) Grundlegende Updates und Software installien 

Um das System auf den aktuellen Stand zu bringen, wird nach dem erneuten Login per Terminal ein komplettes Systemupdate durchgeführt, welches je nach Internetanbindung und zu installierender Pakete mehrere Minuten dauern kann. Anschließend werden nicht benötigte Pakete entfernt und das System nochmals neugestartet.

sudo apt-get update && sudo apt-get -y upgrade && sudo apt-get -y autoremove && sudo reboot


Nach dem Reboot des RPI erstmal wieder per ssh einloggen und nachfolgende Befehle absetzen, um alle notwendigen Voraussetzungen und zum Schluss auch FHEM zu installieren:

wget -qO - https://debian.fhem.de/archive.key | sudo apt-key add - && echo "deb https://debian.fhem.de/stable ./" | sudo tee -a /etc/apt/sources.list && sudo apt-get -y install apt-transport-https && sudo apt-get update && sudo apt-get -y install fhem

Der Code wurde aus dem FHEM-Wiki entnommen und mit notwendigen Ergänzungen angereichert. Sobald der Code im Terminal abgesetzt wurde, sollte nach einiger Zeit der Eintrag "Starting fhem..." erscheinen. Ab jetzt läuft FHEM immer sobald der RPI gestartet wird.


Das Webinterface ist ab sofort auch unter http://192.168.X.XXX:8083 erreichbar. Hier muss natürlich jeder die eigene IP-Adresse ersetzen, der Port 8083 am Schluss bleibt unverändert.
