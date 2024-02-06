### 20200709_20200802 (12 885 images)

#### Test avec 16Go de RAM, SSD, AMD Ryzen 5600H 2.28GHz, GPU RTX 3060 Mobile (PC Gamer)
| Nom du modèle | Temps de calcul (min) | Classifications correctes et comptages corrects (%) 100_BTCF | Classifications correctes et comptages corrects (%) 101_BTCF|
|-----------|-----------|-----------|-----------|
| yolov4   | 28'22"(1682.22sec)  | 95.2%   | 93.0%|
| yolov8n   | 5'43"(342.83sec)   | 95.3%   | 92.6%|
| yolov8x   |   9'39"(579sec) | 98.8%   | 97.5%| 

#### Test avec 8Go de RAM, SSD, Intel I5 11eme Gen 2.4GHz (PC Bureautique)
| Nom du modèle | Temps de calcul (s) | Classifications correctes et comptages corrects (%) 100_BTCF | Classifications correctes et comptages corrects (%) 101_BTCF|
|-----------|-----------|-----------|-----------|
| yolov8n   | 29'01"(1741sec)   | 95.3%   | 92.6%|

### *20200827_20200911 (2 714 images)*

#### Test avec 16Go de RAM, SSD, AMD Ryzen 5600H 2.28GHz, GPU RTX 3060 Mobile (PC Gamer)
| Nom du modèle | Temps de calcul (s) | Classifications correctes et comptages corrects (%) |
|-----------|-----------|-----------|
| yolov4   | Ligne 1   | Ligne 1   |
| yolov8n   | Ligne 2   | Ligne 2   |

#### Test avec 8Go de RAM, SSD, Intel I5 11eme Gen 2.4GHz (PC Bureautique)
| Nom du modèle | Temps de calcul (s) | Classifications correctes et comptages corrects (%) |
|-----------|-----------|-----------|
| yolov8n   | 6'11"(371sec)  | Ligne 2   |

#### Commentaires
On remarque que la précision des modèles v4 et v8n sont très proches, mais on observe bien que le modèle v8n est beaucoup plus performant (plus de 5x plus rapide). Le v8x est plus lent que le v8n, même si toujours bien plus rapide que le v4 (3x plus rapide). Sa performance est par contre bien meilleure.

## Conclusion
On a les possibilités d'utiliser du v8x (avec la configuration que l'on a) donc on va l'utiliser, mais il peut être judicieux de passer sur des modèles du v8 plus léger lorsque l'on utilise des machines moins performantes