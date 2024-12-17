# Traffic-Sign-Classification
Use the pre-trained VGG19 model on imageNet to classify traffic signs. 

![image](https://github.com/user-attachments/assets/a695f9cb-9799-49be-9e4a-44541212ff8e)

The original dataset consists of 73,139 images across 43 classes. We have reduced the dataset size to 24,091 images by focusing solely on speed signs, which correspond to the first 9 classes. Each image has a resolution of 32x32 pixels. Both datasets can be accessed on Moodle under the names “sign.zip” and “sign_small.zip.” After loading the dataset, please split the data into training (80%) and testing (20%) sets.

Two tasks are considered in this repo:

![image](https://github.com/user-attachments/assets/3bbc0544-3b8b-4525-84ee-3557b82d7adc)


**Task 1:** Use the pre-trained VGG19 model on imageNet as a feature extraction:
1. Add a Flatten and 2 Dense layers with 1024 and 512 nodes respectively. Add some Dropout layers in between Dense layers.
2. The convolutional base is frozen during training such that its weights are not updated.
3. Compile the model with Adam optimizer and loss="categorical_crossentropy"
4. Train the model on the “train” dataset and “test” dataset for epochs =10.
5. Evaluate the model on the training and test dataset.
   - Print loss and accuracy of model for training and test datasets and compare their
accuracy.
   - The predicted results (classification label) on 5 random examples of the test dataset.
   
**Task 2:** Use the pre-trained VGG19 model on imageNet for fine-tuning:
1. Unfreeze the top 3 layers (i.e. block5_conv3, block5_conv4, and block5_pool) and then stack our custom dense layer on top of it such as step1 (Add a Flatten and 2 Dense layers with 1024 and 512 nodes respectively).
2. Repeat steps 3-5 of Task1 and then compare the training and test accuracy with the first task
