In this project we basically focus on producing a model which can recognize  hand gestures in order to control mouse and keyboard operation for each gesture. 

The gestures we trained are as given in the image below.

![Signs](data/0,1,2,3.jpg) basically we have taken 4 gestures OK,STOP,JUMP & HELLO. And Stores them in a 4 different classes.

# Steps of building this project

### 1. The first Step of building this project was of creating the folders for storing the training and testing data. As, in this project we have built our own dataset.
 We have all the libraries in the requirement mentioned then simply runned the  collect_imgs.py file to take images of our  desired hand gestures. If you want to take more than 4 gestures then you need to edit the 7th line :
number_of_classes = 4
dataset_size = 250
and set your desired number of classes you want to classify. To start collect the images simply pressed the 'Q' key  and then again pressed 'Q' key  to create another image folder and follow same. Then all the images stored on data folder like:
Data----
 |
 |--0---
     |
     |-------1.jpg
     |--------2.jpg
     |………….
     |---------250.jpg
|
|---1—
      |
      |-----1.jpg
      |------2.jpg
      |…………..
      |------250.jpg
………………..
……………….. etc

## 2. The second step, after the folder creation is of creating the training and testing dataset.

Now we have runned create_dataset.py file to create a dataset using medipipe which takes the landmarks of hands and converts the images from BGR2RGB format as mediapipe works with RGB values and stores them in data.pickle file

## 3. The third step, after creating the dataset we need to create a model and train the model
 
 To build the model we runned the train_classifier where we have splitted the dataset into 80% for training and remaining 20% for testing. To remove the overfitting problem we used Random Forest Classifier and creates model.p file.

 ## 4. After Finishing the model training, we have tested real-time evaluation of our model

 There have inference_classifier file which is used to recognize the hand gesture and gives accouracy up to 96% for all.

 Then we have mouse.py file for the mouse opearations.
   •	if the recognized gesture is ‘JUMP’ works as 'Back', it simulates the keyboard press of the spacebar using pyautogui.
   •	If the gesture is 'STOP' works as ‘Option’, it simulates a right-click action pyautogui.
   •	If the gesture is 'OK' works as‘Open’, it simulates a double-click action pyautogui.
   •	If the gesture is 'Hello'works as ‘Free’, it moves the mouse cursor to the position of the hand, and moves the cursor quickly to follow the hand’s movement action pyautogui.

And we have another file for multiple hand detection named multiplehand.py, which detects gestures from multiple hand.
And lastly we have gamejump.py file which is mainly used for keyboard space bar press. And using this we have played the dino jump game and it perfectly works.

## 5. To terminate the project we have to press 'Q' key 