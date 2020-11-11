# Panorama-Stitching

This project was also a part of my course assignment in Modern Computer Vision.

In this problem we will develop an algorithm for stitching a panorama from overlapping photos (Figure1), which amounts to estimating a transformation that aligns one image to another. To do this, we will compute SURF/SIFT/ORB features in both images and match them to obtain correspondences. We will then estimate a homography from these correspondences, and we’ll use it to stitch the two images together in a common coordinate system. In order to get an accurate transformation, we will need many accurate feature matches. Unfortunately, feature matching is a noisy process: even if two image patches (and their SURF/SIFT/ORB descriptors) look alike, they may not be an actual match. To make our algorithm robust to matching errors, we will use RANSAC, a method for estimating a parametric model from noisy observations. We will use the obtained homography transformation to do panoramic stitching 

The following were the guidelines for this assignment:
1. Implement get features(img) to compute SURF/SIFT/ORB features for both of the given image.
Implement match keypoints(desc1, desc2) to compute key-point correspondences between the two
source images using the ratio test. Run the plotting code to visualize the detected features and resulting
correspondences. (Hint: You can use existing libraries.)
2. Write a function find homography(pts1, pts2) that takes in two N×2 matrices with the x and
y coordinates of matching 2D points in the two images and computes the 3×3 homography H that
maps pts1 to pts2. You can implement this function using direct linear transform (DLT). Report the
homography matrix. (Hint: You should implement this function on your own)
3. Your homography-fitting function from (2) will only work well if there are no mismatched features. To
make it more robust, implement a function transform ransac(pts1, pts2) that fits a homography
using RANSAC. Run the plotting code to visualize the point correspondences after applying RANSAC.
(Hint: You should implement this function on your own)
4. Write a function panoramic stitching(img1, img2) that produces a panorama from a pair of overlapping images using your functions from the previous parts. Run the algorithm on the two images
provided. Report the panorama stitched image. (Hint: You should implement this function on your
own. Use inverse mapping while stitching.)
5. Extend the algorithm to handle n=3 images, use these given images. I have also provided reference
panoramic stitched image to compare your result with. Report the all visualizations as mentioned
for n=2 case, along with two homography matrices with respect to middle image.(Hint: You should
implement this function on your own. Take the middle image as reference and find the homography
transformations with respect to middle image, that doesn’t need further transformations and also produce
the most aesthetically pleasing panorama.) 


There were some problems in the stiching process for  this project using custom functions for finding homography and RANSAC algorithm  and hence I tried the same using in-built cv2 methods apart from the functions that I had written by myself. You can find the proper panoramic image by running `stitch.py`

One can run `stitch.py` to find the panormaic images of pair of images using the built in cv2 methods. 
