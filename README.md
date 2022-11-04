# 关系抽取
## 1.主要环境依赖
```shell
jieba
gensim==3.8.0
tensorflow==1.14.0
keras==2.3.1
```
PS：keras2.2.4也测试过，能跑通

## 2.数据集
网上公开数据集  

词向量：https://pan.baidu.com/s/17jBo2VppJUXm4KQJB7tGJQ 提取码: tpd8

## 3.实验结果
|模型|accuracy|备注|
| :---: | :---: | :---: | 
|dgcnn+attention|0.8168||
|CasRel|0.8250||
|EfficientGlobalPointer|0.8283|相对GlobalPointer参数少|
|GlobalPointer|0.8283||

**dgcnn+attention 训练过程**
```shell
Epoch 1/120
2705/2705 [==============================] - 443s 164ms/step - loss: 0.4871
21639it [11:47, 30.61it/s]
f1: 0.5502, precision: 0.8424, recall: 0.4085, best f1: 0.5502, best precision: 0.8424, best recall: 0.4085, best epoch: 1

Epoch 2/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0812
21639it [12:49, 28.11it/s]
f1: 0.7892, precision: 0.7917, recall: 0.7866, best f1: 0.7892, best precision: 0.7917, best recall: 0.7866, best epoch: 2

Epoch 3/120
2705/2705 [==============================] - 406s 150ms/step - loss: 0.0716
21639it [12:57, 27.83it/s]
f1: 0.8010, precision: 0.7892, recall: 0.8133, best f1: 0.8010, best precision: 0.7892, best recall: 0.8133, best epoch: 3

Epoch 4/120
2705/2705 [==============================] - 406s 150ms/step - loss: 0.0679
21639it [13:01, 27.71it/s]
f1: 0.8064, precision: 0.7911, recall: 0.8223, best f1: 0.8064, best precision: 0.7911, best recall: 0.8223, best epoch: 4

Epoch 5/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0654
21639it [13:02, 27.66it/s]
f1: 0.8079, precision: 0.7895, recall: 0.8272, best f1: 0.8079, best precision: 0.7895, best recall: 0.8272, best epoch: 5

Epoch 6/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0636
21639it [13:03, 27.62it/s]
f1: 0.8092, precision: 0.7900, recall: 0.8294, best f1: 0.8092, best precision: 0.7900, best recall: 0.8294, best epoch: 6

Epoch 7/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0624
21639it [13:03, 27.63it/s]
f1: 0.8108, precision: 0.7928, recall: 0.8297, best f1: 0.8108, best precision: 0.7928, best recall: 0.8297, best epoch: 7

Epoch 8/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0615
21639it [13:02, 27.66it/s]
f1: 0.8115, precision: 0.7926, recall: 0.8312, best f1: 0.8115, best precision: 0.7926, best recall: 0.8312, best epoch: 8

Epoch 9/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0607
21639it [13:04, 27.58it/s]
f1: 0.8117, precision: 0.7924, recall: 0.8319, best f1: 0.8117, best precision: 0.7924, best recall: 0.8319, best epoch: 9

Epoch 10/120
2705/2705 [==============================] - 409s 151ms/step - loss: 0.0601
21639it [13:04, 27.59it/s]
f1: 0.8118, precision: 0.7932, recall: 0.8312, best f1: 0.8118, best precision: 0.7932, best recall: 0.8312, best epoch: 10

Epoch 11/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0599
21639it [13:05, 27.55it/s]
f1: 0.8123, precision: 0.7937, recall: 0.8318, best f1: 0.8123, best precision: 0.7937, best recall: 0.8318, best epoch: 11

Epoch 12/120
2705/2705 [==============================] - 407s 150ms/step - loss: 0.0593
21639it [13:04, 27.57it/s]
f1: 0.8117, precision: 0.7935, recall: 0.8308, best f1: 0.8123, best precision: 0.7937, best recall: 0.8318, best epoch: 11

Epoch 13/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0588
21639it [13:03, 27.61it/s]
f1: 0.8130, precision: 0.7956, recall: 0.8313, best f1: 0.8130, best precision: 0.7956, best recall: 0.8313, best epoch: 13

Epoch 14/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0585
21639it [13:06, 27.53it/s]
f1: 0.8145, precision: 0.7972, recall: 0.8326, best f1: 0.8145, best precision: 0.7972, best recall: 0.8326, best epoch: 14

Epoch 15/120
2705/2705 [==============================] - 410s 152ms/step - loss: 0.0582
21639it [13:05, 27.55it/s]
f1: 0.8139, precision: 0.7978, recall: 0.8307, best f1: 0.8145, best precision: 0.7972, best recall: 0.8326, best epoch: 14

Epoch 16/120
2705/2705 [==============================] - 409s 151ms/step - loss: 0.0581
21639it [13:06, 27.52it/s]
f1: 0.8136, precision: 0.7962, recall: 0.8318, best f1: 0.8145, best precision: 0.7972, best recall: 0.8326, best epoch: 14

Epoch 17/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0576
21639it [13:06, 27.52it/s]
f1: 0.8140, precision: 0.7974, recall: 0.8313, best f1: 0.8145, best precision: 0.7972, best recall: 0.8326, best epoch: 14

Epoch 18/120
2705/2705 [==============================] - 409s 151ms/step - loss: 0.0574
21639it [13:05, 27.55it/s]
f1: 0.8138, precision: 0.7958, recall: 0.8327, best f1: 0.8145, best precision: 0.7972, best recall: 0.8326, best epoch: 14

Epoch 19/120
2705/2705 [==============================] - 411s 152ms/step - loss: 0.0574
21639it [13:04, 27.57it/s]
f1: 0.8132, precision: 0.7955, recall: 0.8318, best f1: 0.8145, best precision: 0.7972, best recall: 0.8326, best epoch: 14

Epoch 20/120
2705/2705 [==============================] - 407s 150ms/step - loss: 0.0571
21639it [13:05, 27.55it/s]
f1: 0.8146, precision: 0.7981, recall: 0.8316, best f1: 0.8146, best precision: 0.7981, best recall: 0.8316, best epoch: 20

Epoch 21/120
2705/2705 [==============================] - 407s 150ms/step - loss: 0.0568
21639it [13:06, 27.53it/s]
f1: 0.8141, precision: 0.7981, recall: 0.8308, best f1: 0.8146, best precision: 0.7981, best recall: 0.8316, best epoch: 20

Epoch 22/120
2705/2705 [==============================] - 407s 151ms/step - loss: 0.0567
21639it [13:06, 27.51it/s]
f1: 0.8144, precision: 0.7970, recall: 0.8326, best f1: 0.8146, best precision: 0.7981, best recall: 0.8316, best epoch: 20

Epoch 23/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0565
21639it [13:06, 27.53it/s]
f1: 0.8152, precision: 0.7976, recall: 0.8337, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 24/120
2705/2705 [==============================] - 406s 150ms/step - loss: 0.0561
21639it [13:07, 27.49it/s]
f1: 0.8142, precision: 0.7978, recall: 0.8313, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 25/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0562
21639it [13:05, 27.54it/s]
f1: 0.8141, precision: 0.7963, recall: 0.8328, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 26/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0560
21639it [13:07, 27.47it/s]
f1: 0.8146, precision: 0.7974, recall: 0.8326, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 27/120
2705/2705 [==============================] - 407s 150ms/step - loss: 0.0558
21639it [13:05, 27.53it/s]
f1: 0.8144, precision: 0.7961, recall: 0.8335, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 28/120
2705/2705 [==============================] - 406s 150ms/step - loss: 0.0555
21639it [13:06, 27.50it/s]
f1: 0.8145, precision: 0.7977, recall: 0.8321, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 29/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0554
21639it [13:07, 27.48it/s]
f1: 0.8146, precision: 0.7969, recall: 0.8331, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 30/120
2705/2705 [==============================] - 407s 151ms/step - loss: 0.0556
21639it [13:06, 27.50it/s]
f1: 0.8141, precision: 0.7966, recall: 0.8323, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 31/120
2705/2705 [==============================] - 407s 151ms/step - loss: 0.0553
21639it [13:08, 27.45it/s]
f1: 0.8145, precision: 0.7971, recall: 0.8326, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 32/120
2705/2705 [==============================] - 407s 150ms/step - loss: 0.0552
21639it [13:05, 27.53it/s]
f1: 0.8148, precision: 0.7977, recall: 0.8327, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 33/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0549
21639it [13:07, 27.49it/s]
f1: 0.8149, precision: 0.7983, recall: 0.8322, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 34/120
2705/2705 [==============================] - 409s 151ms/step - loss: 0.0550
21639it [13:07, 27.48it/s]
f1: 0.8152, precision: 0.7971, recall: 0.8341, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 35/120
2705/2705 [==============================] - 412s 152ms/step - loss: 0.0547
21639it [13:04, 27.58it/s]
f1: 0.8148, precision: 0.7975, recall: 0.8328, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 36/120
2705/2705 [==============================] - 411s 152ms/step - loss: 0.0547
21639it [13:05, 27.56it/s]
f1: 0.8149, precision: 0.7991, recall: 0.8314, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 37/120
2705/2705 [==============================] - 411s 152ms/step - loss: 0.0547
21639it [13:07, 27.47it/s]
f1: 0.8145, precision: 0.7980, recall: 0.8318, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 38/120
2705/2705 [==============================] - 408s 151ms/step - loss: 0.0546
21639it [13:08, 27.46it/s]
f1: 0.8149, precision: 0.7972, recall: 0.8334, best f1: 0.8152, best precision: 0.7976, best recall: 0.8337, best epoch: 23

Epoch 39/120
2705/2705 [==============================] - 406s 150ms/step - loss: 0.0541
21639it [13:06, 27.51it/s]
f1: 0.8160, precision: 0.7989, recall: 0.8339, best f1: 0.8160, best precision: 0.7989, best recall: 0.8339, best epoch: 39

Epoch 40/120
2705/2705 [==============================] - 412s 152ms/step - loss: 0.0542
21639it [13:08, 27.43it/s]
f1: 0.8168, precision: 0.8008, recall: 0.8333, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 41/120
2705/2705 [==============================] - 410s 151ms/step - loss: 0.0543
21639it [13:06, 27.51it/s]
f1: 0.8154, precision: 0.7991, recall: 0.8325, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 42/120
2705/2705 [==============================] - 409s 151ms/step - loss: 1.0974
21639it [04:54, 73.56it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 43/120
2705/2705 [==============================] - 408s 151ms/step - loss: 1.6967
21639it [04:54, 73.59it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 44/120
2705/2705 [==============================] - 411s 152ms/step - loss: 1.6974
21639it [04:54, 73.55it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 45/120
2705/2705 [==============================] - 410s 152ms/step - loss: 1.6994
21639it [04:54, 73.48it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 46/120
2705/2705 [==============================] - 409s 151ms/step - loss: 1.6975
21639it [04:53, 73.84it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 47/120
2705/2705 [==============================] - 407s 151ms/step - loss: 1.6990
21639it [04:53, 73.68it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 48/120
2705/2705 [==============================] - 410s 152ms/step - loss: 1.6951
21639it [04:53, 73.72it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 49/120
2705/2705 [==============================] - 410s 151ms/step - loss: 1.6965
21639it [04:53, 73.72it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 50/120
2705/2705 [==============================] - 408s 151ms/step - loss: 1.6986
21639it [04:53, 73.66it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

...

Epoch 118/120
2705/2705 [==============================] - 409s 151ms/step - loss: 1.6964
21639it [04:54, 73.52it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 119/120
2705/2705 [==============================] - 411s 152ms/step - loss: 1.6982
21639it [04:53, 73.69it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40

Epoch 120/120
2705/2705 [==============================] - 409s 151ms/step - loss: 1.6984
21639it [04:53, 73.75it/s]
f1: 0.0000, precision: 1.0000, recall: 0.0000, best f1: 0.8168, best precision: 0.8008, best recall: 0.8333, best epoch: 40
```

**CasRel 训练过程**
```shell
Epoch 1/20
5410/5410 [==============================] - 2691s 497ms/step - loss: 0.0717
f1: 0.79055, precision: 0.79120, recall: 0.78990: : 21639it [16:12, 22.24it/s]
f1: 0.79055, precision: 0.79120, recall: 0.78990, best f1: 0.79055

Epoch 2/20
5410/5410 [==============================] - 2653s 490ms/step - loss: 0.0381
f1: 0.80928, precision: 0.80305, recall: 0.81560: : 21639it [16:07, 22.37it/s]
f1: 0.80928, precision: 0.80305, recall: 0.81560, best f1: 0.80928

Epoch 3/20
5410/5410 [==============================] - 2650s 490ms/step - loss: 0.0334
f1: 0.81776, precision: 0.81226, recall: 0.82333: : 21639it [16:05, 22.40it/s]
f1: 0.81776, precision: 0.81226, recall: 0.82333, best f1: 0.81776

Epoch 4/20
5410/5410 [==============================] - 2651s 490ms/step - loss: 0.0303
f1: 0.82229, precision: 0.81685, recall: 0.82781: : 21639it [16:05, 22.42it/s]
f1: 0.82229, precision: 0.81685, recall: 0.82781, best f1: 0.82229

Epoch 5/20
5410/5410 [==============================] - 2650s 490ms/step - loss: 0.0277
f1: 0.82341, precision: 0.81666, recall: 0.83027: : 21639it [16:06, 22.39it/s]
f1: 0.82341, precision: 0.81666, recall: 0.83027, best f1: 0.82341

Epoch 6/20
5410/5410 [==============================] - 2655s 491ms/step - loss: 0.0255
f1: 0.82499, precision: 0.81830, recall: 0.83180: : 21639it [16:05, 22.42it/s]
f1: 0.82499, precision: 0.81830, recall: 0.83180, best f1: 0.82499

Epoch 7/20
5410/5410 [==============================] - 2643s 489ms/step - loss: 0.0235
f1: 0.82426, precision: 0.81764, recall: 0.83099: : 21639it [16:07, 22.37it/s]
f1: 0.82426, precision: 0.81764, recall: 0.83099, best f1: 0.82499

Epoch 8/20
5410/5410 [==============================] - 2643s 489ms/step - loss: 0.0217
f1: 0.82331, precision: 0.81636, recall: 0.83038: : 21639it [16:08, 22.34it/s]
f1: 0.82331, precision: 0.81636, recall: 0.83038, best f1: 0.82499

Epoch 9/20
5410/5410 [==============================] - 2650s 490ms/step - loss: 0.0200
f1: 0.82305, precision: 0.81507, recall: 0.83119: : 21639it [16:07, 22.38it/s]
f1: 0.82305, precision: 0.81507, recall: 0.83119, best f1: 0.82499

Epoch 10/20
5410/5410 [==============================] - 2649s 490ms/step - loss: 0.0186
f1: 0.82288, precision: 0.81355, recall: 0.83244: : 21639it [16:08, 22.35it/s]
f1: 0.82288, precision: 0.81355, recall: 0.83244, best f1: 0.82499

Epoch 11/20
5410/5410 [==============================] - 2645s 489ms/step - loss: 0.0171
f1: 0.82305, precision: 0.81452, recall: 0.83176: : 21639it [16:06, 22.39it/s]
f1: 0.82305, precision: 0.81452, recall: 0.83176, best f1: 0.82499

Epoch 12/20
5410/5410 [==============================] - 2648s 489ms/step - loss: 0.0159
f1: 0.82051, precision: 0.80977, recall: 0.83154: : 21639it [16:08, 22.35it/s]
f1: 0.82051, precision: 0.80977, recall: 0.83154, best f1: 0.82499

Epoch 13/20
5410/5410 [==============================] - 2649s 490ms/step - loss: 0.0146
f1: 0.82061, precision: 0.81070, recall: 0.83077: : 21639it [16:07, 22.37it/s]
f1: 0.82061, precision: 0.81070, recall: 0.83077, best f1: 0.82499

Epoch 14/20
5410/5410 [==============================] - 2648s 489ms/step - loss: 0.0136
f1: 0.81937, precision: 0.80916, recall: 0.82985: : 21639it [16:03, 22.47it/s]
f1: 0.81937, precision: 0.80916, recall: 0.82985, best f1: 0.82499
```

**EfficientGlobalPointer 训练过程**
```shell
Epoch 1/20
5410/5410 [==============================] - 3042s 562ms/step - loss: 13.5090 - efficient_global_pointer_1_loss: 2.8575 - efficient_global_pointer_2_loss: 5.2922 - efficient_global_pointer_3_loss: 5.3594
f1: 0.77869, precision: 0.80637, recall: 0.75284: : 21639it [10:16, 35.09it/s]
f1: 0.77869, precision: 0.80637, recall: 0.75284, best f1: 0.77869

Epoch 2/20
5410/5410 [==============================] - 2986s 552ms/step - loss: 6.1360 - efficient_global_pointer_1_loss: 1.8759 - efficient_global_pointer_2_loss: 2.0507 - efficient_global_pointer_3_loss: 2.2094
f1: 0.80937, precision: 0.80713, recall: 0.81163: : 21639it [10:12, 35.35it/s]
f1: 0.80937, precision: 0.80713, recall: 0.81163, best f1: 0.80937

Epoch 3/20
5410/5410 [==============================] - 2995s 554ms/step - loss: 5.3247 - efficient_global_pointer_1_loss: 1.6737 - efficient_global_pointer_2_loss: 1.7492 - efficient_global_pointer_3_loss: 1.9018
f1: 0.81784, precision: 0.81337, recall: 0.82236: : 21639it [10:09, 35.49it/s]
f1: 0.81784, precision: 0.81337, recall: 0.82236, best f1: 0.81784

Epoch 4/20
5410/5410 [==============================] - 2988s 552ms/step - loss: 4.8440 - efficient_global_pointer_1_loss: 1.5365 - efficient_global_pointer_2_loss: 1.5785 - efficient_global_pointer_3_loss: 1.7290
f1: 0.82257, precision: 0.81682, recall: 0.82840: : 21639it [10:11, 35.36it/s]
f1: 0.82257, precision: 0.81682, recall: 0.82840, best f1: 0.82257

Epoch 5/20
5410/5410 [==============================] - 2991s 553ms/step - loss: 4.4799 - efficient_global_pointer_1_loss: 1.4270 - efficient_global_pointer_2_loss: 1.4558 - efficient_global_pointer_3_loss: 1.5970
f1: 0.82554, precision: 0.81902, recall: 0.83218: : 21639it [10:09, 35.49it/s]
f1: 0.82554, precision: 0.81902, recall: 0.83218, best f1: 0.82554

Epoch 6/20
5410/5410 [==============================] - 2989s 552ms/step - loss: 4.1618 - efficient_global_pointer_1_loss: 1.3259 - efficient_global_pointer_2_loss: 1.3493 - efficient_global_pointer_3_loss: 1.4866
f1: 0.82724, precision: 0.81909, recall: 0.83556: : 21639it [10:10, 35.44it/s]
f1: 0.82724, precision: 0.81909, recall: 0.83556, best f1: 0.82724

Epoch 7/20
5410/5410 [==============================] - 2988s 552ms/step - loss: 3.8914 - efficient_global_pointer_1_loss: 1.2392 - efficient_global_pointer_2_loss: 1.2604 - efficient_global_pointer_3_loss: 1.3918
f1: 0.82825, precision: 0.81852, recall: 0.83821: : 21639it [10:09, 35.49it/s]
f1: 0.82825, precision: 0.81852, recall: 0.83821, best f1: 0.82825

Epoch 8/20
5410/5410 [==============================] - 2990s 553ms/step - loss: 3.6428 - efficient_global_pointer_1_loss: 1.1576 - efficient_global_pointer_2_loss: 1.1773 - efficient_global_pointer_3_loss: 1.3080
f1: 0.82811, precision: 0.81964, recall: 0.83677: : 21639it [10:11, 35.38it/s]
f1: 0.82811, precision: 0.81964, recall: 0.83677, best f1: 0.82825

Epoch 9/20
5410/5410 [==============================] - 2981s 551ms/step - loss: 3.4166 - efficient_global_pointer_1_loss: 1.0859 - efficient_global_pointer_2_loss: 1.1036 - efficient_global_pointer_3_loss: 1.2271
f1: 0.82766, precision: 0.81852, recall: 0.83701: : 21639it [10:09, 35.48it/s]
f1: 0.82766, precision: 0.81852, recall: 0.83701, best f1: 0.82825
```

**GlobalPointer 训练过程**
```shell
Epoch 1/20
2022-10-30 19:40:03.157069: I tensorflow/stream_executor/platform/default/dso_loader.cc:42] Successfully opened dynamic library libcublas.so.10
5410/5410 [==============================] - 3283s 607ms/step - loss: 16.8845 - global_pointer_1_loss: 2.9306 - global_pointer_2_loss: 6.8529 - global_pointer_3_loss: 7.1011
f1: 0.79092, precision: 0.77262, recall: 0.81012: : 21639it [10:25, 34.59it/s]
f1: 0.79092, precision: 0.77262, recall: 0.81012, best f1: 0.79092

Epoch 2/20
5410/5410 [==============================] - 3235s 598ms/step - loss: 5.7271 - global_pointer_1_loss: 1.8365 - global_pointer_2_loss: 1.8593 - global_pointer_3_loss: 2.0313
f1: 0.80930, precision: 0.78945, recall: 0.83018: : 21639it [10:19, 34.93it/s]
f1: 0.80930, precision: 0.78945, recall: 0.83018, best f1: 0.80930

Epoch 3/20
5410/5410 [==============================] - 3232s 597ms/step - loss: 5.0877 - global_pointer_1_loss: 1.6489 - global_pointer_2_loss: 1.6392 - global_pointer_3_loss: 1.7995
f1: 0.81772, precision: 0.80023, recall: 0.83600: : 21639it [10:18, 34.97it/s]
f1: 0.81772, precision: 0.80023, recall: 0.83600, best f1: 0.81772

Epoch 4/20
5410/5410 [==============================] - 3235s 598ms/step - loss: 4.6568 - global_pointer_1_loss: 1.5148 - global_pointer_2_loss: 1.4944 - global_pointer_3_loss: 1.6476
f1: 0.82255, precision: 0.80544, recall: 0.84041: : 21639it [10:21, 34.83it/s]
f1: 0.82255, precision: 0.80544, recall: 0.84041, best f1: 0.82255

Epoch 5/20
5410/5410 [==============================] - 3230s 597ms/step - loss: 4.3107 - global_pointer_1_loss: 1.4035 - global_pointer_2_loss: 1.3810 - global_pointer_3_loss: 1.5262
f1: 0.82538, precision: 0.80959, recall: 0.84179: : 21639it [10:20, 34.88it/s]
f1: 0.82538, precision: 0.80959, recall: 0.84179, best f1: 0.82538

Epoch 6/20
5410/5410 [==============================] - 3237s 598ms/step - loss: 4.0215 - global_pointer_1_loss: 1.3076 - global_pointer_2_loss: 1.2872 - global_pointer_3_loss: 1.4267
f1: 0.82689, precision: 0.81052, recall: 0.84392: : 21639it [10:20, 34.85it/s]
f1: 0.82689, precision: 0.81052, recall: 0.84392, best f1: 0.82689

Epoch 7/20
5410/5410 [==============================] - 3236s 598ms/step - loss: 3.7503 - global_pointer_1_loss: 1.2189 - global_pointer_2_loss: 1.1976 - global_pointer_3_loss: 1.3338
f1: 0.82707, precision: 0.80935, recall: 0.84559: : 21639it [10:20, 34.89it/s]
f1: 0.82707, precision: 0.80935, recall: 0.84559, best f1: 0.82707

Epoch 8/20
5410/5410 [==============================] - 3223s 596ms/step - loss: 3.4988 - global_pointer_1_loss: 1.1355 - global_pointer_2_loss: 1.1152 - global_pointer_3_loss: 1.2481
f1: 0.82834, precision: 0.81203, recall: 0.84533: : 21639it [10:22, 34.77it/s]
f1: 0.82834, precision: 0.81203, recall: 0.84533, best f1: 0.82834

Epoch 9/20
5410/5410 [==============================] - 3228s 597ms/step - loss: 3.2743 - global_pointer_1_loss: 1.0619 - global_pointer_2_loss: 1.0421 - global_pointer_3_loss: 1.1703
f1: 0.82733, precision: 0.81051, recall: 0.84487: : 21639it [10:20, 34.87it/s]
f1: 0.82733, precision: 0.81051, recall: 0.84487, best f1: 0.82834

Epoch 10/20
5410/5410 [==============================] - 3230s 597ms/step - loss: 3.0584 - global_pointer_1_loss: 0.9876 - global_pointer_2_loss: 0.9742 - global_pointer_3_loss: 1.0965
f1: 0.82718, precision: 0.81076, recall: 0.84427: : 21639it [10:19, 34.95it/s]
f1: 0.82718, precision: 0.81076, recall: 0.84427, best f1: 0.82834

Epoch 11/20
5410/5410 [==============================] - 3230s 597ms/step - loss: 2.8617 - global_pointer_1_loss: 0.9251 - global_pointer_2_loss: 0.9075 - global_pointer_3_loss: 1.0290
f1: 0.82627, precision: 0.80974, recall: 0.84348: : 21639it [10:19, 34.94it/s]
f1: 0.82627, precision: 0.80974, recall: 0.84348, best f1: 0.82834

Epoch 12/20
5410/5410 [==============================] - 3229s 597ms/step - loss: 2.6766 - global_pointer_1_loss: 0.8626 - global_pointer_2_loss: 0.8485 - global_pointer_3_loss: 0.9655
f1: 0.82754, precision: 0.81202, recall: 0.84366: : 21639it [10:20, 34.87it/s]
f1: 0.82754, precision: 0.81202, recall: 0.84366, best f1: 0.82834
```
