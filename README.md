# Object-Tracking
Object Tracking Fundamentals

- locates object in motion, (one or multiple objects) over time in a video sequence,
- Goal - to establish a consistent trajectory of the objects across frames, despite chnages in appearance, occulsions.

  1. Object Detection -
 
  - Initial Detection - Object tracking usally starts with object detection, where objects of interest are identified in the first frame of a video.
  - Techniques like YOLO, Faster RCNN, SSD are used.
  - Detection in subsequent frames, objects are detected in every frame, and tracking involves matching these detections over time.
 
  2. Tracking Algorithms -
  -  1. Point Tracking -
        1.1 kalman Filtering - statistical algorithm used for predicting the state of a moving object based on prior motion.
        - It assumes linear motion and gaussian noise, making it suitable for simple tracking scenarios.
        1.2 Particle Filetr -
          - they can handle non-linear filters, non-gaussian scenarios.
          - They use a set of "particles" to present the distribution of the object's state.

  - 2. Kernel based tracking -
       - 2.1 Mean - shift Tracking - this algorithm tracks an object by iteratively shifting a search window towards the mode/ peak of the object's probability distribution, typically based on color histograms.
       - 2.2 Cam shift -  (Continuously Adaptive Mean-Shift): An extension of Mean-Shift, it adapts the search window size and orientation based on the tracked object’s scale and rotation.

  - 3. Contour Tracking -
       - 1. Optical flow - this method estimates the motion of pixels between consecutive frames, which can be used to track object contours.
            - Lucas kanade and farneback are popular optical flow algorithms.
           
 - 4. Template Matching -
     - This approach involves creating a template of the object from the first frame and sliding it over subsequent frames to find the best match. It's suitable for tracking objects with relatively stable appearance.
  
- 5. Deep learning based approach -
     - Recurrent Neural Networks (RNNs): RNNs can model the temporal dependencies in a sequence of frames, making them suitable for tracking objects that change over time.
    
### Data Association - 
Data Association is crucial in multi-object tracking, where the algorithm must decide which detected objects correspond to which tracked objects. Techniques like the Hungarian algorithm or IoU (Intersection over Union) matching are commonly used.

-  Real-World Applications:
Object tracking is used in various applications, including surveillance, autonomous driving, human-computer interaction, sports analytics, and video editing.

- Object tracking is challenging due to factors like:
- Changes in Object Appearance: Due to lighting, scale, and orientation changes.
- Occlusions: When the object is partially or fully obscured.
- Complex Backgrounds: Where objects might blend into the background.
- Multiple Objects: Requiring accurate tracking of each object.

#### Example Workflow:
- Initialization: Detect objects in the first frame using a pre-trained object detector.
- Tracking: Use a tracking algorithm (e.g., Kalman Filter, Mean-Shift) to predict the object’s location in subsequent frames.
- Correction: Adjust predictions based on new observations (detections) in each frame.
- Re-Identification: If an object is lost (due to occlusion), attempt to re-identify it when it reappears.


### DeepSORT (Simple Online and Realtime Tracking): An algorithm that incorporates both motion (from Kalman filters) and appearance (using a CNN-based feature extractor) to track objects robustly.

- Multiple Object Tracking (MOT): A system designed to track multiple objects simultaneously, often using techniques like DeepSORT.


### DeepSORT Overview DeepSORT (Simple Online and Realtime Tracking with a Deep Association Metric).
- This method is widely used for tracking multiple objects, combining the speed of traditional tracking algorithms with the robustness of deep learning-based appearance models.
- 
how deepsort works ?

- 
