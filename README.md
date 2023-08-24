# Image-Stitching

In this project, our goal with my project partner is to combine multiple images with overlapping fields of view to create 
a seamless panoramic view. This process is called image merging.
First, we took two images as input. Next, we applied the SIFT algorithm to the images to detect 
the points of interest and calculate the corresponding feature descriptors, and these points were 
circled. We used descriptors to match the identified points of interest. We also used BFMatcher 
in this step and performed ratio testing to identify good matches. We visualized these good 
matches. Next, we applied a geometric transformation between the two images to align the two 
images. We first estimated the affine geometric transformation using cv2.estimateAffine2D. 
After using cv2.warpAffine we got a merged (converted) image. Then we created the 
(converted) mask of this merged image. Finally, we enlarged the first image so that its 
dimensions match the dimensions of the converted image. A mask was then created to identify 
the overlapping regions. Overlapping parts are blended by taking the average value of the pixels 
in the overlay. The final result was obtained by combining the first enlarged image with the 
transformed second image.
