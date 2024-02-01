# Compte rendus de recherche sur YoloV8

## YoloV8 detection

### Résumé

Le modèle YoloV8 pour la detection est plus rapide et plus performant que la modele YoloV4.
Il permet de compter les éléments sur lesquels il a été entrainé.
Il est entrainé sur le dataset COCO lui aussi.
Il existe des version préentrainé disponnible qui peuvent être amélioré avec les données du parc.

La migration de YoloV4 vers YoloV8 semble donc facile et plutot recommandée.

### Résultats expérimentaux

<span style="color:red;">TODO : </span>

Sur 1000-10000 images tester YoloV4-Attendance
Sur 1000-10000 images tester YoloV8             

<span style="color:red;">Comparer les temps de predicitions, le pourcentage d'erreurs, les labels </span>



### Ouverture

Il existe un Dataset de Google OpenImageV7, qui pourrai permettre un appronfondissement de l'entrainement du modèle ?????
Entrainer le modèle sur des donnnées du parc semble aussi être une bonne idée pour améliorer la précison. Verifier cependant comment gérer les labels, doivent-il match avec ceux de COCO ?

## YoloV8 pose


### Résumé 

Permet de compter le nombre d'humains et de récupérer leurs poses sous forme de 16 points.

    NOSE:           int = 0
    LEFT_EYE:       int = 1
    RIGHT_EYE:      int = 2
    LEFT_EAR:       int = 3
    RIGHT_EAR:      int = 4
    LEFT_SHOULDER:  int = 5
    RIGHT_SHOULDER: int = 6
    LEFT_ELBOW:     int = 7
    RIGHT_ELBOW:    int = 8
    LEFT_WRIST:     int = 9
    RIGHT_WRIST:    int = 10
    LEFT_HIP:       int = 11
    RIGHT_HIP:      int = 12
    LEFT_KNEE:      int = 13
    RIGHT_KNEE:     int = 14
    LEFT_ANKLE:     int = 15
    RIGHT_ANKLE:    int = 16

**Problème, on ne connait pas l'orientation initial du capteur photo**

Il serai possible de récupérer ces points sur différentes images et de rajouter l'information "vas a droite" ou "vas au Nord" (annoter)
Affin d'entrainer un modele de type RulesTree (lib skrules) qui est capable de comparer des variables entres elle pour classifier (au lieu de valeurs seuils dans un decision tree classique). Intérogation cependant sur la capacité de ce type de modèle d'interpreter des coordonnnées.

Autre possibilitée utiliser une matrice de distances des points de la position pour faire un arbre classique. Si on prend la triangulaire supérieur cela nous donne 109 parametres par personnes.

 - Problème il faut annoter un dataset
 - Problème un arbre peu etre long a entrainer

 + Avantage potentiellement très précis
 + Améliorable avec RandomForest et Bootstrap

Il reste cependant le problème de savoir, grace a la prediction, dans quel sens réel la personne se dirige. Cela dépend d'ou est positionner le capteur sur le chemin et vers ou il fait face.

<span style="color:green;"> Note :  modèle droite/gauche ? OU modèle Nord/Sus/Est/Ouest  ? </span>

## Multi-modèle

### Idée

Au lieu d'utiliser un seul modèle qui fait tout.
Il est possible de mettre en place plusieurs modèle spécialisés pour faire certaine taches.

**Par exemple :** 

Photo -> YoloV8 detection :
- Comptage des éléments
- (optionnel) Frames des "humains"

-------------------------------------------

Photo OU Frame découpée par YoloV8 Detection -> YoloV8 Pose :
- 16 points de poses / personnes

-------------------------------------------

16 points de poses -> ClassificationTree :
- Sens de la marche de la personne concernée

**Légende :**
Input -> Modèle :
- Output1 
- Output2
- ...

## Migration vers Yolov8

yolov4-attendance a été fork sur un nouveau repo qui n'est pas encore dans l'organisation.
Le code a été modifié au minimum pour fonctionner avec YoloV8, cepednant l'outil est conçus spécialement pour être utilisé avec des données formatés du certaines manière.
Nous allons donc récupérer un jeu de données pour test et comparaison des deux modèle afin de confirmer ou non la solution de la migration.

Problèmes potentiels : 
+ Output différent entre v4 et v8
+ Classification différente au niveau de V8 (notamment sur la normalisation des images)