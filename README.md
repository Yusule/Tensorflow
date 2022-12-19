# Tensorflow2.3 中 自构VGG16从新开始训练模型，Loss始终不变，不收敛。
  查阅资料，得知需要对卷积层的权重初始化
  ![image](https://user-images.githubusercontent.com/120508831/208393398-93599815-8bd4-441b-adb2-fb06693c226a.png)
  Tesorflow2.3默认的初始化权重方法是均匀分布
  将tf.keras.layers.Dense(4096, activation='relu')
  改成tf.keras.layers.Dense(4096, activation='relu',kernel_initializer='he_normal')其中he_normal是正太分布问题得以解决！
