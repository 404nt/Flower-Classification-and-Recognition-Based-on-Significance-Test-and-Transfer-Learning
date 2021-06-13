# Flower-Classification-and-Recognition-Based-on-Significance-Test-and-Transfer-Learning
##0529更新:<br>
  data generator以 flower_data中的 train資料集以 8:2分割成 training, validation dataset<br>
  並重新訓練原版 VGG16, Saliency VGG16在predict部分使用 flower_data中的 valid資料集做預測,<br>
  原版 VGG16的 predict accuracy=0.5611, Saliency VGG16的 predict accuracy=0.6406, 並最後輸出為 confusion matrix<br>
0603更新:<br>
  pytorch版本跟tensorflow版本的Alexnet跑完的結果都蠻差的, 但是使用其他資料集(如 Intel Image Classification)的結果就還可以,<br>
  不知道是Alexnet用在 oxford 102的問題還是其他?? confusion matrix改成四類, 每類之間用類別正確率區分<br>
  ( ￣ 3￣)y▂ξ<br>
0604更新:<br>
  現行版本的Saliency, VGG16應該都修改完成了, 剩下AlexNet可能還可以訓練的更好一點(tensorflow api)<br>
0613更新:<br>
  使用pca augmentation的alexnet已經訓練玩了, 以100個epochs來說訓練結果跟不使用augmentation的alexnet差異很小<br>
  ![image](https://github.com/404nt/Flower-Classification-and-Recognition-Based-on-Significance-Test-and-Transfer-Learning/blob/main/saliency_vgg16_hitroy_lr31.jpg)
  上圖為saliency vgg16在lr=0.03, momentum=0.1的訓練結果<br>
  
