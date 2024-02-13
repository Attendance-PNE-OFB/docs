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

![Architecture lorawan](https://github.com/Attendance-PNE-OFB/docs/assets/145433511/9a2e4c82-880f-4daa-b400-1cdbd331fd2d)


Ces appareils représentent tous ceux disponibles dans une installation LoRaWAN. Il est important de noter que tous ces appareils ne sont pas obligatoires pour une installation. Par exemple, le Join Serveur est optionnel.

Dans le cadre d'une installation dans le PNE, il peut être judicieux d'en posséder un, car il est possible qu'un test soit effectué sur une petite portion du parc, puis étendu sur une portion plus grande.

Tous ces appareils ont un coût :

**Endnode :**

*Prix :* 10 € à 500 €

*Facteurs de variation :*
- Fonctionnalités: Capteurs intégrés, puissance de transmission, mémoire, etc.
- Fabricant: Dragino, Microchip, Semtech, etc.

**Gateway :**

*Prix :* 200 € à 1 000 €

*Facteurs de variation :*

- Nombre de canaux: 1 à 8 canaux
- Portée: 2km à 10km
- Fabricant: MultiTech, Kerlink, RAK Wireless, etc.

**Network Server :**

*Prix :* Logiciel open source gratuit ou solution commerciale à partir de 1 000 €/an

*Facteurs de variation :*
- Nombre de nœuds finaux
- Fonctionnalités avancées: Facturation, sécurité, etc.

**Application Serveur:**

*Prix :* Dépend du développement personnalisé ou solution SaaS à partir de 50 €/mois

*Facteurs de variation :*
- Fonctionnalités: Intégration avec d'autres systèmes, tableaux de bord, etc.
- Complexité du développement

**Join Server :**

*Prix :* Gratuit pour les petits réseaux, solution commerciale à partir de 50 €/mois

*Facteurs de variation :*

- Nombre de nœuds finaux
- Fonctionnalités avancées: Authentification, gestion des clés, etc.
Remarques :

Comme le PNE possède déjà des serveurs, il est possible de les utiliser pour héberger le network server et l'application serveur, ce qui réduira le coût total du réseau.
