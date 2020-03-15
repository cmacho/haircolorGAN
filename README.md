
# haircolorGAN

We implement a variation of the cycleGAN architecture (described in [this paper](https://arxiv.org/pdf/1703.10593.pdf)) that allows changing between multiple hair colors in portrait images. We build on the [PyTorch implementation of pix2pix and cycleGAN](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix) by [Jun-Yan Zhu](https://github.com/junyanz), [Taesung Park](https://github.com/taesung) and [Tongzhou Wang](https://ssnl.github.io/). The modified cycleGAN architecture is sketched in the following diagram. 


<img src="imgs/multiple_colors_architecture_v2.png" width="800px"/>

For more details see my [project report](https://cs230.stanford.edu/past-projects/) and [poster](https://cs230.stanford.edu/past-projects/) for the Stanford CS230 class. (hyperlinks to be updated.)

Specifically I have added the following files:

- [haircolor_gan_model.py](models/haircolor_gan_model.py) - - implements the haircolorGAN model
- [hair_dataset.py](data/hair_dataset.py) - - data loader to load images and target hair colors for training
- [hair_testmode_dataset.py](data/hair_testmode_dataset.py) - - data loader for testing with specific pairs of (image,target hair color)
- [hair_list_A.json](datasets/haircolor/hair_list_A.json), [hair_list_B.json](datasets/haircolor/hair_list_B.json) - - these contain hair color labels for images from the [CelebAMask-HQ](https://github.com/switchablenorms/CelebAMask-HQ) dataset which is used for training. The hair color labels were computed using the masks that are provided with the dataset.

I have also made modifications to the following files:

- [networks.py](models/networks.py) - - added the "SigmoidDiscriminator" discriminator architecture
- [train.py](train.py) - - made minor change in order to allow saving images multiple times per epoch during training.
- [visualizer.py](util/visualizer.py) - - disabled auto refresh for the html reports generated during training.

For more information on the code structure consider reading the [Readme of the original code base](docs/original_README_pix2pix_and_cyclegan.md) and the [Overview of Code Structure](docs/overview.md).

<img src='imgs/haircolorGAN_actress.png' width=600>

### Preparing the data

We use the [CelebAMask-HQ](https://github.com/switchablenorms/CelebAMask-HQ) dataset for training. Download the dataset by following the hyperlink. The dataset contains 30.000 images of celebrities. Please rescale all of these images so that they have a resolution of 256x256. Make sure that the filenames are 0.jpg, 1.jpg, 2.jpg etc. Then (after cloning this repo) place the images in [datasets/haircolor/images](datasets/haircolor/images). I have included three example images in that directory. 

### Training

TODO: write this section

### Testing / Using trained model to translate hair colors

TODO: write this section
