# Action-Recognition-HMDB51

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
numpy, pandas, matplotlib, pytorch, itertools...

Using pip to install packages via Python Library From pypi:  
```
pip install package_name
```
**For more installation information of Pytorch**  
Please click on https://pytorch.org/get-started/locally/ 


## Single-frame Approach


## LSTM Approach
