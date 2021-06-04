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
  
  confusion matrix改成四類, 每類之間用類別正確率區分
  
  ( ￣ 3￣)y▂ξ
  
  ver2.0 更改 predict方法, 發現 generator跟直接處理的數值不相同, 等後續修改
  
0604更新:

  現行版本的Saliency, VGG16應該都修改完成了, 剩下AlexNet可能還可以訓練的更好一點(tensorflow api)
  
  
