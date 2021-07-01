# Flower Classification and Recognition Based on Significance Test and Transfer Learning 
  論文概念為使用saliency map對oxford-102花卉資料集做VGG16的遷移學習.<br>
## 0529更新:<br>
  data generator以 flower_data中的 train資料集以 8:2分割成 training, validation dataset<br>
  並重新訓練原版 VGG16, Saliency VGG16在predict部分使用 flower_data中的 valid資料集做預測,<br>
  原版 VGG16的 predict accuracy=0.5611, Saliency VGG16的 predict accuracy=0.6406, 並最後輸出為 confusion matrix<br>
## 0603更新:<br>
  pytorch版本跟tensorflow版本的Alexnet跑完的結果都蠻差的, 但是使用其他資料集(如 Intel Image Classification)的結果就還可以,<br>
  不知道是Alexnet用在 oxford 102的問題還是其他?? confusion matrix改成四類, 每類之間用類別正確率區分<br>
  ( ￣ 3￣)y▂ξ<br>
## 0604更新:<br>
  現行版本的Saliency, VGG16應該都修改完成了, 剩下AlexNet可能還可以訓練的更好一點(tensorflow api)<br>
## 0613更新:<br>
  使用pca augmentation的alexnet已經訓練完畢, 以100個epochs來說訓練結果跟不使用augmentation的alexnet差異很小<br>
  ```
    test_image=image.img_to_array(inputdata)/255
    reshape_image=np.reshape(test_image,(test_image.shape[0]*test_image.shape[1],3)) #攤平為RGB三維度
    centered_image=reshape_image-reshape_image.mean(axis=0)
    # Find 3 x 3 covariance martix
    img_cov=np.cov(centered_image, rowvar=False)
    # Get eigen values and eigen vectors
    eigen_vals, eigen_vecs=np.linalg.eigh(img_cov)
    # Get principal components[p1, p2, p3]
    sort=eigen_vals[::-1].argsort()
    eigen_vals[::-1].sort()     
    eigem_vecs=eigen_vecs[:, sort]
    pc=np.column_stack((eigen_vecs))
    rand=np.random.normal(0, 0.1, 3)
    delta=eigen_vals*rand
    add_v=np.dot(pc,delta) #隨機增強 [p1, p2, p3][α1λ1, α2λ2, α3λ3]T
    outputdata=np.zeros(shape=(test_image.shape[0],test_image.shape[1],test_image.shape[2]))
    for k in range(test_image.shape[2]):
        outputdata[:,:,k]=test_image[:,:,k]+add_v[k]#依據RGB做訊號增強
  ```
  之前嘗試使用early stopping的方式, 但後來發現預測結果不如訓練100個epochs, 為了與後續的saliency alexnet做比較想說就讓兩種都以100個epoch為準<br>
  |AlexNet|saliency AlexNet|
  |-|-|
  |下圖為alexnet訓練結果, 最終預測正確率為0.7176|下圖為saliency alexnet, 最終正確率為0.5782|
  |![image](https://i.imgur.com/jvvuX6l.jpg)|![image](https://i.imgur.com/wXKoGWQ.jpg)
## 0630更新:<br>
  |Guided Grad-CAM output|
  |-|
  |以分類最差的3類(class:4, 85, 101)來做,下方僅顯示其中3張,其他可參考(https://imgur.com/a/I4jghxm)|
  |04799|
  |![image](https://imgur.com/9GpWyU5.jpg)|
  |05677|
  |![image](https://imgur.com/Lco7wBv.jpg)|
  |07963|
  |![image](https://imgur.com/NMzYEin.jpg)|
  
