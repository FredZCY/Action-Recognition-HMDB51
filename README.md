# Action-Recognition-HMDB51
## Background

Human action recognition has been well studied and various approaches have been proposed. Traditional approaches are based on object detection, pose detection, dense trajectories, or structural information. Convolutional Neural Networks(CNN) are able to extract features from each frame and pool the features from multiple frames to achieve video-level prediction, though they fail to obtain sufficient motion information. In addition to 2D CNNs used for image processing, 3D CNNs were proposed to process videos.

Due to the ability of long-term temporal modeling, recurrent neural networks (RNN), particularly long short-term memory (LSTM), obtained outstanding results in sequence tasks, therefore an alternate technique is to use LSTM to model dynamics of frame-level data. Recent designs have concentrated on leveraging attention mechanism to pick salient parts of the video, which contributes to overcoming the constraint of LSTMs.

## Dataset
### HMDB51: a large human motion database

With nearly one billion online videos viewed everyday, an emerging new frontier in computer vision research is recognition and search in video. While much effort has been devoted to the collection and annotation of large scalable static image datasets containing thousands of image categories, human action datasets lack far behind. Here we introduce HMDB collected from various sources, mostly from movies, and a small proportion from public databases such as the Prelinger archive, YouTube and Google videos. The dataset contains 6849 clips divided into 51 action categories, each containing a minimum of 101 clips. The actions categories can be grouped in five types:

- General facial actions smile, laugh, chew, talk.
- Facial actions with object manipulation: smoke, eat, drink.
- General body movements: cartwheel, clap hands, climb, climb stairs, dive, fall on the floor, backhand flip, handstand, jump, pull up, push up, run, sit down, sit up, somersault, stand up, turn, walk, wave.
- Body movements with object interaction: brush hair, catch, draw sword, dribble, golf, hit something, kick ball, pick, pour, push something, ride bike, ride horse, shoot ball, shoot bow, shoot gun, swing baseball bat, sword exercise, throw.
- Body movements for human interaction: fencing, hug, kick someone, kiss, punch, shake hands, sword fight.

You should download the dataset from http://serre-lab.clps.brown.edu/wp-content/uploads/2013/10/hmdb51_org.rar or you can run dataset.py

To cope with the limited computational resources and speed the training, we choose 10 classes with 75 frames per video.

## Packages Installation
numpy, pandas, matplotlib, pytorch, tensorflow

Using pip to install packages via Python Library From pypi:  
```
pip install package_name
```
**For more installation information of Pytorch**  
Please click on https://pytorch.org/get-started/locally/ 


## Single-frame Approach

We used single frame classification, which trains fast, to get a baseline result. The videos are firstly split into training and test videos, and then 13 frames per video are extracted from each set respectively so that the frames in the test set are guaranteed to be from the videos unseen in the training set. We trained on a custom ConvNet and on fine-tuned VGG16 and ResNet50 models.


To train our baseline model using ResNet50, we unfroze all the layers and retrained the imagenet weights by setting ’trainable’ = True. Additionally, we set ’include-top’ = False to ensure the last layers of ResNet50 are not loaded. We found out that a learning rate of 0.005 with Adam as our optimizer led to more stable results. We performed a similar implementation using VGG16, just now we randomly initialized the weights and set ’trainable’ = False.

## LSTM Approach
<img src="https://github.com/FredZCY/Action-Recognition-HMDB51/blob/main/imgs/architecture.jpg" width="500" height="300" />
We use a mostly pretrained VGG16 architecture to process each frame. These outputs are fed to a fully connected
layer and then sent to a sequential model. We use LSTMs for our sequential model. On the test set, we get 68% accuracy.
<br/><br/>

<img src="https://github.com/FredZCY/Action-Recognition-HMDB51/blob/main/imgs/acc&loss.jpg" width="400" height="500" />

## Reference
https://github.com/pypi-ahmad/Action-Recognition-on-hmdb51_org-Dataset


https://github.com/IDKiro/action-recognition

## Contact the Author  

***Special thanks*** :pray: for the advice from  

*[Prof. Mathias Unberath](https://mathiasunberath.github.io/) 
(Assistant Professor, Computer Science, Johns Hopkins)*  


If you got any enquiries or suggestions, We're all ears :sunglasses:  

- **Institution:**  Johns Hopkins University  :mortar_board: Graduates  
- **Group Members:** Abdouh Harouna Kenfack, Chenyu Zhang, Daniel Stambler, Erix Xie
- **Academic E-mail:** aharoun1@jhu.edu, czhan146@jhu.edu, dstambl2@jhu.edu, jxie36@jhu.edu
