# HP-Invisibility-Cloak

## Objective
<img align="right" src="HP.gif">
  The main objective of this project is to obtain a end result as shown here in the right. This is a gif from the movie "Harry Potter and The Sorcerer's Stone". The idea of how to implement this idea is inspired from a blog from the website machinelearningman.com. 
<br><br><br><br>

## Logic Implemented
<img align="right" height="300" width="400" src="harry_potter.gif">
The logic behind this implementation can be explained in the following 6 steps:
  
* We capture the background for the range of 60 so that it can later be used to replace the area covered by the cloak.
* Start reading the captured video frame by frame to detect the cloak.
* Since our cloak is red in color we use two ranges of red color to detect it and mask it and the final mask is obtained by adding both.
* Using the mask obtained that represents the cloak area, obtain the remaining area of the frame as a mask using bitwise_not operator.
* We pass in the pixel values of frame image in inverted mask and background image in cloak area mask using bitwise_and operator, because this will ensure that the unmasked area in both mask will not be affected during this operation.
* Finally above obtained results are added equally using "addWeighted" operator and the finaly result is written as an avi file.
<br>This process continues to take place untill webcam returns False on cap.read() or a user enter "q" from his Keyboard.

