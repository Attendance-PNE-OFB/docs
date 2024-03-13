## CLIP
(pour plus de détails, voir le fichier [analyseCLIP](analyseCLIP.md))  
Meilleure combinaison : **"man", "woman", "children", "adolescent", "adult", "senior", "it's a hiker", "it's a skier", "it's a bicyclist"**
| Nom du sous_dataset | Temps de calcul (min) | Identification de sexe correct (%) | Identification de tranches d'âge correct (%) | Identification d'activité correcte (%)
|-----------|-----------|-----------|-----------|-----------|
| 101_BTCF (2911img)  | 3'29"(209sec)      | 73.9% | 51.3% | 73.6%   |
| 100_BTCF (9971img)   | 11'47"(707sec)   | 81.1% | 55.0% | 63.4%   |

## OIV7 (OpenImageV7)
Seuil 0.1 :
| Nom du sous_dataset | Identification de sexe correct (%) | Identification de tranches d'âge correct (%) | Identification d'activité correcte (%)
|-----------|-----------|-----------|-----------|
| 101_BTCF (2911img)  | 43.8% | x | 73.4%   |
| 100_BTCF (9971img)   | 40.6% | x | 73.8%   |

Seuil 0.2 :
| Nom du sous_dataset | Identification de sexe correct (%) | Identification de tranches d'âge correct (%) | Identification d'activité correcte (%)
|-----------|-----------|-----------|-----------|
| 101_BTCF (2911img)  | 37.7% | x | 65.8%   |
| 100_BTCF (9971img)   | 35.7% | x | 66.4%   |

## Conclusion
On ne peut pas comparer les temps de calcul des deux outils, car nous avons testé OIV7 dans le code de yolov8-attendance qui contient également le modèle yolov8m-pose pour déterminer les directions.
Il n'est donc pas seul modèle, ce qui empêche de comparer le temps de calcul.  
Pour l'âge, on ne peut pas sortir de chiffres non plus, car les labels de OIV7 ne couvrent que deux catégories d'âges : enfant ou adulte.
Nous ne disposons pas d'images annotées avec seulement ces deux catégories d'âges, on ne peut pas sortir de chiffres.  

Pour catégoriser le genre, OIV7 est moins bon que CLIP. Il sous compte le nombre de 'male' et de 'female' comparé à la réalité.  
Pour les activités, OIV7 est équivalent à CLIP. Il compte aussi bien le nombre de personnes qui font l'une de ces trois activités (hiking, ski/snow, vélo/vtt).

En conclusion, **utiliser CLIP serait meilleur qu'utiliser OIV7 pour faire du qualitatif**.  
Néanmoins, compte tenue de notre chaîne de travail. Nous n'utiliserons pas CLIP, car cela allongerait le temps de calcul du code final et compliquerait l'installation de l'outil, car rajoute un modèle différent de yolov8 (pose et OIV7).
