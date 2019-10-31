# APTOS-Diabetic-Retinopathy
My first Deep Learning Competition. Involves classifying images of eyes in one the categories of Diabetic Retinopathy. It is multiclass classification problem. My basic workflow was training in one kernel and inference over the test set in another kernel. I shall include the inference kernel once the competition is over. I have uploaded my final private leaderboard rank image. I secured 296th position out of 2987 candidates.

1. Initally, I used DenseNet-121 and ResNet50 for comparison. I did the basic img color conversion from BGR to RGB and resized the image to         256*256 size. I used the basic data augmentation from ImageDataGenerator namely, zoom_range, horizontal_flip, rotation_range and vertical       flip. DenseNet proved to be better than ResNet50. 

2.  Many images had lot of black unnecessary background. I saw one kernel applying cropping image algorithm. Basically, some threshold was         defined. All pixels in an image with intensity lesser than that threshold were removed . I used that preprocessing, same data augmentation     as before and used DenseNet-121, EfficientNet B4 and EfficientNet B5. EfficientNet B5 came out to be the best. 

3.   Now, I apply heavy data augmentation using  imgaug library. Apparently, heavy data augmentation didn't help. 

4. I applied GaussianBlur to enhance image to some extent. It improved my score by 0.6 percent. 

5. In DataAugmentation, I changed zoom range from 0.15 to 0.3 and my LB (LeaderBoard) increased from 0.754 to 0.778. It was quite significant jump in LB. 

6. I changed zoom range from 0.3 to 0.45. LB increased from 0.778 to 0.788. It seems that the images in test set are really zoomed out. 
7. I trained on Old competition data with around 35000 images. Thenn finetuned the model on new data. Butmy score didn't improve. I tried various augmentations as well as preprocessing but nothing helped. 
8. Only using new data, I had got 4-5 submissions in the range of 0.795. Blending two of them gave me a boost to 0.805 in public LB. I submitted it for final score. 
9. The shakeup in the competition was huge. From the beginning itself it was clear that as CV amd LB are far away, the train test distribution is very different. Neverthelss, I dropped only 22 places and secured 311th position. There were many whose models overfit and they dropped down by more than 100 places. 
