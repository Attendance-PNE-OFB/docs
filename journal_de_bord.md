# Journal de bord

## 29/01 (demi-journée)
Lecture approfondie du sujet, explications par Aurélien du contexte et des outils.

## 30/01
Préparation de questions pour affiner les priorités dans le sujet du projet.  
Réunion avec le PNE & Mathieu Garel, mise au point des priorités du projet ainsi qu'un éclaircissement sur le contenu.

## 31/01
- Travail sur le benchmark d'outils déjà existant, coup d'œil sur la plateforme huggingface, le support de la présentation de Mathieu au séminaire de Toulouse.
Début d'analyse de l'outil CLIP, envoi mail à Vincent Miele à propos de son thésard -> confidentiel.
J'ai alors commencé à faire moi même quelques tests sur l'outil, à voir s'il est adapté à notre cas d'usage, car à première vue, ce n'est pas sûr.
- Premières expérimentations sur YoloV8, rédaction d'un markdown de compte-rendus sur les pistes trouvées et les expérimentation a faire.
- Planification de la tentative de fork et migration de YoloV4-Attendance et YoloV8 pour vérification de la pertinence de la solution.
- Début création d'un script pour définir l'orientation des humains

## 01/02 (demi-journée)

- Redaction des questions et pistes trouvés par Lony pour Mathieu Garel. (IAE)
- CLIP n'est pas adapté à notre cas d'usage, pour les explications voir le benchmark
- Continue le script d'orientation

## 02/02

- Rencontre avec Mathieu Garel dans les locaux de l'OFB. Récupération des données et discussion autour des pistes envisagées
- Travail sur CLIP pour essayer de faire plusieurs classifications successives avec différents critères à chaque fois pour réduire le problème du nombre de prompts
- Test du modèle d'orientation avec des photos du site + optimisation
- Comparaison de rapidité de calcul entre YoloV4 et YoloV8, YoloV8 est plus rapide d'un facteur 3. Et ce, pour le plus gros modèle de YoloV8 (le 'X').
- Pour la prochaine fois, redigier les tests complet et faire une comparaison de précision entre les deux modèles.
- Commencement d'un script python d'extraction des métadonnées des photos, afin de pouvoir vérifier les prédictions du modèle.

## 05/02 (demi-journée)
- Travail sur le code qui sort en output la classification par image (pour Yolov4)
- Création du template de comparaison de modèle
- Test sur images du site les directions + cleaning
- Reprise du code Yolov4-attendance pour faire un output de classificatiobn par image, reste a adpater pour Yolov8.
- Fin du code d'extraction des métadonnées, avec l'ajout d'un fichier JSON de sortie, plus propre.

## 06/02
- Inspection des cas d'erreurs de la prédiction des directions
- Correction et ajout de fonctionnalités sur la partie extraction de métadonnées (les activités d'hiver (ski, ski rando, snowboard, ...) sont à rajouter)
- Rédaction du code de comparaison des modèle
- Rédaction du code pour tester l'efficacité de CLIP
- Fin d'implémentation du code d'extraction des données classifié par images de YoloV8
- Comparaison sur le premier dataset (12K images) entre Yolov4, Yolov8n, Yolov8x
- Rédaction du comparatif entre les différents modèles sur un même jeu de données
- Optimisation des codes à planifier

## 07/02 (demi-journée)
- Fin des test avec CLIP
- Mise à jour du cahier des charges
- Réalisation d'une matrice SWOT
- Réalisation d'une matrice de prévention des risques
- Réalisation d'un tableau de mitigation des risques
- Première préparation pour la réunion checkpoint avec les pistes à explorer et à proposer

## 08/02 (demi-journée)
- Analyse des labels du dataset de Google pour voir ce qu'on pourrait en tirer
- Process des modèles pour continuer des comparaisons
- Préparation de la réunion de demain

## 09/02
- Fin comparaison yolov4 et yolov8
- Mise au propre des labels du dataset de Google
- Fin préparation de la réunion pour cet aprem
- Réunion avec le PNE & l'OFB
- Distribution et préparation des tâches pour la semaine prochaine

## 12/02 (demi-journée)
- Analyse de CLIP sur le singulier/pluriel, la taille des phrases et l'ordre
- Début prospection LoRaWAN
- Début comparaison du modèle yolov8m entrainé sur COCO et OpenImageV7

## 13/02
- Point avec Emmanuelle Trehoust vis à vis de la gestion de projet (30min)
- Fin de l'analyse du modèle yolov8m avec dataset COCO et OpenImageV7 + seuils
- Continuation sur la prospection LoRaWAN
- Début correction et optimisation du code de yolov8_attendance
- Optimisation et mise au propre du code de comparaison de modèles
- Commencement de la detection d'activité en fonction des classification de Yolov8m - OIV7

## 14/02 (demi-journée)

## 15/02 (demi-journée)

## 16/02
