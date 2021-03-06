# Thermal to Visible Face Recognition Using Deep Autoencoders
This repository contains the implementation and the manual landmark annotations that have been used in our [BIOSIG19][3] paper "Thermal to Visible Face Recognition Using Deep Autoencoders". Our research utilizes a deep autoencoder to perform thermal to visible face recognition by constructing a visible corresponding of a thermal image as close as possible.
More details will be added and updated after the publication of the paper. For now this repository contains only the manual landmark annotations of the [Carl Dataset][1] and [EURECOM Visible and Thermal paired face database][2] which are marked by us.
## Introduction
In this research, we present a deep autoencoder based system to learn the mapping between visible and thermal face images. Also, we assess the impact of alignment in thermal to visible face recognition. U-Net based autoencoder network take visible face image as input and create the face in thermal modality. 

Authors are Alperen Kantarcı and Assoc. Dr. Hazım Kemal Ekenel. This research is also Bachelor thesis of the Alperen Kantarcı and accepted by the [BIOSIG19][3] conference. 
## Manually Labeled Facial Landmarks
Today there are lots of automatic landmark detection systems to detect facial landmarks, but there is no stable system that provides automatic landmark detection for the thermal face images. We investigated effect of the facial alignment on recognition with our proposed network. In order to make accurate alignment we manually marked six landmark of the faces. In this repository we share our manual landmark data with the community. 
### Facial Landmarks 
![Example Face](https://github.com/Alpkant/Thermal-to-Visible-Face-Recognition-Using-Deep-Autoencoders/blob/master/images/simpleface.png "Six landmarks")

We have marked six landmarks of the face. All marked landmarks saved as dlib annotation XML file for each subject. Numerated landmarks and their corresponding names are listed below. 
```python
Landmark 1 : righteye_outer
Landmark 2 : righteye_inner
Landmark 3 : lefteye_inner
Landmark 4 : lefteye_outer
Landmark 5 : mouthcorner_right
Landmark 6 : mouthcorner_left
```

You can see an example of the facial landmarks for the "imagename.bmp". Box provides a rectangle around the face but it is not utilized for cropping or anything else. Each part corresponds to a landmark point as stated above.
```
<image file='imagename.bmp'>
  <box top='9' left='46' width='72' height='91'>
    <label>unlabelled</label>
    <part name='righteye_outer' x='62' y='49'/>
    <part name='righteye_inner' x='75' y='50'/>
    <part name='lefteye_inner' x='88' y='51'/>
    <part name='lefteye_outer' x='99' y='52'/>
    <part name='mouthcorner_right' x='71' y='78'/>
    <part name='mouthcorner_left' x='87' y='79'/>
  </box>
</image>
```

For each subject we have created a XML file that contains both thermal and visible images of the subject. 
## Architecture
Architecture of the network is inspired by the [U-Net][4] which is used on medical segmentation where the training data is limited. Our problem also has limited number of training data. Because of this, we employed similar architecture to the U-Net. You can see our architecture below.
![Architecture](https://github.com/Alpkant/Thermal-to-Visible-Face-Recognition-Using-Deep-Autoencoders/blob/master/images/architecture.png)

## Citation
You can access to the publication via [this link][5].

@INPROCEEDINGS{8897222,  
author={A. {Kantarcı} and H. K. {Ekenel}},  
booktitle={2019 International Conference of the Biometrics Special Interest Group (BIOSIG)},  
title={Thermal to Visible Face Recognition Using Deep Autoencoders},  
year={2019},  
volume={},  
number={},  
pages={1-5},  
keywords={face recognition;image coding;image matching;learning (artificial intelligence);thermal face recognition;deep autoencoders;visible face recognition systems;deep learning;visible cross-domain face matching;night time surveillance;deep autoencoder;visible face images;thermal face images;annotated facial landmark positions;Convolutional neural networks;autoencoders;heterogeneous face recognition;thermal to visible matching},  
doi={},  
ISSN={1617-5468},  
}


[1]: http://splab.cz/en/download/databaze/carl-database
[2]: http://vis-th.eurecom.fr/
[3]: http://fg-biosig.gi.de/biosig-2019
[4]: https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/
[5]: https://ieeexplore.ieee.org/abstract/document/8897222
