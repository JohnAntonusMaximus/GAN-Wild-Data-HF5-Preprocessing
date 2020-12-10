# Generative Adversarial Networks - In The Wild Data

[![Tensorflow](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT7b9ZDD7lMdkByT-f_RCAqSQYqnq_CpgD16IFrwfmUwWCmdt7H)](https://www.tensorflow.org/beta/guide/effective_tf2)


[![Colab](https://camo.githubusercontent.com/52feade06f2fecbf006889a904d221e6a730c194/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667)](https://colab.research.google.com/drive/1ThZp9ZXVPykZR94r4pjy4pv9XtcPUnPn?usp=sharing)

## Background

Generative Adversarial Networks, or GANs for short, are an approach to generative modeling using deep learning methods, such as convolutional neural networks.

Generative modeling is an unsupervised learning task in machine learning that involves automatically discovering and learning the regularities or patterns in input data in such a way that the model can be used to generate or output new examples that plausibly could have been drawn from the original dataset.

GANs are a clever way of training a generative model by framing the problem as a supervised learning problem with two sub-models: the generator model that we train to generate new examples, and the discriminator model that tries to classify examples as either real (from the domain) or fake (generated). The two models are trained together in a zero-sum game, adversarial, until the discriminator model is fooled about half the time, meaning the generator model is generating plausible examples.

GANs are an exciting and rapidly changing field, delivering on the promise of generative models in their ability to generate realistic examples across a range of problem domains, most notably in image-to-image translation tasks such as translating photos of summer to winter or day to night, and in generating photorealistic photos of objects, scenes, and people that even humans cannot tell are fake.

[![GANS Model](https://i.imgur.com/0vuUsY0.png)]()


## Approach

In this example, I created a GAN network to work on a german dataset of clothing. The data was preprocessed and saved as a HF5 file using TFTransform and GAPCV. That pre-processed file can be downloaded here:

https://drive.google.com/file/d/1WLyKrWk8sjrRvpghmbgU5ZisdChTSa0J/view?usp=sharing

Data format:
```
[
    {
        'url': string
        'description': string
    }
...
]
```

The H5 file can be used to stream the structured data in mini batches for training large datasets, which helps when datasets become too large to fit into memory. Since this dataset is small (8700 images), I just loaded it straight into memory and used the train_on_batch method. 

If you wanted to do this with stream training, you'd need to use the "fit" method and change the '1's and '0's tensors to match the shape of the expected target.  

You can find some photos that the network generated labeled by the epoch number in the gan_images folder. 

# Links

* [KaizenTek](http://www.kaizentek.io) - IT Consulting & Cloud Professional Services