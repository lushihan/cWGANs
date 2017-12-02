# Conditional Wasserstein GANs

This is an implementation of conditional GANS using the Improved Wasserstein (WGAN-GP) method.
Currently I'm trying it out on multiple datasets, though Celeba has been the main target.

### Results
These are some results generated by taking random attribute values from the Celeba test set.

Attributes in consideration: bald, bangs, black hair, blond hair, eyeglasses, heavy makeup, male, pale skin, smiling

| Image         | Attributes    |
|:-------------:|:-------------:|
| ![g1](https://i.imgur.com/lGnnXzq.png) | Male, Smiling  |
| ![g2](https://i.imgur.com/zfAfNI8.png) | Female, Blonde |
| ![g3](https://i.imgur.com/51rzV8s.png) | Female, Heavy Makeup |
| ![g4](https://i.imgur.com/rCYeDw2.png) | Female, Heavy Makeup, Smiling |

Male attribute while alternating the others
![m1](https://i.imgur.com/cB0Qqee.png)

![m2](https://i.imgur.com/Cr2uq05.png)

Female attribute while alternating the others
![f1](https://i.imgur.com/2QQgRmV.png)

![f2](https://i.imgur.com/lCiujc3.png)


### Interpolation results

#### On just z
These are interpolating between two different z vectors but using the same y (same attributes).
![i1](https://i.imgur.com/Ca6nRZt.png)

![i2](https://i.imgur.com/7sxwx1a.png)

![i3](https://i.imgur.com/PaDw1RV.png)

#### On just y

This shows interpolation between four faces (four corners) using random attributes for each face,
and interpolating between the attributes as well.

![i4](https://i.imgur.com/q13bJL3.png)


### How to run
1. Download the cropped and aligned celebA dataset from [here](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html)
as well as the annotations.

2. Your folder layout must be like so:
```
root_celeba/
   img_align_celeba/
   img_align_celeba_cropped/
   list_attr_celeba.txt
```

3. Run the crop script on the downloaded images. `img_align_celeba_cropped/` is an empty folder made by you.
Then copy the `ops/crop_images.py` file to your `root_celeba/` folder and run

   `python crop_images.py`
