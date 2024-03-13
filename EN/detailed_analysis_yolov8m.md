### 20200709_20200802 (12 885 images)

| Name of the model + dataset + threshold | Compute time (min) | Correct human classifications and accurate counts (%) 100_BTCF | Correct human classifications and accurate counts (%) 101_BTCF| Mean correct human classifications and accurate counts (%)|
|-----------|-----------|-----------|-----------|-----------|
| yolov8m COCO 0.10  | 7'12"(434.4sec)   | 90.0%   |91.7%   |90.9%|
| yolov8m OpenImageV7 0.10 | 11'3" (663.3sec)   | 98.6%   |95.8%   |97.2%|
| yolov8m COCO 0.20  | 7'22"(444.5sec)   | 98.8%   |99.0%   |98.9%|
| yolov8m-pose COCO 0.20  | -   | 96%   |99.1%   | 97.6% |
| yolov8m OpenImageV7 0.20 | 11'9"(666.2sec)   | 87.6%   |85.0%   |86.3%|
| yolov8m COCO 0.30  | +/-7'15 (435s)   | 95.6%   |93.6%   |94.6%|
| yolov8m-pose COCO 0.30  | -   | 97.9%   |95.1%   | 96.5% |
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
According to the training dataset (COCO or OpenImageV7), the confidence threshold of the model has different effects on the percentage of correct classifications.

For the YOLOv8m model, the best combination is the COCO training dataset with a threshold of 0.20. However, since the difference is very slight compared to the OpenImageV7 dataset with a threshold of 0.10, we have decided to use the latter as the base dataset in our code. This decision was made because the OpenImageV7 training dataset allows for more detailed classification of our images, including hiking equipment, gender of individuals, and other attributes.
