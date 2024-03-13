## CLIP
(For further details, see [CLIP_analysis](CLIP_analysis.md))  
Best combination : **"man", "woman", "children", "adolescent", "adult", "senior", "it's a hiker", "it's a skier", "it's a bicyclist"**
| Dataset name | Compute time (min) | Correct gender identification (%) | Correct age identification (%) | Correct activity identification (%)
|-----------|-----------|-----------|-----------|-----------|
| 101_BTCF (2911img)  | 3'29"(209sec)      | 73.9% | 51.3% | 73.6%   |
| 100_BTCF (9971img)   | 11'47"(707sec)   | 81.1% | 55.0% | 63.4%   |

## OIV7 (OpenImageV7)
Seuil 0.1 :
| Nom du sous_dataset | Correct gender identification (%) | Identification de tranches d'âge correct (%) | Correct activity identification (%)
|-----------|-----------|-----------|-----------|
| 101_BTCF (2911img)  | 43.8% | x | 73.4%   |
| 100_BTCF (9971img)   | 40.6% | x | 73.8%   |

Seuil 0.2 :
| Nom du sous_dataset | Correct gender identification (%) | Identification de tranches d'âge correct (%) | Correct activity identification (%)
|-----------|-----------|-----------|-----------|
| 101_BTCF (2911img)  | 37.7% | x | 65.8%   |
| 100_BTCF (9971img)   | 35.7% | x | 66.4%   |

## Conclusion
We cannot compare the computation times of the two tools because we tested OIV7 in the yolov8-attendance code, which also contains the yolov8m-pose model to determine directions. It is not the only model, which prevents us from comparing computation time.

For age classification, we cannot provide figures either because the labels in OIV7 cover only two age categories: child or adult. Since we do not have annotated images with only these two age categories, we cannot provide figures.

Regarding gender categorization, OIV7 is less accurate than CLIP. It undercounts the number of 'male' and 'female' compared to reality. For activities, OIV7 is equivalent to CLIP. It accurately counts the number of people engaging in these three activities (hiking, skiing/snowboarding, cycling/mountain biking).

In conclusion, **using CLIP would be better than using OIV7 for qualitative analysis**. However, considering our workflow, we will not use CLIP because it would lengthen the computation time of the final code and complicate the tool's installation by adding a different model from yolov8 (pose and OIV7).
