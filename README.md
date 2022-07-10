# StyleGAN3-Anime
A StyleGAN3 model trained on the danbooru2019 portraits dataset using [vision-aided GAN](https://github.com/nupurkmr9/vision-aided-gan). Sponsored by Runpod

I trained using vanilla StyleGAN3 up to 900 kimg, at which point I switched to vision-aided GAN for the remainder of training.

## Download
[11100 kimg](https://drive.google.com/file/d/1rsKrF4x4fh6kBgyKi8Mn6u9E5sWSoIcS/view)

## Using it
As I trained using vision-aided GAN, you cannot use this model with vanilla StyleGAN3 without some modifications, I made these modifications already [here](https://github.com/Expl0dingCat/stylegan3-modified). You could also use [vision-aided GAN's StyleGAN3](https://github.com/nupurkmr9/vision-aided-gan/tree/main/stylegan3)

## Training notebook
Used with RunPod's Pytorch pod. [Download](https://drive.google.com/file/d/1Rf2ASfuxRwW5rKWt2da6jdWViMQC8-ys/view)

## Training configuration
### StyleGAN3

Notes: 
- s/kimg & GPU mem are with vision-aided GAN.

| Config      | s/kimg (A6000)   | GPU mem | Options                                                                                |
|-------------|------------------|---------|----------------------------------------------------------------------------------------|
| StyleGAN3-T | 54.84            | 11.50   | `--cfg=stylegan3-t --gpus=4 --batch=32 --gamma=6 --dlr=0.001 --glr=0.001 --aug=noaug`  |
### Vision-aided GAN

Note: If you are going to resume training you need to use these parameters or you will get a module not found error.

```
--cv=input-clip+dino+vgg+face_normals+face_seg-output-conv_multi_level+conv_multi_level+conv+conv+conv \
--cv-loss=multilevel_sigmoid_s+multilevel_sigmoid_s+sigmoid_s+sigmoid_s+sigmoid_s \
--warmup=0
```


## Acknowledgements
Gwern Branwen, Anonymous, & The Danbooru Community; “Danbooru2019 Portraits: A Large-Scale Anime Head Illustration Dataset”, 2019-03-12. Web. Accessed 2022-06-19 https://www.gwern.net/Crops#danbooru2019-portraits

An anonymous friend who helped me with configuration and showed me vision-aided GAN

