# 关系抽取
## 1.主要环境依赖
```shell
jieba
gensim==3.8.0
tensorflow==1.14.0
keras==2.3.1
```

## 2.数据集
网上公开数据集

## 3.实验结果
|模型|accuracy|备注|
| :---: | :---: | :---: | 
|dgcnn+attention|||
|CasRel|0.8250||
|EfficientGlobalPointer|0.8283|相对GlobalPointer参数少|
|GlobalPointer|0.8283||

CasRel 训练过程
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

EfficientGlobalPointer 训练过程
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

GlobalPointer 训练过程
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
