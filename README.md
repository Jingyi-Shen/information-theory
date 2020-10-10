# information-theory-in-ML

## deep learning for statistical inference
* Conditional Independence Testing
  * Estimating total variation distance between two distribution
  * Distance measure estimation using classifier

* Estimating Information
  * Estimating Kullback-Leibler Distance
  * Information bottleneck and deep learning
  * Conditional mutual information estimation (Plays vital role in controlling bias or privacy)


## Information theory for deep learning
* GAN based generative models
  * Parametric models (e.g. mixture of Gaussians) fail on complex data
  * Non-parametric models (e.g. KDE, Nearest Neighbor) fail in high dimensions
  * GAN loss: Cross-Entropy loss; f-divergence; Wasserstein distance 
    * Mode Collapse collectively refers to the lack of diversity in the generated samples.
    * One weakness of GAN is that the latent variable Z has no interpretable meaning. e.g, infoGAN



## Learn the underlying Distribution of the data
Use cases
1. Sampling (GAN)
2. Prediction
3. De-noising 
4. Compression
    * We can use the Log-loss (Cross-entropy loss) to learn p<sub>X</sub>(X)


## ML for lossy compression 
• Why use ML?
1. Unclear, high-dimensional data models. Eg: natural images.
2. Unclear Loss functions for lossy compression
3. EG: Image Compression → ”Human perception loss”

• Lots of very different types of techniques used. The core idea is:
1. Learn a ”smooth” representation for the Image (key to good lossy compression)
2. Quantize the representation
3. Entropy coding of the representation

Different techniques used for compression: Autoencoders, VAE, GANs

[stanford slides](https://web.stanford.edu/class/ee376a/files/kedar_slides.pdf)







    

