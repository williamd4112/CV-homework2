# 洪章瑋 <span style="color:red">(102062171)</span>

# Project 2 / Panorama Stitching

## Overview
The project is related to 
> This projects implemented basic image stitching algorithm with SIFT feature descriptor and affine transform matrix. For now, this version cannot support unordered image set.


## Implementation
1. SIFT Feature extraction
	* Use 'vl_sift' to extract SIFT features
	<img src="sift.png"/>
2. SIFT Feature matching
	1. Compute Euclidean distance in each pair
	```
	distance = pdist2(descriptor1, descriptor2);
	```
	2. Compute ratio of 1st nearest pair and 2nd pair (i.e. 1st nearest distance / 2nd nearest distance)
	3. Filter out ratio < thresh
	4. Result  
	<img src="siftsimplematcher_result.png"/>
	
3. Compute affine matrix
	* We have H * P1 = P2
	* Compute H = (P1' \ P2')'
4. RANSAC affine matrix computation
	1. Transform points in P1 to P2 with H
	2. Compute sum of error (Euclidean distance)
	```
	sqrt(sum(((pt2_h - H * pt1_h).^2)))
	```
5. Multiple image stitch
	1. Initialize T = eye(3)
	2. currentFrameIndex < refFrameIndex
	```
	for k = currentFrameIndex:refFrameIndex - 1
        	T = i_To_iPlusOne_Transform{k} * T;
    	end
	```
	3. currentFrameIndex > refFrameIndex
	```
	for k = currentFrameIndex:-1:refFrameIndex + 1
        	T = pinv(i_To_iPlusOne_Transform{k-1}) * T;
    	end
	```

## Installation
* Other required packages.
* How to compile from source?

### Results

<table border=1>
<tr>
<td>
<img src="placeholder.jpg" width="24%"/>
<img src="placeholder.jpg"  width="24%"/>
<img src="placeholder.jpg" width="24%"/>
<img src="placeholder.jpg" width="24%"/>
</td>
</tr>

<tr>
<td>
<img src="placeholder.jpg" width="24%"/>
<img src="placeholder.jpg"  width="24%"/>
<img src="placeholder.jpg" width="24%"/>
<img src="placeholder.jpg" width="24%"/>
</td>
</tr>

</table>
