# aca_advanced_ml_hw13 <br>
File descriptions: <br>
Irena's part: <br>
`hw13.ipynb`, `first_model_try_hw12.h5` <- contain the first attempt at solving the problem and the corresponding saved model <br>
`hw-13_with_dropout.ipynb`, `second_model_try_hw13.h5` <- retrained model based on the first version with added dropouts and the corresponding saved model <br>
`hw13_cont_added_layersipynb`, `final_model_try_hw13.h5` <- used the model from `second_model_try_hw13.h5`, added layers, continued training and the corresponding saved model <br>

Mane's part: <br>
Initially, I tried to train NASNet, but it needed to be lighter and took a lot of time, even on 10 epochs. Thus, I terminated. Besides, I have also tried EfficientNetB0 and EfficientNetB1, but they still needed to be improved from 0.1009 accuracy three epochs on a row. Lastly, I discovered that MobileNet is a comparably suitable and light model for this classification problem; thus, I specifically took MobileNetV2 as a transformer, did fine-tuning on it, and added DNN layers with a dropout rate 0.4 to avoid overfitting. I could manage to run for 10 epochs because of source scarcity. You can see the data importing, training, and testing processes in `MobileNetV2+DNN.ipynb` . The model is saved in `MobileNetV2+DNN.h5` and later can be used by just calling it by the following code part below. 

```
#loading the model
loaded_model = tf.keras.models.load_model("MobileNetV2+DNN.h5")

```

