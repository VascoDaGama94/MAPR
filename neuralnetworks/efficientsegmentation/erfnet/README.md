# ERFNet
By combining the ideas from several high performing deep neural networks, the [Efficient Residual Factorized Network (ERFNet)](http://www.robesafe.es/personal/eduardo.romera/pdfs/Romera17tits.pdf) offers a powerful and efficient architecture for a semantic segmentation task. The researchers proposed this architecture to achieve a good trade-off between good accuracy and the necessary computational resources. At a high-level the ERFNet is a convolutional neural network (CNN) that follows am encoder-decoder architecture. This structure is often referred to as autoencoder and exemplary shown in Figure 9. Contrary to networks like UNet or SegNetwhere feature maps from different layers need to be connected to the decoders corresponding outputs using long-range skip connections, ERFNet follows a more sequential approach. The encoder component is producing a downsampled representation of the input, which the subsequent decoder is upsampling to match the input resolution. The decoder and encoder itself contain the networks inner composition, which is predominantly built out of three differentiable modules that are sequentially stacked to each other:

 - A factorized residual network module 
 - A downsampling module 
 - An upsampling module

## Efficiency Tricks used

## Results Flop Counter

## Resources
