---
title: "Evelyn Basham - Plant Disease Recognition With Neural Networks"
kind: "page"
date: "1970-01-01"
slug: "evelyn-basham-plant-disease-recognition-with-neural-networks"
permalink: "/pages/evelyn-basham-plant-disease-recognition-with-neural-networks/"
render_with_liquid: false
---
<h2>Preparation</h2>
Read: <a href="http://news.mit.edu/2015/how-brain-recognizes-objects-1005">How the brain recognizes objects</a>

Watch: <a href="https://www.youtube.com/watch?v=7HnLVYhvars">Guidelines for Diagnosing Plant Problems</a>

After watching the video, jot down a few features of plant diseases (i.e. shape, texture, etc.) that are important to their classification in your notebook.
<h2>Overview</h2>
As agriculture continues to develop into a global enterprise, so too does the spread of diseases and pests that affect plants everywhere. Unfortunately, it takes a rather trained eye to identify the particular kind of affliction a plant may experience. Even then, new diseases may arise that escape identification in that particular region. Experts in the field have identified artificial neural networks (ANNs) as capable identifiers of plant disease and pest problems.

<strong>However, this begs the question we might ask of all NNs in comparison with the human capacity to complete the same task: what features enable NNs to execute an exercise that would require years of visual training in humans?</strong>

Please ponder this question as you read Sladojevic et al., authors who present another type of NN for plant disease identification using deep convolutional neural networks (CNNs or ConvNets ). ConvNets are often used in the field for analyzing visual imagery:
<blockquote>“The architecture of a ConvNet is analogous to that of the connectivity pattern of Neurons in the Human Brain and was inspired by the organization of the Visual Cortex. Individual neurons respond to stimuli only in a restricted region of the visual field known as the Receptive Field. A collection of such fields overlap to cover the entire visual area” (Saha).</blockquote>
As you may know, pictures are treated computationally as a matrix of pixels. However, other types of neural networks, such as ANNs, do a poor job of converting those matrices into usable information. ConvNets are better at consolidating such dense information without losing the important features of the picture (Saha)! They’re better because they are able to:
<blockquote>“...extract the high-level features such as edges, from the input image...Conventionally, the first ConvLayer is responsible for capturing the Low-Level features such as edges, color, gradient orientation, etc. With added layers, the architecture adapts to the High-Level features as well, giving us a network which has the wholesome understanding of images in the dataset, similar to how we would” (Saha).</blockquote>
See the picture below demonstrating the extraction of only the most important pixel data from the larger, original image.

<img class=" size-full wp-image-3103 aligncenter" src="../../wp-content/uploads/2020/05/picture1.png" alt="Picture1" width="278" height="268">

Sladojevic et al. reveal that:
<blockquote>“The main goal for the future work will be developing a complete system consisting of server side components containing a trained model and application for smart mobile devices with features such as displaying recognized diseases in fruits, vegetables, and other plants, based on leaf images captured by the mobile phone camera. This application will serve as an aid to farmers (regardless of the level of experience), enabling fast and efficient recognition of plant diseases and facilitating the decision-making process when it comes to the use of chemical pesticides.”</blockquote>
<h2>Close Reading Assignment</h2>
<a href="http://downloads.hindawi.com/journals/cin/2016/3289801.pdf" target="_blank" rel="noopener">Sladojevic et al. - Deep Neural Networks Based Recognition of Plant Diseases by Leaf Image Classification</a>
<h2>Response</h2>
Compare and contrast the abilities of ANNs and ConvNets to mimic the human brain in your notebook. A bulleted list/diagram is fine.
<h2>Further reading/Sources</h2>
<a href="https://www.researchgate.net/publication/273525097_2015_Plant_Leaf_Recognition_using_Texture_and_Shape_features_with_Neural_Classifiers" target="_blank" rel="noopener">Chaki et al. - Plant Leaf recognition using texture and shape features with neural classifiers</a>

<a href="https://towardsdatascience.com/a-comprehensive-guide-to-convolutional-neural-networks-the-eli5-way-3bd2b1164a53" target="_blank" rel="noopener">Sumit Saha - A Comprehensive Guide to Convolutional Neural Networks — the ELI5 way</a>
