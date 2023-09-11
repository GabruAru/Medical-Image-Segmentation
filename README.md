

**DATASET**

**HyperKvasir: A Comprehensive Multi-Class Image and Video Dataset for Gastrointestinal Endoscopy**

Gastrointestinal endoscopy is a type of endoscopic procedure that allows physicians to examine the digestive system by inserting a long, flexible lighted instrument called an endoscope either through the rectum or down through the throat.
A polyp is a projecting growth of tissue from a surface in the body, usually a mucous membrane. Bowel polyps are not usually cancerous, although if they're discovered they'll need to be removed, as some will eventually turn into cancer if left untreated.
This model is capable of depicting polyp tissue for Gastrointestinal Endoscopy. 

Download dataset from here: https://datasets.simula.no/downloads/hyper-kvasir/hyper-kvasir-segmented-images.zip

**Data augmentation**

The data for training contains 1000 128*128 images, which are far not enough to feed a deep learning neural network. I use a module called ImageDataGenerator in keras.preprocessing.image to do data augmentation.

See data_preprocessing.py and train.py for detail.

**MODEL**

![u-net-architecture](https://github.com/GabruAru/Medical-Image-Segmentation/assets/84130891/067ca172-27d6-449b-9ed9-97dd0faee096)


**UNET — Network Architecture**
UNET is a U-shaped encoder-decoder network architecture, which consists of four encoder blocks and four decoder blocks that are connected via a bridge. The encoder network (contracting path) half the spatial dimensions and double the number of filters (feature channels) at each encoder block. Likewise, the decoder network doubles the spatial dimensions and half the number of feature channels.


**Training**
The model is trained for 100 epochs. Using Binary crossentropy as loss function achiving aroung 90% accuracy. Learning rate used 0.001(default for Adam).

Then model is trained further using dice coefficient as loss function achieving accuracy of 97%. And Mean IOU of around 91. Learning rate used here is 0.0001.


**How to use**

1.run data_preprocessing.py to import dataset
2. run model.py to train model 
3. run evaluation.py for reuslts


**Results**

Got good results using trained model.

![Evaluation](https://github.com/GabruAru/Medical-Image-Segmentation/assets/84130891/79ba60c4-641d-462f-b115-fd44ea082104)
![Evaluation1](https://github.com/GabruAru/Medical-Image-Segmentation/assets/84130891/ffe6bf09-819b-4e47-aa5f-06e5503ffc71)
