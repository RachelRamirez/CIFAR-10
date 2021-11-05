# CIFAR-10
Migrating previous Fashion MNIST data to the CIFAR 10 dataset

Fitting the Definitive Screening Design in JMP to the results:

I set the first Stage-1 Main Effect Estimates alpha to 0.2 so theres better power to catch an effect that has an effect.  (I'm more willing to accept main effects that are not significant, then to set the significancy level so high that I miss it.  Dr. Montgomery talks about this in DoX talks)  Stage 1 Main Effects of importance are in descending t-ratio order:  *Dropout, FlipVertical, FancyPCA, Crop, ShiftX, ToGray, ZoomIn, Brighten*.  

In Stage 2, "Even Order" Effect Estimates, to find significant Quadratic effects and Interactions of Main Effects, you have to choose whether you assume Quadratic Terms  and Interactions obey Strong Heredity.  In my results, whether you do or do not assume Quadratric Terms obey Strong Heredity, *"ZoomIn"x"ZoomIn"* or *"ZoomIn^2"* is a large negative effect. (0.016)  Interactions is two different results dependingon assumptions: If strong heredity is not assumed: *Brighten*x*Contrast* has a positive effect of 0.0037.  If strong heredity is assumed: *dropout*x*FancyPA* has a semi-large negative effect (0.003).

 
 ## Stage 1 Main Effects
 
![image](https://user-images.githubusercontent.com/13596380/140319002-137e947c-e23e-4e4c-b19c-c040aafca320.png)

 ## Combined Stage 1 and 2 Effects
 
![image](https://user-images.githubusercontent.com/13596380/140319414-a09d9b7b-e4a3-470c-9cce-7bcedb50a312.png)


## Fitting the Model

After fitting the model with the Stage 1 and 2 Combined Effects  the overall Prediction Profiler in JMP that helps optimize the desired test accuracy suggests using
* Dropout: 0.6
* ShftX: 0
* Contrast: 0
* Brighten: 0
* Crop: 8  (32-8=24)
* ZoomIn: 0.071451
* FlipVertical: 0
* FancyPCA: 0
* toGray: 1

I am surprised to see **toGray, ZoomIn and Crop** 


