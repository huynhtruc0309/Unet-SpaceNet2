# SpaceNet2 Report
sn2_AOI_5_Khartoum dataset: https://drive.google.com/drive/folders/1-E0Qf56LnZJzwOGDRAGXLRgkHa1cT8Cx?usp=sharing

I try to solve this as an image segmentation problem and build a segmentation model which is Unet in Pytorch (based on this https://www.pyimagesearch.com/2021/11/08/u-net-training-image-segmentation-models-in-pytorch/). This report covers:

* An overview of U-Net that make it a powerful segmentation model
* Creating a custom PyTorch Dataset for our image segmentation task
* Training the U-Net segmentation model from scratch

## About Unet
* The U-Net architecture follows an encoder-decoder structure, where the encoder gradually compresses information into a lower-dimensional representation. Then the decoder decodes this information back to the original image dimension. Owing to this, the architecture gets an overall U-shape, which leads to the name U-Net.

* One of the salient features of the U-Net architecture is the skip connections, which enable the flow of information from the encoder side to the decoder side, enabling the model to make better predictions.

* As we go deeper, the encoder processes information at higher levels of abstraction. This simply means that at the initial layers, the feature maps of the encoder capture low-level details about object texture and edges, and as we gradually go deeper, the features capture high-level information about object shapes and categories.

* To segment objects in an image, both low-level and high-level information is important. For example, a change in texture between objects and edge information can help determine the boundaries of various objects. On the other hand, high-level information about the class to which an object shape belongs can help segment corresponding pixels to correct object classes they represent.

* Thus, to use both these pieces of information during predictions, the U-Net architecture implements skip connections between the encoder and decoder. This enables us to take intermediate feature map information from various depths on the encoder side and concatenate it at the decoder side to process and facilitate better predictions.

# SpaceNet 2: Building Detection v2
I chose Khartoum as it is the smallest one. Downloading them is very time-consuming, AWS made me wait for 24h in oder to be able to register for AWS CLI. 
