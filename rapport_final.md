> Aurélien COSTE, Esteban THÉVENON, Lony RIFFARD, Florian MACHENAUD

# Rapport Final

## Rappel du sujet/besoin et cahier des charges

Notre projet est porté par le Parc National des Écrins et par l'OFB (Office Français de la Biodiversité). L'objectif est de connaître la fréquentation des parcs par les visiteurs et usagers afin d’assurer au mieux leurs missions de protection, de connaissance, ainsi que d’accueil du public.

Les données de flux physiques (eco-compteurs, enquêtes…) collectés avec des méthodes traditionnelles demandent a être consolidées en terme d’analyse et confrontés avec des solutions innovantes en devenir (big data, informations géographiques, IA...).

En 2022, dans le contexte de hausse de la fréquentation post covid le Parc national des Ecrins a redéfini ses objectifs en matière de suivi des flux de visiteurs.

Cela a amené le Parc national des Ecrins à collaborer avec l’OFB à l’été 2023 pour expérimenter et consolider une solution de suivi innovante par l’utilisation de l’Intelligence artificielle associée à des capteurs photos. Solution mise au point par Mathieu Garel, chercheur à l’OFB, et qui a été testée (robustesse, sur 4 sites de terrain), comparée à d’autres solutions (Deepfaune...) et qui a fait l’objet de développements pour la consolider et l’intégrer dans une chaîne de travail propre au PNE. La chaîne de travail testée en 2023 va de la collecte de terrain, en passant par le floutage des visages, la détection, la classification, et la visualisation des données dans l’application Ist SOS.

A noter que le cœur du projet repose sur un script de détection automatique d'objets (ici les "humains") dans des images, basé sur le modèle YOLOv4 entraîné sur le jeu de données COCO. Ce script utilise le modèle de réseau de neurones yolov4 pour détecter des objets dans des images provenant d'un serveur FTP ou d'un répertoire local. Il permet ainsi de compter automatiquement, sans visualisation par l'utilisateur, le nombre de personnes présentes sur des images, notamment dans le cadre de suivis de la fréquentation réalisés avec des pièges photos à déclenchement automatique. Le script compte le nombre maximum d'humains au sein de chaque séquence, retenu comme taille de groupe. Le travail d’expérimentation et de consolidation a été mené dans le cadre du stage d’Aurélien Coste, 4ème année à Polytech Grenoble de mai à août 2023.

Les usages des données de fréquentation sont diverses :
- alimenter les indicateurs de données socio-économiques pour évaluer le poids de la randonnée dans les espaces naturels,
- suivi des flux à des fins d’observation,
- travaux de recherche appliquée pour étudier les interactions faune / pratiques récréatives (cas de l’OFB dans les massifs de Belledonne et des Bauges par ex.).

La solution de suivi de la fréquentation par capteurs photos associé à de l’IA permet de répondre à des besoins des gestionnaires d’espaces protégés et à des projets de recherche appliquée en espaces naturels. Le projet que nous proposons pour les 5ème année (S10) présente un fort potentiel d’utilisation par d’autres structures que le PNE et l’OFB. A l’issue de cette nouvelle phase de R&D, l’essaimage de l’usage de cette solution pourrait se faire à court-moyen terme dans le cadre de réseaux constitués (Parcs nationaux, conservatoires d’espaces naturels, réserves naturelles, organismes de recherche...).

L'objectif du projet est d'approfondir l’expérimentation menée en 2023 et poursuivre la consolidation de l’outil mis au point par Mathieu Garel en intégrant notamment les derniers développements (floutage des cadres de détection plutôt que les visages – en lien avec les développements aussi menés par d’autres solutions qui reposent sur l’IA).

Il s’agira de mener un travail exploratoire afin de :
- renforcer et tester la fiabilité de la solution,
- de développer l’outil (sens de passage, upgradage de briques, etc.),
- de tester l’utilisation de l’outil dans un contexte d’étude précis à partir de jeu de données fournies et d’explorer de nouvelles pistes d’utilisation de la donnée (modèle mathématique/cartographique, data visualisation...),
- et de proposer des scénarios d’évolution tel que l’utilisation de l’IA embarquée et l’IoT.

En ce qui concerne le travail attendu, voici les consignes que l'on nous a donné :


A partir de l’existant et d’un travail de prospective le PNE et l’OFB ont identifié des pistes de travail qu’il conviendra de préciser lors du lancement et de la phase de définition de la roadmap. Le Parc national souhaiterait que le projet se déroule en méthode Agile.

Périmètre du projet proposé en première intention :

- Réaliser une analyse de l'outil développé en mode prototype à l'été 2023 (résultats, analyse "critique" du processus et recommandations d'améliorations) + ré investiguer les outils équivalents, y compris commerciaux
- Analyser, critiquer et redéfinir au besoin l’architecture globale du système et de la chaîne de travail (objets, script d'IA, floutage des images, serveurs, data visualisation...),
- Identifier les obligations en matière de respect de la vie privée du service (RGPD) et du droits à l'image (risques d’atteinte au respect de la vie privée ou à d'autres aspects réglementaires...)
- Étudier et définir la sécurité du projet
- Approfondir la faisabilité de développer la reconnaissance des sens de passage des piétons par l'IA- Réaliser les développements pour la détection des sens de passage : modélisation de l'évolution du modèle IA, réalisation de codes, tests de classification, tests de fiabilité, développement des API en V2, développement de l'outil Ist SOS pour la visualisation double sens…
- Analyser la pertinence et le cas échéant upgrader vers yolov8 pour monter en capacité (rapidité)
- Réaliser les tests de la solution développée à partir de sets de données fournies
- Continuer la calibration des modèles utilisés sur d’autres éléments que le simple comptage des humains avec notamment la caractérisation de la pratique (randonnée, ski de randonnée, VTT, présence ou non de chien)
- Documenter les développements sur le dépôt Github du projet.
- Analyser la faisabilité et élaboration d'un modèle mathématique/cartographique pour essayer d'analyser les flux d'un site avec une logique de maillage d'itinéraires. Cas d’étude du site du Lauvitel en Oisans.
- Exploiter les données connexes (niveaux d'équipements des piétons, chiens, faune...) et les rendre visualisables dans l'outil IST SOS.
- Prospective et recommandations sur l'évolution de la chaîne de travail à moyen terme : remplacement des capteurs photos par IA embarquée, serveurs, …

- Volet prospectif :
  - Prospecter et estimer le coût d'objectif d'un scénario à moyen terme de remplacement des capteurs photos par le développement d'une solution d'IA embarquée avec transmission LoRaWAN pour 50 objets (développement du capteur intégrant l'IA et déploiement d’un mode de transmission à distance)
  -> Changement à 5 objets sur une zone précise suite à un entretien.

  - Prospecter pour la réalisation d'une solution de dénombrements de tentes de bivouac sur photos (set de donnée disponible au besoin).



## Technologies employées

- YOLOv8 : dernier modèle de détection d'Ultralytics (actuellement, la version 9 est sortie). Ce modèle est plus optimisé et performant que YOLOv4, et permet de générer un squelette sur un corps humain, en y identifiant des points (articulations, et points du visage).

- CLIP : CLIP est un réseau de neurones qui apprend efficacement les concepts visuels de la supervision du langage naturel. CLIP peut être appliqué à n’importe quel repère de classification visuelle en fournissant simplement les noms des catégories visuelles à reconnaître, de la même façon que les capacités « zero-shot » du GPT-2 et du GPT-3. C'est un outil développé par OpenAI.

- Ist SOS : Logiciel de visualisation de données, utile pour voir les résultats des analyses.

## Architecture techniques

En ce qui concerne l'architecture technique, nous avons la contrainte de devoir réaliser un outil utilisable sur la chaine de travail actuelle.

![chaine de travail du PNE](https://github.com/Attendance-PNE-OFB/docs/assets/145437462/7cd3f7df-b42a-431c-a6cd-a94f7382500f)

Tout d'abord, cette chaine de travail commence avec les pièges photos. Ces pièges sont utilisés pour prendre des photos des visiteurs lorsqu'ils passent devant l'appareil. Ces photos sont stockées sur une carte SD propre à chaque appareils. Ces données sont ensuite récoltées à la main et déposées sur le serveur FTP.

Cette chaine de travail est composée de 3 serveurs. Le premier est un serveur FTP. Les photos récoltés des pièges photos sont stockées sur ce serveur.Ensuite, il y a un serveur data, qui permet de faire tourner le modèle, de récolter les données des photos sous forme de CSV, et de flouter les photos traitées afin de respecter la vie privée des visiteurs. Ces données de sorties CSV sont ensuite envoyées vers un dernier serveur d'administration et de visualisation de données. Ce dernier serveur permet d'utiliser les données CSV pour les visualiser avec l'outil Ist SOS.

## Réalisations techniques

Tout d'abord, nous avons du prendre en main les technologies étudiées. Lors de nos recherches, nous avons constaté que les technologies évoluaient rapidement, et que Ultralytics avaient sortie une version bien plus optimisée et performante que YOLOv4. Nous avons donc décidé de les comparer, en faisant une étude.

Pour cela, il nous fallait tout d'abord un jeu de donnée du parc, qui soit annoté pour que l'on puisse gagner du temps. Nous nous sommes donc rendus dans les locaux de Mathieu Garel, chercheur à l'OFB. Nous avons pu y récupérer les jeux de données annotés. Par la suite, nous avons pu créer un code qui nous permettait d'extraire les métadonnées des photos, et de les répertorier dans un fichier JSON.

Il faut savoir que YOLOv8 existe avec différentes tailles de modèles. Certains modèles sont très légers, mais moins précis, et d'autres plus lourds, mais donc plus précis.
Il existe 5 versions, de la plus légère à la plus lourde : N (nano), S (small), M (medium), L (large), X (extra-large).

Ensuite, nous avons fait tourner les différents modèles, et comparé les sorties des modèles aux annotations des photos, effectuées par des humains.

Nous avons donc trouvé les résultats suivants :

<img width="1080" alt="image" src="https://github.com/Attendance-PNE-OFB/docs/assets/145437462/a3dd4bad-c31f-47eb-bb7e-9cb1ecdddb52">

On s'est donc rendu compte que les dernières versions de YOLO étaient plus précises, mais surtout bien plus optimisées, avec un temps de traitement bien plus petit. Après une réunion avec les porteurs du projet, il a été décider que l'on utiliserait la version "M" de YOLOv8. Cette version permet d'atteindre une précision très bonne, tout en restant assez léger.

Une fois le modèle choisi, une partie de l'équipe s'est penchée sur la détection de la direction des passants. Pour cela, on utilise une variation du modèle de YOLOv8, qui s'appelle YOLOv8-pos, et qui permet de positionner des points du squelette sur un corps humains détecté. On retrouve ici un exemple de squelette généré par le modèle :

[image squelette modèle v8 pose]

En posant des règles sur la positions des jambes, des épaules ou encore des yeux, nous arrivons donc à déterminer la direction de chaque personne sur une photo (ce qui n'était jusqu'ici impossible).

Pendant ce temps, une autre équipe étudiait l'analyse par CLIP. Cet outil nous permettrait de déterminer le sexe des passants, leur catégorie d'âge, ou encore leur type d'activité. Des tests ont donc été effectués pour déterminer la précision de l'outil. Nous avons pu voir que pour certaines choses, comme les activités, la précision était satisfaisante, mais pour d'autres critères, tels que l'âge, la précision n'est pas assez bonne pour utiliser l'outil.

Il a fallu alors trouver une autre solution qui pourrait remplacer CLIP pour les catégories où la précision n'était pas assez bonne. Pour cela, nous avons vu qu'il existait des modèles de YOLOv8 entrainé sur différentes bases de données, avec différents objets pouvant être détectés. Jusqu'ici, nous utilisions un modèle entrainé sur la base de données COCO, qui permet de détecter 60 objets. Il existe aussi un autre modèle, cette fois ci entrainé sur la base de donnée d'OpenImages V7, une base de données de Google, qui permet de détecter plus de 600 objets.

L'avantage potentiel d'utiliser ce deuxième modèle est que parmi les objets détectés, on peut en conclure un certain type d'activité. Par exemple, si le modèle reconnait des équipements de randonnées, avec un sac à dos, on pourra en conclure que le passant fait de la randonnée. Dans le cas où le modèle détecte des roues de vélo, un vélo ou un casque de vélo, alors on pourra en conclure que le passant est un cycliste. Ainsi, en posant un certain nombre de règle, il serait possible de détecter différentes activités (randonnée, VTT, ski de randonnée).

## Gestion de projet (méthode, planning prévisionnel et effectif, gestion des risques, rôles des membres ...)

## Outils (collaboration, CD/CI ...)

En ce qui concerne les outils d'organisation, nous avons centralisé au maximum les informations. Pour cela, nous avons utilisé la fonctionnalité Projet de GitHub. Cela permet d'avoir une liste de toutes les tâches à faire, celles qui sont en cours de développement et celles terminées. Nous avons aussi la possibilité de réaliser une roadmap, ce qui permet d'ajouter une vision temporelle de nos tâches.

En ce qui concerne notre organisation, nous avons plusieurs dépôts. Un dépôt avec la documentation, sur lequel n'importe quel membre du groupe peut commit sans faire de PL.

En revanche, sur les dépôts de développement, nous avons mis en place un système de pull request, sur lequel au moins 2 membres du groupe doivent approuver la pull request avant que le commit soit effectué.

## Métriques logiciels : lignes de code, langages, performance, temps ingénieur (d'après vos journaux), la répartition des lignes de code et des commits en pourcentage entre les membres du projet ...)

## Conclusion (Retour d'expérience)
