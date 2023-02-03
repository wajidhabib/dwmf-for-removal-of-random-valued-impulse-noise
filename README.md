# Directional Weighted Median Filter for Removal of Random-Valued Impulse Noise

Implementation of paper "A new directional weighted median filter for removal of random-valued impulse noise" by Yiqiu Dong and Shufang Xu [1]

## Summary

The median based filters are well known methods for removing the noise from the corrupted images. These methods work well when the intensity and level of noise is small. In case of random-
valued impulse noise or highly corrupted images, their results are not optimal. This paper proposes a new impulse detector, which is based on the differences between the current pixel and its
neighbors aligned with four main directions. Then, it combines the results with the weighted median filter to get a new directional weighted median (DWM) filter. Extensive simulations show
that the proposed filter not only can provide better performance of suppressing impulse with high noise level but can preserve more detail features, even thin lines. As extended to restoring
corrupted color images, this filter also performs very well.

Keywords: Image denoising, impulse detector, random valued impulse noise

## Steps/Detection Algorithm

1.  Take a gray scale image.
2.  Create a 5x5 filter window.
3.  Find the pixel values in 4 directions (vertical, horizontal, diagonal left, diagonal right) from the center pixel.
4.  Create a weight filter such that give double weight to the pixel which are neighbours of the center pixel.
5.  Calculate Absolute weighted difference of each pixel with center pixel value in each direction and take the minimum of them.
6.  Minimum value is compared to a threshold value; 
    
     if value > threshold; it is noisy pixel 
     else; it is not noisy pixel

7.  Calculate standard deviation of the 5 pixels in each direction
8.  Giving extra weight (say 2) to the direction in which the standard deviation is smallest,
9.  Compute the weighted median as V=alpha * yij  + (1-alpha)* median 
10. Replace the noisy pixel with this median value
11. Repeat the process (step 2-9) for 5-10 times for more smoother image.
12. Reduce Treshold value by .80 on each iteration.

## References:
[1] : Y. Dong and S. Xu, “A new directional weighted median filter for removal of random-valued impulse noise,” IEEE signal processing letters, vol. 14, no. 3, pp. 193–196, 2007.

