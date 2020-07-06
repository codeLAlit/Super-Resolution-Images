# Super-Resolution-Images

From lower resolution image to higher resolution.

For this I will be trying multiple methods. All of them are as follows:

## Using GAN

I used `mnist` dataset. First I downsampled the data to 26x26 that will act as my input (Low resolution LR images) to the model
and kept the actual 28x28 images as my ground truth (from here High Resolution HR images). The model will generate images of dimension
28x28 (Super Resolution SR images). The structure of model is not like a usual GAN.

The genrator part of the GAN is basically an Variational Autoencoder's encoder part in starting that generates a latent vector which is given as an input to the latter part that is like a usual generator. The use of reparametrization trick helps to flow the gradient back to VAE part.

The discriminator is acting on HR and SR. The loss function I used for the Generator part is a combination of reconstruction loss of HR and SR
sum with the loss of images detected as fake by discriminator.

![26](readme_assets/26.png "LR images (26x26)")

![28](readme_assets/28.png "HR images (28x28)")

Results come out to be satisfactory considering the simplicity of the model.