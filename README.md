# Image-captioning


### Repo structure:
<br />
`ImageCaptioning.ipynb` - main pipeline


### Recap

__Dataset__  

MSCOCO https://drive.google.com/file/d/1k5wIy4ImwaTFMqNYj0lrQYX4DBYq04QE/view?usp=sharing
<br />
Dataset consist of image embeddings (vector with dim=2048) and five captions for each image vector

<br />

__Model Definition__

![Image of Encoder-Decoder img captioning](https://miro.medium.com/max/1400/1*LMIw-ZJlKeoBSDhPc5keLg.png)

1. Encoder: Pretrained Inveption-v3. 

2. Decoder: LSTM
- Feed a <sos> (start of a sentence or a word) token to the LSMT cell as an input at time t=0.
- Find the index of the most probable character (word) at time t=0, using argmax.
- Feed the next token (next embedded word from our target, if teacher forcing) to the LSMT cell as an input at time t=1.
- Repeat until <eos> token is obtained as the output of the cell.

<br />

### References

<br />
Pytorch chatbot tutorial: https://pytorch.org/tutorials/beginner/chatbot_tutorial.html#prepare-data-for-models 
<br />
Medium post caption images with pytorch: https://medium.com/@stepanulyanin/captioning-images-with-pytorch-bc592e5fd1a3
<br />
https://guillaumegenthial.github.io/sequence-to-sequence.html
