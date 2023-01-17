# Self-service Checkout Classification Problem

* Ívar Karl Bjarnason 
* Helgi Freyr Sigurgeirsson 
* Stefán Ásgeir Arnarsson
* Joao Martins 

## Problem Description

You are provided with some photos from Krónan of a customer using the self-service check-out. Your task is to analyze the images and answer the following questions:

1. Why is this an interesting classification problem?
2. What is the instance space?
3. What are the concepts c(x)?
4. What hypothesis h(x) can we use?
5. What is the target distribution D?
6. What is the oracle EX[c,D]?
7. How do we measure the error?
8. How can we take this project further?

## Answers

### **Why is this an interesting classification problem?**
This is an interesting multi class classification problem with many possibilities of real world implementations, such as this one or for example being able to search through photo sets by classes that the images represent or help identify abnormalities in medical images.

### **What is the instance space?**
We can think of the instance space as the supermarket products that are then transposed as the possible compositions of images, specifically the color value of each pixel in the images that the camera at the self-checkout captures, but more generally we can think of it as the shape and color on the image, perhaps as well as the measured weight of the item.

### **What are the concepts c(x)?**
The concepts could then be the products sold at the supermarket for example specific vegetables or fruit that certain images form, for example images of a butternut squash (a composition of pixels in the shape and color of butternut squash) with certain weights (for example as here weighing 1.215 kg) that form the concept butternut squash. For products with barcodes the concept is primarily labeled based on the barcode. When you scan the barcode, the system knows the weight from their database and confirms if it is the right concept on the second scale. 

### **What hypothesis h(x) can we use?**
The hypotheses that we can use are the compositions of the images that the self-checkout camera captures and weight and whether they are considered to estimate the target concept, an apple-shaped, apple-red object weighing 0.170 kg represents an apple, or at least is deemed most likely to represent a red apple or an red onion etc.

### **What is the target distribution D?**
The target distribution would be the probability of a certain fruit or vegetable to be measured at the self-checkout which would not be uniformly distributed as they are not all equally likely to be measured at the self-checkout but rather dependent on the demand and sales of the fruits and vegetables.

### **What is the oracle EX[c,D]?**
The oracle could be a procedure within the self-checkout system that can be called while the learning algorithm is learning a concept c and returns a labeled example of an instance, image that has been labeled as specific fruit or a vegetable, drawn randomly according to sales numbers.

### **How do we measure the error?**
We could measure the error according to the selection made by the customer after measuring the item, whether the customer selects the label chosen for the measured item. We assume that the options given on the screen are given with certain probabilities, the 6-12 labeled deemed most likely to correspond to the item measured in descending order from the left. Therefore the label given with the highest probability for the ginger is incorrectly classified as potatoes in bulk or in the case of the scallion where no positively labeled option is offered so the customer must manually select the correct label, which shows that the given hypotheses disagree with the target concept.

### **How can we take this project further?**
If we wanted to take this problem further we could try to understand the likelihood of products selling together or we could let the self-checkout algorithm know that a particular person is at the checkout so it could make suggestions based on previous purchases. 

The first one would be a version of a machine learning algorithm that predicts and learns what products are likely to sell together and it should reduce errors. It would not override the existing technology but when in doubt it could help make the right suggestion by adding weight to products more likely to be bought together with previously scanned items. 

The second one could help in the same way. Customers could use a loyalty card giving them a discount or store credit while collecting data about their purchase history. With the customer's purchase history we would have a different more representative probability distribution than the general one from total sales numbers which would help determining the scanned product more accurately.
