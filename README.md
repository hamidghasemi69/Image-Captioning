# Image-Captioning
Training a CNN-RNN model to predict captions for a given image
# Project Overview: Building a CNN-RNN Network for Image Captioning
In this project, I implemented an encoder-decoder architecture using Convolutional Neural Networks (CNN) and Recurrent Neural Networks (RNN) to automatically generate captions from images. The training data used for this project is the [COCO dataset](https://paperswithcode.com/dataset/coco). 

On the encoding side, a CNN is employed to extract features from the input images, while on the decoding side, RNNs with LSTM cells are used to generate the captions. Below is a representation of the encoder-decoder architecture:





<img width="1291" alt="image_caption" src="https://github.com/hamidghasemi69/Image-Captioning/assets/22797186/23200d45-5d6c-48c2-aeb4-bf533b402714">




After, training the model, I tried to generate the captions for some new images. Below is one sample output:




<img width="376" alt="image_caption_sample" src="https://github.com/hamidghasemi69/Image-Captioning/assets/22797186/ea4e0aa1-657b-4e97-b1b0-4781e4b5f775">

