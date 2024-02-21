# Prospection LoRaWAN - Parc National des Écrins

## Contexte

Le Lora est un moyen de communication faible énergie, qui communique sur des ondes basse-fréquence. Il est utilisé par la plupart des outils IoT, car il permet leur communication, tout en économisant sa batterie. Sa portée elle aussi est un avantage : de 5km (zone urbaine) à 15km dans les zones rurales. Il peut donc être judicieux d'utiliser ce genre de réseau de communication dans un parc.

## Problématique

Comme écrit précédemment, ce type de réseau peut être très utile, permettant de consommer très peu d'énergie, tout en transmettant de manière efficace l'information. Cependant, cela a un coût, et potentiellement de la pollution visuelle dans le parc. Nous allons donc voir les avantages d'une installation LoRaWAN dans le parc national des Écrins, et les inconvénients que son installation représente.

## LoRaWAN, ses besoins

Pour fonctionner correctement, une infrastructure LoRaWAN doit comprendre plusieurs appareils :

- **EndNodes :** les appareils qui captent l'information qu'il faut transmettre

- **Gateways :** les appareils qui permettent de recevoir les informations des endnodes, pour les envoyer au Network Server

- **Network Server :** un serveur qui fait tourner un software qui permet de gérer tout le réseau

- **Application Server :** un serveur (peut-être le même serveur que le Network Server) qui fait tourner un software qui permet de consulter les données de manière sécurisée

- **Join Serveur :** un software qui tourne sur un serveur qui permet de gérer les join-requests des endnodes, autrement dit il gère l'ajout de nouveaux équipements dans le réseau

![Architecture LoRaWAN](https://github.com/Attendance-PNE-OFB/docs/assets/145433511/9a2e4c82-880f-4daa-b400-1cdbd331fd2d)


Ces appareils représentent tous ceux disponibles dans une installation LoRaWAN. Il est important de noter que tous ces appareils ne sont pas obligatoires pour une installation. Par exemple, le Join Serveur est optionnel.

Dans le cadre d'une installation dans le PNE, il peut être judicieux d'en posséder un, car il est possible qu'un test soit effectué sur une petite portion du parc, puis étendu sur une portion plus grande.

Tous ces appareils ont un coût :

**Endnode :**

Pour le cas d'une utilisation avec un piège photo, le coût du endnode comprendra le piège photo, la batterie, le cadenas, et le module de communication LoRa, ainsi que la carte IoT. Le coût total est d'environ 540€.

*Prix :* piège photo (batterie, piège photo, cadenas, ...) + module de communication LoRa + Carte IoT (~500€ + ~10 € + ~30€)

Afin d'avoir un lien entre piège photo et carte IOT, il faudrait disposer d'une liaison filaire entre l'un et l'autre. Pour cela, il faut veiller à bien choisir ses pièges photos. Certains ne disposent pas de port USB, et donc ne seront pas adaptés. On retrouve ce type de piège pour environ 300€.

Ensuite, via une connexion filaire, il sera possible de lier le piège photo et la carte IoT. Ainsi, la carte IoT pourra récupérer les photos et les traiter avec le modèle.

En parlant du modèle, selon la carte il pourra être préférable d'utiliser le modèle le plus petit de yolov8, qui est yolov8n. La carte IoT pourra ensuite utiliser le modèle sur les photos récoltées, puis envoyer les informations avec LoRa. 

Un exemple de endnode serait le suivant : 

- Piège photo : Browning Strike Force PRO DCL (~220€)
![Piège Photo USB](https://github.com/Attendance-PNE-OFB/docs/assets/145437462/e32277ed-494b-4eb6-89be-2e53a2a9b584)

- Carte IoT & Module LoRa : *a renseigner*

  
**Gateway :**

Il existe de nombreuses gateways différentes avec un nombre d'options variables. Les principales sont le nombre de canaux, autrement dit le nombre d'appareils que la gateway peut gérer en même temps. La portée varie en fonction de la taille de l'antenne. A noter qu'il est préférable d'ajouter une antenne extérieures en plus pour augmenter la portée et la qualité du signal.
On peut construire son propre réseau de gateway ou alors payer pour utiliser le réseau d'un opérateur. Voici par exemple la couverture LoRa d'Orange au niveau du Parc National des Écrins :

![Couverture LoRa Orange](https://github.com/Attendance-PNE-OFB/docs/blob/main/assets/couverture_lora_orange.png?raw=true)

Il est important de prendre en compte que le coût de la gateway n'est pas le seul coût à prendre en compte. Il faut aussi prendre en compte le coût de l'installation, qui peut être très élevé, surtout dans un parc national, où il est possible que l'installation soit difficile. Dans le cas d'une installation en hauteur, il faudra prendre en compte un coût additionnel pour l'installation d'un paratonnerre.

*Prix :* 200 € à 1 000 €

*Facteurs de variation :*

- Nombre de canaux: 1 à 8 canaux
- Portée: 2km à 10km
- Fabricant: MultiTech, Kerlink, RAK Wireless, etc.

**Network Server :**

Ici, il est possible d'utiliser 3 méthodes :
- Utiliser un logiciel open source, gratuit, et le faire tourner sur un serveur déjà existant, dans le cas d'une utilisation privée.
- Faire partie de la LoRa Alliance, et utiliser un netID, qui permettra de filtrer les messages, et donc d'économiser sur les forfaits des gateways (gratuit si les démarches sont effectuées).
- Sous-traiter un service (Amazon avec *AWS IoT* par exemple) qui va héberger le serveur pour vous.

*Prix :* Logiciel open source gratuit ou solution commerciale (AWS IoT, etc.) pour moins d'1€/mois pour un petit réseau (50 appareils, qui envoient 24 messages par jour (1 par heure)) :

- 0,17$ pour les frais de connectivité
- 0,036$ pour les frais de messagerie
- 0,01$ pour les frais de règles (envoi de donnés toutes les heures)

Soit un coût de 0,216$/mois pour tenir le service à jour.

*Facteurs de variation :*
- Nombre de nœuds finaux
- Fonctionnalités avancées: Facturation, sécurité, règles, mises à jour, etc.

**Application Serveur:**

*Prix :* Dépend du développement personnalisé ou solution SaaS à partir de 50 €/mois

*Facteurs de variation :*
- Fonctionnalités: Intégration avec d'autres systèmes, tableaux de bord, etc.
- Complexité du développement

**Join Server :**

L'ajout d'un Join Server est optionnel, mais peut être utile pour gérer les join-requests des endnodes. Cela permet une meilleure gestion des endnodes, et une meilleure sécurité.

*Prix :* Gratuit pour les petits réseaux, solution commerciale à partir de 50 €/mois

*Facteurs de variation :*

- Nombre de nœuds finaux
- Fonctionnalités avancées: Authentification, gestion des clés, etc.

Remarques :

Comme le PNE possède déjà des serveurs, il est possible de les utiliser pour héberger le network server et l'application serveur, ce qui réduira le coût total du réseau.

## Mise en situation - PNE

Le parc national des Écrins a une superficie de 2 700 km². En sachant qu'on est en zone rurale, (non urbaine), mais que l'on a la présence d'un grand nombre d'arbres dû aux forêts, ainsi qu'une forte disparité de relief, ce qui peut engendrer une grande baisse de portée pour les gataway. On estimera alors qu'une gateway peut avoir une portée d'environ 5à10km. Pour s'assurer d'une bonne couverture, il faudrait que les gateways se chevauchent, à 50% par exemple pour garantir une bonne couverture et transmission/réception des messages (ce chauvauchement peut être modifié, un moins grand pourcentage de chevauchement permettra une installation plus légère (moins de gateways), mais une couverture moins bonne).

Nombre de gateways = Superficie / (Portée² * (1 - Chevauchement))

Il faudrait donc 2700 / (10² * (1 - 0.5)) = 54 gateways pour couvrir l'entièreté du parc.

## Points à prendre en compte

- **Coût :** Le coût total de l'installation est très élevé, et il est possible que le parc national des Écrins ne puisse pas se permettre une telle installation. Il est possible de réduire le coût en utilisant des serveurs déjà existants, mais cela reste un coût très élevé. Le CNRS a actuellement un projet appelé Terra Forma qui vise à développer la récolte d'information dans des espaces naturels. Ils proposent par exemple ce genre d'installation :

<img width="726" alt="image" src="https://github.com/Attendance-PNE-OFB/docs/assets/145437462/257f9205-173f-4328-8ef8-006111dfccbd">


Il faudrait donc prendre en compte l'installation d'autres capteurs tels que des capteurs de température, de qualité de l'air, ...

- **Pollution visuelle :** L'installation de gateways dans le parc national des Écrins peut être une pollution visuelle, et peut donc être interdite par le parc.

Exemple d'installation d'une gateway :

![Exemple d'installation](https://github.com/Attendance-PNE-OFB/docs/assets/145437462/f891cdd7-954c-4299-8c40-a5008245e631)


- **Installation :** L'installation des gateways peut être très difficile, et donc très coûteuse. Il est possible que l'installation soit impossible dans certaines zones du parc.

- **Maintenance :** La maintenance des gateways peut être très difficile, et donc très coûteuse. Il est possible que la maintenance soit impossible dans certaines zones du parc.

- **Couverture réseau :** Il est possible que la couverture réseau soit impossible dans certaines zones du parc, et donc que l'installation soit moins efficace, voir inutile.


## Cas du Lauvitel
Pour couvrir le site du Lauvitel, une seule gateway pourrait suffire. Il s'agit de la gateway positionnée sur la cabane du PNE.
Néanmoins, pour rendre plus robuste l'installation, il est fortement recommandé d'installer au minimum une deuxième gataway pour se prémunir du cas où la gateway serait en panne et donc par conséquent toute l'infrastructure qui reposerait sur une seule gateway. 
Voici une carte qui montre trois gateways ainsi que la zone qui devrait être théoriquement couverte malgré le relief.  
![Positions_gateways](https://github.com/Attendance-PNE-OFB/docs/assets/145433511/e10bf9be-69b7-4254-8a13-21f7e3e443d9)
![Lauvitel_gateways](https://github.com/Attendance-PNE-OFB/docs/assets/145433511/74b04bea-af53-4c82-9892-aea5ffe8d67c)  
En effet, le relief est un facteur très important dans l'estimation de la couverture d'une zone. On préférera toujours poster les gateways le plus en hauteur possible.  
Grâce au site : [Line-of-sight](https://www.scadacore.com/tools/rf-path/rf-line-of-sight/) il est possible de visualiser le relief entre deux points et de voir si la ligne de vue est vide ou non.
On peut également jouer avec la hauteur du point GPS pour connaître la hauteur minimale au-dessus du sol pour éviter l'atténuation du signal à cause du relief.
Par exemple, entre la gateway de la cabane et la gateway du point de Malhaubert, il faudrait que la gateway de Malhaubert soit surélevée à 18 mètres du sol.  
![Elevation_map](https://github.com/Attendance-PNE-OFB/docs/assets/145433511/ac67c103-5671-44c3-9ab9-2cf39837ae72)

Une fois le positionnement défini, il faut déterminer le modèle de gateway. Comme décrit au-dessus, il y a de nombreux modèles de gateway différents, en voici trois avec pour chacun ses avantages et ses inconvénients comparés aux autres.

Une fois le modèle de gateway choisi, il est nécessaire d'avoir une connexion de téléphonie mobile 4G pour transmettre des messages du gateway vers le serveur. Pour cela, nous avons étudié les couvertures 4G des principaux opérateurs français sur le site du Lauvitel. L'opérateur couvrant le mieux le site du Lauvitel est Bouygues.  
![Couverture 4g](https://github.com/Attendance-PNE-OFB/docs/assets/145433511/d940d190-382a-4408-8340-7092cc8edf75)

