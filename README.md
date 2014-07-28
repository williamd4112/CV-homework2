<center>
<img src="./index_files/AllStitched.png" width="410" >
<br>
(Panorama image of Mt. Rainer in Washington USA.)
</center>

# Project 2: Panorama Stitching

## Brief
* Due: TBA
* Required files: results/index.md, and code/

##Overview
Panoramic stitching is an early success of computer vision. Matthew Brown and David G. Lowe published a famous [panoramic image stitching paper](http://www.cs.ubc.ca/~lowe/papers/07brown.pdf) in 2007. Since then, automatic panorama stitching technology has been widely adopted in many applications such as Google Street View, panorama photos on smartphones, and stitching software such as [Photosynth](http://photosynth.net/) and [AutoStitch](http://cs.bath.ac.uk/brown/autostitch/autostitch.html). This homework will help you create your own panorama stitching software so you can go out and have fun :)

##Details

In this programming assignment, we will match SIFT keypoints from multiple images to build a single panoramic image. This will involve several tasks:
* Detect SIFT points and extract SIFT descriptor for each keypoint in an image using vlfeat.
* Compare two sets of SIFT descriptors coming from two different images and find matching keypoints.
* Given a list of matching keypoints, use least-square method to find the affine transformation matrix that maps positions in image 1 to positions in image 2.
* Use RANSAC to give a more robust estimate of affine transformation matrix.
* Given that transformation matrix, use it to transform (shift, scale, or skew) image 1 and overlay it on top of image 2, forming a panorama. (This is done for you.)
<center>
<img src="./index_files/Rainier1.png" width="200" >
<img src="./index_files/Rainier2.png" width="200" >
<br>
(Left: image 1 & Right: image 2)
<br>
<img src="./index_files/Stitched.png" width="410" >
<br>
(Stitched image)
</center>* Stitch multiple images together under a simplified case of real-world scenario.

</p><p>
<b>Potentially useful MATLAB functions</b>: <code>fspecial()</code> and the operators in the <a href="http://cs.brown.edu/courses/csci1430/docs/matlab-tutorial/">MATLAB tutorial</a> which make it efficient to cut out image subwindows and do the convolution (dot product) between them. <code>padarray()</code>. 
<br>
<b>Forbidden functions</b> you can use for testing, but not in your final code: <code>imfilter()</code>, <code>filter2()</code>, <code>conv2()</code>, <code>nlfilter()</code>, <code>colfilt()</code>.
</p><br>

## Extra Points
* +2 pts: If you make your code publicly available.
* +2 pts: If you comment on pull request from students who fork the homework. Make sure you send me a screenshot of the comments to me.
* Other things that impress me.

## Writeup
For this project, and all other projects, you must do a project report in results folder using [Markdown](https://help.github.com/articles/markdown-basics). We provide you with a placeholder [index.md](./results/index.md) document which you can edit. In the report you will describe your algorithm and any decisions you made to write your algorithm a particular way. Then, you will describe how to run your code and if your code depended on other packages. Finally, you will show and discuss the results of your algorithm. In the case of this project, show the results of your filtering algorithm (the test script saves such images already) and show some of the intermediate images in the hybrid image pipeline (e.g. the low and high frequency images, which the starter code already saves for you). Also, discuss anything extra you did. Feel free to add any other information you feel is relevant.

## Rubric
* +50 pts: Working implementation of image filtering in my_imfilter.m
* +30 pts: Working hybrid image generation
* +20 pts: Writeup with several examples of hybrid images
* +10 pts: Extra credit (up to ten points)
* -5*n pts: Lose 5 points for every time (after the first) you do not follow the instructions for the hand in format

## Get start & hand in
* Publicly fork version (+2 extra points)
	- [Fork the homework](https://education.github.com/guide/forks) to obtain a copy of the homework in your github account
	- [Clone the homework](http://gitref.org/creating/#clone) to your local space and work on the code locally
	- Commit and push your local code to your github repo
	- Once you are done, submit your homework by [creating a pull request](https://help.github.com/articles/creating-a-pull-request)

* [Privately duplicated version](https://help.github.com/articles/duplicating-a-repository)
  - Make a bare clone
  - mirror-push to new repo
  - [make new repo private](https://help.github.com/articles/making-a-private-repository-public)
  - [add aliensunmin as collaborator](https://help.github.com/articles/adding-collaborators-to-a-personal-repository)
  - [Clone the homework](http://gitref.org/creating/#clone) to your local space and work on the code locally
  - Commit and push your local code to your github repo
  - I will clone your repo after the due date

## Credits
	Assignment modified by Min Sun based on James Hays and Derek Hoiem's previous developed projects
