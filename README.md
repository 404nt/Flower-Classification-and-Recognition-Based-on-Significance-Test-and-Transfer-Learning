# Flower-Classification-and-Recognition-Based-on-Significance-Test-and-Transfer-Learning
0529更新:

  data generator以 flower_data中的 train資料集以 8:2分割成 training, validation dataset
  
  並重新訓練原版 VGG16, Saliency VGG16
  
  在 predict部分使用 flower_data中的 valid資料集做預測, 
  
  原版 VGG16的 predict accuracy=0.5611, Saliency VGG16的 predict accuracy=0.6406
  
  並最後輸出為 confusion matrix

0603更新:

  pytorch版本跟tensorflow版本的Alexnet跑完的結果都蠻差的,
  
  但是使用其他資料集(如 Intel Image Classification)的結果就還可以,
  
  不知道是Alexnet用在 oxford 102的問題還是其他??
  
  confusion matrix改為兩個分類, 一張是分類正確率(各類別分類)大於.5的, 另一張是分類正確率小於.5的
  
