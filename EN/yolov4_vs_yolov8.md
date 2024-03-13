### 20200709_20200802 (12 885 pictures)

#### Test with 16Go RAM, SSD, AMD Ryzen 5600H 2.28GHz, GPU RTX 3060 Mobile (Gamer PC)
| Model name | Compute time (min) | Correct classification and counting (%) 100_BTCF | Correct classification and counting (%) 101_BTCF| Correct classification and counting en moyenne(%)|
|-----------|-----------|-----------|-----------|-----------|
| yolov4   | 28'22"(1682.22sec)  | 95.2%   | 93.0%|94.67%|
| yolov8n   | 5'43"(342.83sec)   | 95.3%   | 92.6%|94.66%|
| yolov8s   | 5'46"(346.3sec)   | 94.8%   |93.1%   |94.39%|
| yolov8m   | 7'04"(424.7sec)   | 97.9%   |95.9%   |97.42%|
| yolov8l   | 7'55"(474.7sec)   | 98.2%   |96.5%   |97.81%|
| yolov8x   |   9'39"(579sec) | 98.8%   | 97.5%| 98.50%|

#### Test with 8Go de RAM, SSD, Intel I5 11eme Gen 2.4GHz (Bureaucracy PC)
| Model name | Compute time (s) | Correct classification and counting (%) 100_BTCF | Correct classification and counting (%) 101_BTCF|
|-----------|-----------|-----------|-----------|
| yolov8n   | 29'01"(1741sec)   | 95.3%   | 92.6%|

### *20200827_20200911 (2 714 images)*

#### Test with 16Go RAM, SSD, AMD Ryzen 5600H 2.28GHz, GPU RTX 3060 Mobile (Gamer PC)
| Model name | Compute time (s) | Correct classification and counting (%) |
|-----------|-----------|-----------|
| yolov4   | 5'58"(357.6sec)  | 97.5%   |
| yolov8n   | 1'12"(71.9sec)  | 97.2%   |


#### Test with 8Go RAM, SSD, Intel I5 11eme Gen 2.4GHz (Bureaucracy PC)
| Model name | Compute time (s) | Correct classification and counting (%) |
|-----------|-----------|-----------|
| yolov8n   | 6'11"(371sec)  | 97.2%   |

#### Comments
It is observed that the precision of the v4 and v8n models is very close, but it is evident that the v8n model is significantly more efficient (over 5 times faster). The v8x model is slower than the v8n, although still much faster than the v4 (3 times faster). However, its performance is significantly better.

## Conclusion
We have the option to use v8x (with the configuration we have), so we will use it. However, it might be wise to switch to lighter v8 models when using less powerful machines.
