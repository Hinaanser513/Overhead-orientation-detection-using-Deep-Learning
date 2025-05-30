Over-Head Orientation Detection 
In my project, we focus on determining the orientation of a person's head from above, without 
relying on facial recognition. Previous systems have primarily used facial features for head 
orientation detection, which raises privacy concerns and also have the lower accuracy when 
their is brightness, and occlusions.  
Research Questions 
• Is it feasible to detect head orientation (left, right, straight, down) from overhead images 
containing occlusions (e.g., headphones, caps) and varying lighting conditions through 
a deep learning model? 
• How can data augmentation strategies improve model robustness to occlusions and 
lighting variations? 
• What is the feasible complexity of a deep learning model for overhead orientation 
detection to achieve real-time performance on low-cost microcontrollers (e.g., ESP32) 
without compromising accuracy? 
Collection of Data 
Total dataset size=11,200 
Folder = 4 
Left = 2800 = 1200 non-occluded and 1600 occluded  
Right = 2800 = 1200 non-occluded and 1600 occluded  
Down= 2800 = 1200 non-occluded and 1600 occluded  
Straight= 2800 = 1200 non-occluded and 1600 occluded  
Data Splitting: 
You split your data into 70% training, 15% validation, and 15% test sets. This split keeps the 
same ratio of classes (left/right/straight/down) and occlusions (hats/headphones) in each set. 
This way, your model isn’t biased toward certain cases during training or testing. 
Preprocessing: 
You resize all images to 224x224 pixels because MobileNetV2 needs this size. You also 
normalize pixel values (divide by 255) to make training faster and more stable. Think of this 
like standardizing all images to a "common language" the model understands. 
Models: 
Baseline Model: Trained on your original 11,200 images. 
Augmented Model: Trained on the same images but with added variations: 
Rotation: Images randomly tilted up to 15 degrees left/right. 
Brightness: Images made slightly darker or brighter (up to 20% change). No horizontal and 
vertical flipping because it change the left and right images.
