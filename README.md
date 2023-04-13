# Pneumonia_Classification
DS 4400 (Machine Learning and Data Mining 1) Final Project Spring 2023

<b> Title: </b> Pneumonia Classification

<b> Abstract: </b> In several sentences, summarize your project (e.g., think of a Tweet).
1. Introduction:
<p> Pneumonia is a medical condition characterized by inflammation of the air sacs (alveoli) in one or both lungs, usually caused by a bacterial, viral, or fungal infection. The inflammation causes the air sacs to fill with pus or other fluid, which can make it difficult to breathe and lead to symptoms such as coughing, fever, and chest pain.  One way to detect pneumonia is through chest x-rays. A chest X-ray can help detect pneumonia by showing the inflammation and fluid buildup in the lungs. An X-ray classifier would be a helpful tool for the healthcare industry. For one, it can allow for early detection: Pneumonia can be difficult to diagnose in its early stages, as its symptoms are similar to those of other respiratory illnesses. When caught early, patient outcomes are likely to be better. Secondly, it would be an efficient diagnosis: an X-ray classifier can quickly and accurately diagnose pneumonia by analyzing chest X-rays. This can save time and resources compared to traditional diagnostic methods, such as laboratory tests, which can be time-consuming and expensive.</p>
<p> Creating an X-ray classifier is an intesting problem for many reasons. More industries are starting to take advantage of artificial intelligence and machine learning including the healthcare industry. X-ray classifiers are already being used in healthcare and are likely to become increasingly common in the future. A recent study found that an X-ray classifier for pneumonia had an accuracy rate of 93.3%, compared to 90.3% for radiologists. We found this stat to be reflective of what the future of healthcare will look like. Working to create an X-ray classifier for pneumonia means we are working on something that is likely to be heavily used in the real world.</p>
<p> The approach we decided to take for creating an X-ray classifier for pneumonia was through neural networks. Neural networks are used in X-ray classifiers for pneumonia because they are well-suited to the task of image recognition and classification. In the case of X-ray classifiers for pneumonia, neural networks can be trained on large datasets of chest X-rays to learn how to identify the characteristic patterns and features associated with the disease. The neural network can then use this knowledge to analyze new X-ray images and classify them as either showing signs of pneumonia or not.
Neural networks are particularly effective at image recognition and classification because they can learn to identify complex patterns and relationships in data, even when those patterns are not immediately obvious to human observers. Neural networks are great for images because they can automatically extract and analyze features and patterns in image data. Images contain large amounts of complex data, and the other types of methods we learned in class may struggle to effectively analyze and classify them. By analyzing images at multiple levels of abstraction, neural networks can accurately classify images even when they contain significant variability or noise. </p>
<p> Neural networks are better than regression and tree methods for classifying images because of their ability to learn complex relationships between features in the image. Our X-rays may be in black and white but there relationships between the features can be highly nonlinear and difficult to model using traditional statistical methods like regression or decision trees. Neural networks are specifically designed to handle high-dimensional data and can learn to identify patterns and features in the data that are important for image classification. They are able to automatically extract features from the raw pixel data using convolutional layers, which are specialized layers in the neural network that learn to detect local patterns in the image. This allows the neural network to capture the most salient features of the image, regardless of their location in the image.</p>
<p> Our approach was to start by creating a simple two-layer neural network to start with and try different activation functions such as ReLU and Thanh. From here we would pick the best one and try adding more hidden layers to our model. We also wanted to  </p>


Documentation:

	1. Introduction: Summarize your project report in several paragraphs.
		a. What is the problem? For example, what are you trying to solve? Describe the motivation.
		
		b. Why is this problem interesting? Is this problem helping us solve a bigger task in some 			way? Where would we find use cases for this problem?
		c. What is the approach you propose to tackle the problem? What approaches make sense for 		this problem? Would they work well or not? Feel free to speculate here based on what we 		taught in class.
		d. Why is the approach a good approach compared with other competing methods? For 			example, did you find any reference for solving this problem previously? If there are, how does 		your approach differ from theirs?
		e. What are the key components of my approach and results? Also, include any specific 			limitations.
	2. Setup: Set up the stage for your experimental results.
		a. Describe the dataset, including its basic statistics.
		b. Describe the experimental setup, including what models you are going to run, what 			parameters you plan to use, and what computing environment you will execute on.
		c. Describe the problem setup (e.g., for neural networks, describe the network structure that 		you are going to use in the experiments).
	3. Results: Describe the results from your experiments.
		a. Main results: Describe the main experimental results you have; this is where you highlight 		the most interesting findings.
		b. Supplementary results: Describe the parameter choices you have made while running the 		experiments. This part goes into justifying those choices.
	4. Discussion: Discuss the results obtained above. If your results are very good, see if you could 	compare them with some existing approaches that you could find online. If your results are not as 	good as you had hoped for, make a good-faith diagnosis about what the problem is.
	5. Conclusion: In several sentences, summarize what you have done in this project.
	6. References: Put any links, papers, blog posts, or GitHub repositories that you have borrowed 	from/found useful here.
