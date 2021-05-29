# Flower-Classification-and-Recognition-Based-on-Significance-Test-and-Transfer-Learning
0529更新:

  data generator以 flower_data中的 train資料集以 8:2分割成 training, validation dataset
  
  並重新訓練原版 VGG16, Saliency VGG16
  
  在 predict部分使用 flower_data中的 valid資料集做預測, 
  
  原版 VGG16的 predict accuracy=0.5611, Saliency VGG16的 predict accuracy=0.6406
  
  並最後輸出為 confusion matrix
