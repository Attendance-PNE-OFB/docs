### 20200709_20200802 (12 885 images)

| Nom du modèle + dataset + seuil | Temps de calcul (min) | Classifications humaines correctes et comptages corrects (%) 100_BTCF | Classifications humaines correctes et comptages corrects (%) 101_BTCF| Classifications humaines correctes et comptages corrects en moyenne(%)|
|-----------|-----------|-----------|-----------|-----------|
| yolov8m COCO 0.10  | 7'12"(434.4sec)   | 90.0%   |91.7%   |90.9%|
| yolov8m OpenImageV7 0.10 | 11'3" (663.3sec)   | 98.6%   |95.8%   |97.2%|
| yolov8m COCO 0.20  | 7'22"(444.5sec)   | 98.8%   |99.0%   |98.9%|
| yolov8m OpenImageV7 0.20 | 11'9"(666.2sec)   | 87.6%   |85.0%   |86.3%|
| yolov8m COCO 0.30  | +/-7'15 (435s)   | 95.6%   |93.6%   |94.6%|
| yolov8m OpenImageV7 0.30 | 11'4"(664.5sec)   | 73.5%   |70.3%   |71.9%|
| yolov8m COCO 0.40  | +/-7'15 (435s)   | 91.2%   |90.0%   |90.6%|
| yolov8m OpenImageV7 0.40 | +/-11' (660s)  | 52.7%   |48.9%   |50.8%|
| yolov8m COCO 0.50  | +/-7'15 (435s)   | 87.2%   |85.8%   |86.5%|
| yolov8m OpenImageV7 0.50 | +/-11' (660s)   | 30.0%   |26.4%   |28.2%|
| yolov8m COCO 0.60  | +/-7'15 (435s)   | 83.0%   |81.0%   |82.0%|
| yolov8m OpenImageV7 0.60 | +/-11' (660s)   | 11.9%   |9.2%   |10.6%|
| yolov8m COCO 0.70  | +/-7'15 (435s)   | 76.9%   |74.5%   |75.7%|
| yolov8m OpenImageV7 0.70 | +/-11' (660s)   | 1.5%   |0.68%   |1.1%|
| yolov8m COCO 0.80  | +/-7'15 (435s)   | 65.7%   |63.1%   |64.4%|
| yolov8m COCO 0.90  | +/-7'15 (435s)   | 26.2%   |23.8%   |25.0%|

## Conclusion
Selon le dataset d'entraînement (COCO ou OpenImageV7), le seuil de confiance du modèle influe différemment sur le pourcentage de bonnes classifications.  
Le meilleur ensemble pour le modèle yolov8m est le dataset d'entraînement COCO avec un seuil de 0.20.  
Néanmoins, comme la différence, est très faible avec l'ensemble OpenImageV7 et seuil de 0.10. Nous avons décidé d'utiliser comme ensemble de base dans notre code, cet ensemble-là, car le dataset d'entraînement OpenImageV7 permet de classifier plus en détail nos images avec notamment les équipements de randonnée, le genre des personnes, et autres.
