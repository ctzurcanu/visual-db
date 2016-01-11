# A Visual Method For Adressing Large Collections

## Abstract

## The Problem
When visualising a large dataset there is a fitting issue in the available screen space. We will constrain the record to just one attribute thus approximating the dataset to a one-dimension object and the problem remains related to the best way to map this object to a 2-dimensional space (screen space) that is in most cases a rectangle with the width larger than the height.
Given a large ordered dataset D of size s we will find a mapping to a cartesian rectangle region V (viewport) of size width, height (w, h) in such a way that we will be able to approximate easily the location (x, y) in V of a record at location l in D. And vice versa.
### Proposed Solution
Since we do not know the order of s, we need to consider a scaleable solution. The most obvious is to have a space-covering 1-d fractal since the fractal spans the 2-d space and increases its length at each iteration.
## Finding The Best Fractal
The optimal fractal curve should have the following characteristics:

+ should span the space with a resonable degree of:
	+ homegenity
	+ bound to a foreseable rectangle region
+ should not generate intersection with itself
+ be generated by simple rules (ideally L-System)
+ a reasonable degree of "neighborhooding"
+ high degree of local symmetry
+ minimal variation of geometric shapes of elements
+ simple formulae for finding the exact location of a point value on any iteration

Optional/preferable characteristics

+ improved redability by:
	+ minimal variation of angles
	+ or continous curve without angles

A Hilbert curve produced by the L-System:
Start: X
Rules: X=+YF-XFX-FY+;Y=-XF+YFY+FX-;F=F
Angle: 90 deg

![](http://oroboro-oroboro.rhcloud.com/file/dbb3DzLC3xSkYAehp)

















































Meets the most characteristics. Even better when the 90 degree angles are rounded.

### Proposed Fractal

Hoever we can find an even better solution that retains all the advantageous characteristics of Hilbert and even upgrade on local symmetry, minimisation of used shapes. Also the ratio w/h is 3/2: advantageous for most viewports.

We will explore the curve produced by:
Start: F
Rules: F=FF+FFF+FF
Angle: 90 deg

![](http://oroboro-oroboro.rhcloud.com/file/hXedrCQpsxcdRBTda)










































The initial shape that spans the F production rule is a circle arc with a 90 deg angle in order to provide a continous curve without angles. For this purpuse the positions 2, 3, 5, 6 of the first rule have to have inverse sense than the arc on positions 1, 4, 7.
![](http://oroboro-oroboro.rhcloud.com/file/H7RT6gcDCdgAsBAc3)



























This clearly shows a higher degree of local symmetry than Hilbert curve together with the use of less geometrical elements. We were able to generate a smooth curve and the next step is to predict the exact and approximate coordinate transformations.

## Coordinate Transformations
### Determine the Number of Iterations
In order to map the dataset of size s, we will need n iterations. The euclidian metric of this fractal is 2.(6)^i * L where i is the number if iterations and L is the initial length of the first iteration. Therefore, given L, n is the first iteration where s is less than 2.(6)^n * L. n > log(2.(6), s/L).
### Determine the Inflexion Points
Each iteration will have 7^i + 7^(i-1) + .. + 1 inflexion points. Their relation to the base 7 of numeration is evident. The length of the base 7 number is the number of iterations i. We can use base 7 of numeration to name the inflexion points.
Taking into consideration the origin as the first point of the arc of the first iteration, the inflection points for the first iteration have the coordinates: (0, 0) and ((L * sqrt(2))/(2 * PI), 0) where L is the length of the arc.
For next iteration:

point 0: (0 ,0) 

point 1: (0, (L * sqrt(2))/(2 * PI * 2.(6))) 

point 2: (0, (L * sqrt(2))/(PI * 2.(6)))) 

point 3: ((L * sqrt(2))/(2 * PI * 2.(6))), (L * sqrt(2))/(PI * 2.(6)))) 

point 4: ((L * sqrt(2))/(PI * 2.(6))), (L * sqrt(2))/(PI * 2.(6)))) 
 
point 5: ((L * sqrt(2))/(2 * PI), (L * sqrt(2))/(PI * 2.(6)))) 

point 6: ((L * sqrt(2))/(2 * PI), (L * sqrt(2))/(2 * PI * 2.(6)))) 

point 10: ((L * sqrt(2))/(2 * PI), 0)

The locations of the points on the fractal curve are equaliy spaced.

We do not need to calculate the points for the next iterations explicitly since we can use a recursive function to do so. We only need to calculate the coordinates of the offset of the reminder of the location l on the last iteration n.
 
## Visual Alternatives
### Pixel Approximation
We will consider a more restrictive case where the curve is approximated to pixels or squares and the curve is only used as a reading guide.

![](http://oroboro-oroboro.rhcloud.com/file/LHX2kpsqiag83DC2s)

![](http://oroboro-oroboro.rhcloud.com/file/dgssMMAW7bohhTCyM)
With reading direction guides.

#### Space Folding

![](http://oroboro-oroboro.rhcloud.com/file/yvk7wDroGZrtBkTpf)








The square is shown for compararison with the first iteration. The marked pixel gets repeated to improve redability. This brings an improvement in information density of a factor of at least 2. 

## Generalization To Higher Dimmensions
## Applications
### Binary Tree
### Large Text
### Knowledge Systems
### Source Code
### DNA String
### Stock Market
### KV Ordered DBs
### Automatons & Nano Robots

### Construction of Synthetic Organs
## Conclusions



























































