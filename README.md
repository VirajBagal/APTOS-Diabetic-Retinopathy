# APTOS-Diabetic-Retinopathy
My first Deep Learning Competition. Involves classifying images of eyes in one the categories of Diabetic Retinopathy. It is multiclass classification problem. My basic workflow was training in one kernel and inference over the test set in another kernel. I shall include the inference kernel once the competition is over. 

1. Initally, I used DenseNet-121 and ResNet50 for comparison. I did the basic img color conversion from BGR to RGB and resized the image to         256*256 size. I used the basic data augmentation from ImageDataGenerator namely, zoom_range, horizontal_flip, rotation_range and vertical       flip. DenseNet proved to be better than ResNet50. 

2.  Many images had lot of black unnecessary background. I saw one kernel applying cropping image algorithm. Basically, some threshold was         defined. All pixels in an image with intensity lesser than that threshold were removed . I used that preprocessing, same data augmentation     as before and used DenseNet-121, EfficientNet B4 and EfficientNet B5. EfficientNet B5 came out to be the best. 

3.   Now, I apply heavy data augmentation using  imgaug library. Apparently, heavy data augmentation didn't help. 

4. I applied GaussianBlur to enhance image to some extent. It improved my score by 0.6 percent. 

5. In DataAugmentation, I changed zoom range from 0.15 to 0.3 and my LB (LeaderBoard) increased from 0.754 to 0.778. It was quite significant jump in LB. 

6. I changed zoom range from 0.3 to 0.45. LB increased from 0.778 to 0.788. It seems that the images in test set are really zoomed out. 
