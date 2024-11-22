Notre projet repose sur un réseau que nous avons conçu, intégrant trois routeurs pour communiquer, des switches et plusieurs machines remplissant des rôles spécifiques : client, serveur SNMP, serveur web et machine Syslog. Ce système permet de recevoir une notification SNMP, consultable sur le Syslog, lorsqu'un client accède à un site web via le service Apache activé. Ce site web, développé par nos soins, est une page simple sur le Japon, codée en HTML et CSS.

PSEUDO :

Github:
TurtulesNinjas -> Mathis Gogan 
Cucurbitaceagile -> Koba Traore
buisnesspro986 -> Aadil Jafar Safayatulla Marecar
Villa77777 -> Aly Demba

TRELLO :
Suzuki Mbozu -> Koba Traore


CONNFIGURATION POUR TESTER LE PROJET :

Télécharger et ouvrir le fichier Réseaux.mar sur marionnet.

Activer les interfaces réseaux respectives avec la commande ifup :
Client 1 : eth0
Client 2 : eth0
Web : eth0
SNMP : eth0
Syslog : eth0
R1 : eth1 et eth3
R2 : eth1 et eth3
R3 : eth1, eth2 et eth3

Donner la priorité au test avec le client 2 plutôt qu'avec le client 1 afin de prévenir les éventuels bugs. 

Lancer le service rsyslog sur les machines Web et Syslog en utilisant la commande : /etc/init.d/rsyslog start.

Utiliser les commandes /etc/init.d/apache2 start ou /etc/init.d/apache2 stop pour activer ou désactiver le service Apache, selon les besoins des tests sur le serveur Web et la machine cliente.

Vérifier l'état du service Apache et afficher un message indiquant un succès ou un échec en consultant les journaux avec la commande tail -f /var/log/daemon.log. Ou tail -f /var/log/messages.log pour surveiller tous les services.
