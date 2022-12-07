
## 工具介紹

## 1. calculate_the_items.py

此工具是將所有Vott匯出的結果進行統計分析

### 使用方式

python calculate_the_items.py (資料夾位置) (匯出位置)

```python calculate_the_items.py D:\\VoTT_JSON\\  D:\\Auto_Calculate\\```

將所有VoTT匯出的結果放進第一個參數位置 (範例為D:\\VoTT_JSON\\)

![](https://i.imgur.com/ad4TsQI.png)



工具在分析後會將結果匯出成JSON格式放置第二個參數位置 (範例為D:\\Auto_Calculate\\)
並將其命名為 VoTT_JSON的子資料夾名稱 + _auto_calculate_the_items

![](https://i.imgur.com/h63MwJJ.png)





### 分析結果
包含每個幀數的圖片名字、標註數量、時間跟位置


## 2. compare_export_files.py

此工具主要是分析VoTT與其他模型輸出的JSON檔
並計算出Precision及Recall

### 使用方式
python compare_export_files.py (Auto_Calculate資料夾位置中某部影片的JSON檔) (模型輸出的JSON檔位置) (模型輸出的圖檔位置) (損失函數 可輸入CIoU/IoU) (是否要存照片)

```python compare_export_files.py D:\\Auto_Calculate\\Video002_auto_calculate_the_items.json C:\\darknet-master\\build\\darknet\\Yolov4_Output_Json\\Video002.json C:\\darknet-master\\build\\darknet\\Yolov4_Output_Image\\Video002\\ iou True```

第一個參數為所有VoTT匯出檔案的分析結果資料夾位置
![](https://i.imgur.com/XtuBEzk.png)

第二個參數為模型輸出的JSON檔位置
![](https://i.imgur.com/sOBsqpM.png)

第三個參數為模型輸出的圖檔位置
![](https://i.imgur.com/m0cEHWc.png)

第四個參數為選擇損失函數為CIoU或是IoU

第五個參數為是否要將VoTT的標註框放上模型輸出的圖檔上
(若為True則會放上，這部分會影響計算速度)

### 分析結果
包含每幀模型與VoTT各標註多少以及TP、FP、FN、Precision以及Recall
![](https://i.imgur.com/cKiRa85.png)

並將其結果輸出成JSON檔，放置此程式同一層的位置




