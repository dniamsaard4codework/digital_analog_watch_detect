# Digital watch and analog watch detection

Group 4: 

64011094   Dechathon  Niamsa-ard

64011502   Pakwan  Jintapitak

64011654   Teerapat  Ramdit

64011689   Varapatr  Kamthongvijit


Task 1 - Data Acquisition (10%)
Since we decided to create a software to detect a smart watch, the data we need would be images of a smartwatch and the normal one. According to our research, we decided to find 2 datasets: one with images of a digital watch and another one with images of an analog watch. Each of them must have a significant number of images that would be able to produce a significant value of accuracy for the model. At the same time, there must not be too many images that would result in incompetent time consumption that would directly affect throughout the processes since we planned to use the augmentation technique in order to generate more images for the training process.

Task 2 – Data Preparation (30%) - Roboflow, Cvat, MakesenseAI
We used 2 datasets including one with 889 images of a digital watch and another one with 553 images of an analog watch from the same website called “images.cv”. Next, we uploaded the datasets into Roboflow platform and started annotating them. While annotating, we found that some images are not related to the topic and some are ineffective, so we decided to organize the datasets by deleting the irrelevant images. Using Roboflow, we split the data into 3 sections: train, test, and valid. At first, we have 1,442 images in total, but since we eliminated the irrelevant images, we are left with 1,082 images. We then use an augmentation process to help increase the number of training data by the technique called “shear” with a condition of plus, minus 15 degrees both in vertical and horizontal perspectives. We agree that the best augmentation technique is “shear” because it would be the most suitable for the real world situation where the angle of the watch might not be perfect as the images in the datasets.

Task 3 – Model Training and deploy (40%) - .ipynb
From the data prepared, we created a YOLOv8 model in Roboflow platform to detect between the digital and analog watch. Then, we moved to Google Colab, starting by setting its ‘Hardware Accelerator’ as ‘Graphic Processing Unit (GPU)’. Then, we train the YOLOv8 model in Google Colab and seek for the perfect number of epochs required for our model to converge. In order to train the model in Google Colab, we load the datasets from Roboflow, import necessary libraries such as ‘ultralytics’, then set a high epoch number, waiting for the model to suggest the best number of epochs, which is where the result converged. From the model trained, we use the functions to display the performance details including confusion matrix, F1-confidence, Recall-confidence, Precision-confidence, and Precision-Recall curve. Lastly, we upload the model back into the Roboflow, and deploy the model into the Raspi board.

Task 4 – Model Inference (20%) - In any video format
The model inference is presented in a video format consisting of 5 parts including about our project, searching and browsing data step, labeling and annotation process, code explanation, hardware connection, and the inference produced by the model. We, first, talk about the overall detail of the project including a brief description of the project and the purpose. Secondly, we talked about our searching and browsing data step with details of what we did, the datasets we selected, and the reasons why we chose these datasets. Next is the step of labeling and annotation process where we briefly talked about the meaning of the annotation process and the reason why we chose to apply the augmentation technique. Then, we explain about the code and the training process such as the steps we worked on Roboflow including uploading datasets, split the data, image orientation and resizing, apply the augmentation technique, shear, and generate images to increase the number of data for the training process. We also demonstrate a way to export the YOLOv8 model from Roboflow. Before the final part, we mentioned the hardware components and a Raspi board configuration where we need to format the operating system and install the new one of Raspberry Pi (64-bit), then select the country, the language, and create the user by filling in the username and the password. Finally, the last part of the video is the inference of our project where we show the final result of when we load the model and let it detect the watch from the video captured by the camera in real-time.

References

https://www.raspberrypi.com/software/operating-systems/

https://pyimagesearch.com/2019/09/16/install-opencv-4-on-raspberry-pi-4-and-raspbian-buster/

https://pyimagesearch.com/2020/01/06/raspberry-pi-and-movidius-ncs-face-recognition/

https://www.zdnet.com/article/raspberry-pi-4-model-b-and-raspbian-buster-how-to-set-up-your-board/

https://saixiii.com/basic-shell-script/

https://github.com/SkalskiP/yolov8-live

https://www.thailand.intel.com/content/www/th/th/support/articles/000033354/boards-and-kits/neural-compute-sticks.html

https://github.com/roboflow/notebooks

https://github.com/roboflow/roboflow-python

https://www.youtube.com/watch?v=QV85eYOb7gk
