# Pneumonia_Classification
DS 4400 (Machine Learning and Data Mining 1) Final Project Spring 2023

<b> Title: </b> Pneumonia Classification

<b> Abstract: </b> In several sentences, summarize your project (e.g., think of a Tweet).
## Introduction:
<p> Pneumonia is a medical condition characterized by inflammation of the air sacs (alveoli) in one or both lungs, usually caused by a bacterial, viral, or fungal infection. The inflammation causes the air sacs to fill with pus or other fluid, which can make it difficult to breathe and lead to symptoms such as coughing, fever, and chest pain.  One way to detect pneumonia is through chest x-rays. A chest X-ray can help detect pneumonia by showing the inflammation and fluid buildup in the lungs. An X-ray classifier would be a helpful tool for the healthcare industry. For one, it can allow for early detection: Pneumonia can be difficult to diagnose in its early stages, as its symptoms are similar to those of other respiratory illnesses. When caught early, patient outcomes are likely to be better. Secondly, it would be an efficient diagnosis: an X-ray classifier can quickly and accurately diagnose pneumonia by analyzing chest X-rays. This can save time and resources compared to traditional diagnostic methods, such as laboratory tests, which can be time-consuming and expensive.</p>
<p> Creating an X-ray classifier is an interesting problem for many reasons. More industries are starting to take advantage of artificial intelligence and machine learning, including the healthcare industry. X-ray classifiers are already being used in healthcare and are likely to become increasingly common in the future. A recent study found that an X-ray classifier for pneumonia had an accuracy rate of 93.3%, compared to 90.3% for radiologists. We found this stat to be reflective of what the future of healthcare will look like. Working to create an X-ray classifier for pneumonia means we are working on something that is likely to be heavily used in the real world.</p>
<p> The approach we decided to take for creating an X-ray classifier for pneumonia was through neural networks. Neural networks are used in X-ray classifiers for pneumonia because they are well-suited to the task of image recognition and classification. In the case of X-ray classifiers for pneumonia, neural networks can be trained on large datasets of chest X-rays to learn how to identify the characteristic patterns and features associated with the disease. The neural network can then use this knowledge to analyze new X-ray images and classify them as either showing signs of pneumonia or not.
Neural networks are particularly effective at image recognition and classification because they can learn to identify complex patterns and relationships in data, even when those patterns are not immediately obvious to human observers. Neural networks are great for images because they can automatically extract and analyze features and patterns in image data. Images contain large amounts of complex data, and the other types of methods we learned in class may struggle to effectively analyze and classify them. By analyzing images at multiple levels of abstraction, neural networks can accurately classify images even when they contain significant variability or noise. </p>
<p> Neural networks are better than regression and tree methods for classifying images because of their ability to learn complex relationships between features in the image. Our X-rays may be in black and white but there relationships between the features can be highly nonlinear and difficult to model using traditional statistical methods like regression or decision trees. Neural networks are specifically designed to handle high-dimensional data and can learn to identify patterns and features in the data that are important for image classification. They are able to automatically extract features from the raw pixel data using convolutional layers, which are specialized layers in the neural network that learn to detect local patterns in the image. This allows the neural network to capture the most salient features of the image, regardless of their location in the image.</p>
<p> Our approach was to start by creating a simple two-layer neural network to start with and try different activation functions such as ReLU and Thanh. From here, we would pick the best one and try varying the amount of hidden layers in our model. We also decided to explore using convolutional neural networks as another approach, since CNNs are designed to handle high-dimensional data, such as images or videos. They use convolutional layers to learn local features, such as edges and textures, and pooling layers to downsample the data and reduce the number of parameters in the network. This allows them to capture the hierarchical structure of the data and make accurate predictions on complex image and video processing tasks. Lastly, we considered applying image processing on our dataset to see if our results could improve. Through filters for sharpening and blurring, we believed that we could train our dataset to better handle X-rays. However, the added noise has the potential to negatively impact our accuracy. </p>
<p> Our main limitations include computational power and the size of our dataset. Our dataset for training has about 5,000 images which will limit our accuracy. Some other limitations include interpretability and overfitting. It is difficult the interpret how our neural network is classifying our images and what is uses to detect pneumonia in the X-rays. With overfitting, we have concern since our pneumonia x-rays aren't clear and come be considered "cloudy." This might be interpreted as noise in our pictures and disrupt of model from properly learning.  </p>

## Setup:
<p> Our dataset consisted of images of X-rays where the patient didn't have pneumonia or had bacterial or viral pneumonia. We had 1,341 cases of no pneumonia patient X-rays and 3,875 cases of pneumonia X-rays in our train dataset. We had 234 cases of no pneumonia patient X-rays and 390 cases of pneumonia X-rays in our test dataset. This gave us a 10.68% test-train split. Our X-rays without pneumonia look tend to be more clear in the chest area, while X-rays with pneumonia can be considered "cloudy." However, at first glance at the images there doesn't appear to be much of a difference.</p>
<p> For our experiment we setup our neural network in python and opted to use machine learning library PyTorch since we had experience using it in our homework assignments. We setup our model in a Jupyter notebook so we wouldn't have to rerun entire files as we worked on creating our model. This helped since we didn't want to load in our images every time we made a minor change. We used a simple two-layer neural network to start with. Our first model used the ReLU activation function.  </p>

## Results:
<p>The preliminary results from our baseline model showed that we get us a 62.5% accuracy when classifying images from the test set. This model incorporates our default settings. It has initial parameters we used to reshape each image (120 pixels for image height and 160 pixels for image length), and has our default network setup (a single hidden layer and the ReLU activation function).  </p>

<p>The first parameter we chose to vary was the image reshape settings, as we wanted to determine what was the smallest image size that allows us to still get decent results. We originally decided to fix the height/length ratio as 3:4 because we found most images in our dataset fit those proportions. Further down in our analysis, we decided to shift towards using 28x28 pixels as our dimensions, as this is a standard image size to use in convolutional neural networks. </p>

<p>After making small adjustments to the model and fixing some minor bugs, our default model achieved a 71% accuracy on our test set. This original default setting had a width of 256 nodes in the hidden layer, so we thought that varying this parameter would affect the accuracy. We did find that by decreasing the number of nodes in the hidden layer to 64, we were able to get our highest test accuracy on our baseline model (78.8%)</p>

<p>Finally, we decided to look at convolutional neural networks to see if we could design an architecture that would see improved accuracy on the test set. We originally started with a single convolutional layer, varying the parameters for filter size, stride, and padding, but we saw slightly worse performance on the test set. We then decided to expand to multiple layers. The best CNN model we examined involved 3 convolutional layers, along with 2x2 average pooling. This had decent accuracy (75.4%) on the test set. Interestingly, when looking at other important metrics, the f1 score was 0.83, while the recall was 0.98. This means that the model was very confident that most patients with pneumonia were classified as such.</p>

## Discussion:
<p>These results are pretty good, but could be improved upon. While 75% accuracy is a lot better than what we started with (62%), is not yet sufficient for our task of classifying pneumonia images. We want to be as sure as possible that are model is correct in its predictions before using it in such a high-stakes real world setting (as incorrectly classifying someone could be very very costly). That said, our model did have 0.98 for recall, which means that the model successfully identified almost all the patients with pneumonia. Since this is much more important in our domain than the precision (ie. preventing healthy patients from being classified with pneumonia), we consider this to be a successful part of our model. However, we think that there exists a convolutional neural network architecture that would see very good test performance as well as improved recall and precision. </p>

## Conclusion:
<p>We have identified the problem of trying to classify between x-rays of people who have pneumonia and of those who don’t. We have determined an approach to doing this by creating a neural network that will take in as input the image and classify it as a patient that has pneumonia or not. Our default baseline model was able to classify the images with 78% accuracy. While we continued exploring with different convolutional neural network approaches, we were not able to improve the model much further. However, we can be very confident that our model will identify nearly all patients that have pneumonia, which in the context of the health care industry, is paramount.</p>

## References:
<p>Other than referencing online documentation for PyTorch and lecture notes, we did not consult any other resources for this project. </p>
