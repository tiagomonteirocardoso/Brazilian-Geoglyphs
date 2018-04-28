# Brazilian-Geoglyphs

This project aims at automating the discovery of new geoglyphs in Acre State - Brazil. Geoglyphs are large earthworks usually
displaying geometrical or even antropomorphical motifs. In America they were built many centuries ago by Pre-Columbian populations. In recent years, thanks to Google Earth and the deforestation process, many so far unknown specimens have been 
identified in Acre State, Brazil. This discovery is potentially revolutionary for the field of Amerindian studies, for it
shows that forest areas which were thought to be pristine were in fact already occupied by, in some cases, large populations.
However, the same process that allows us to discover new geoglyphs (deforestation) also brings along ironically the main 
menaces to the preservation of the same geoglyphs, that is, farm and road construction, the disorderly occupation of new spaces
etc. The identification of new geoglyphs should ideally occur BEFORE deforestation takes place, in order that it may guide
informed conservation policies. For that matter, at least a major initiative has been proposed, namely, an aerial survey of 
still canopied areas using LIDAR technology (see Khan, Aragão and Iriarte, "A UAV–lidar system to map Amazonian rainforest and 
its ancient landscape transformations", IJRS 38:8-10 (2017), 2313-2330). 

The ultimate goal of this project is to identify candidate patterns in Lidar aerial data. However, Lidar data is still not 
publicly availabe. I have thus decided to focus on Google Earth data. The identification of patterns on Google Earth
data is not an easy task. The colour-spectrum images from satellite data present a variability of conditions not found in the 
grayscale images produced by LIDAR systems. So far I have restricted my training set to a subset of images with more 
homogeneous characteristics (terrain texture, kind of vegetation cover etc.) and used the grayscale converts of these images. 
Working with this group of images I found that, although the pixels values which are relevant for segmentation vary greatly 
from image to image, their pdf's are reasonably similar. In this way, I was able to define a segmentation routine which uses 
different values as threshold parameters for different images from the group but whose results have overall similar sensitivity.

The next step in this project is the generalization of the method to an arbitrary satellite image. In order to accomplish this,
we shall first be able to correctly classify the image in a group for which a segmentation routine is established. We could use
a supervised learning method to classify new images. The training would have the images as input, the segmentation method which
works better for each image as labels, and the classification features as output. We could thus establish a taxonomy of image
types found in our regions of interest. I'm confident that with this taxonomy the system's sensitivity could reach decent levels.

# Built with
Python 3.6.4
OpenCV 3.3.1

# Author
Tiago Monteiro Cardoso

# Acknowledgments
For skeletonization I used the code provided by Abid Rahman K in <http://opencvpython.blogspot.com.br/2012/05/skeletonization-using-opencv-python.html>
