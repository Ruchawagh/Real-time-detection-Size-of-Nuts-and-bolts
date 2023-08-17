# Measure size of Nuts/Bolts in an image for Intelligent spanner using OpenCV 

The project provides a script to read an image and based on the dimensions of a reference object find the dimensions of other objects in a scene. The reference object must be the leftmost object in the scene. In sample images given, a box of dimension 2cm x 2cm is taken as a reference object.

For any other reference object provide actual width of the object. (change line 59 in file 'init.py')

### Constraints
1. Shadow effect: use dark braground
2. Object boundry: use contrasting background


## Algorithm
1. Image pre-processing
  - Read an image and convert it it no grayscale
  - Blur the image using Gaussian Kernel to remove un-necessary edges
  - Edge detection using Canny edge detector
  - Perform morphological closing operation to remove noisy contours

2. Object Segmentation
  - Find contours
  - Remove small contours by calculating its area (threshold used here is 100)
  - Sort contours from left to right to find the reference objects
  
3. Reference object 
  - Calculate how many pixels are there per metric (centi meter is used here)

4. Compute results
  - Draw bounding boxes around each object and calculate its height and width

## Results

![Result](images/result2.png?raw=true "Title")

## Author

* Rucha wagh



* https://www.pyimagesearch.com/




 
