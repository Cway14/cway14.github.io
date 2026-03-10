---
title: Transfer Learning 101
date: 2026-03-09
layout: post
---

Today I fine tuned my first Neural Network using the [FastAI](https://docs.fast.ai/) library!

Recently I completed the Hugging Face Reinforcement Learning course. It was a great introduction to the world of RL, and I plan on a "Capstone" project to apply my learnings from that soon. In the meantime, I am interested in gaining a deep understanding of neural networks and modern ML techniques, so I have decided the FastAI's [Practical Deep Learning for Coders](https://course.fast.ai/) course is the best place to start. 

So far I have completed the first two lessons and have really enjoyed Jeremy's teaching style. I plan to continue along and post updates on here from time to time.

Today's model was fine tuned on the [PlantVillage Dataset](https://www.kaggle.com/datasets/abdallahalidev/plantvillage-dataset) to identify the disease of a given leaf. I used Resnet34 as the base model and performed 3 epochs of training. Surprisingly, this was enough to get 0.4% error on the validation set. Based on my experience it performs best on images that have no background since that is what is included in the training set. It would be interesting to augment the dataset with a more variable dataset, but this was a good place to start.

The full code to train the model is below. While this was an easy introduction, I am excited to get into the weeds a bit and learn what is happening under the hood. I have also deployed the model on Hugging Face Spaces, so you can play around with it if you like!

## Code
```py
# Load the Dataset
path = Path('/kaggle/input/datasets/abdallahalidev/plantvillage-dataset/color')
dls = ImageDataLoaders.from_folder(
    path, valid_pct=0.2, seed=42,
    item_tfms=Resize(192))

# Fine tune the model for 3 epochs
learn = vision_learner(dls, resnet34, metrics=error_rate)
learn.fine_tune(3)

# Save the model for later use
learn.export('plant_classifier.pkl')
```

## Demo

<iframe
    src="https://cway140-plantvillage-resnet34.hf.space"
    frameborder="0"
    width="850"
    height="650"
></iframe>
