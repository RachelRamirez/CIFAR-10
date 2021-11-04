# CIFAR-10
Migrating previous Fashion MNIST data to the CIFAR 10 dataset

Fitting the Definitive Screening Design in JMP to the results:

I set the first Stage-1 Main Effect Estimates alpha to 0.2 so theres better power to catch an effect that has an effect.  (I'm more willing to accept main effects that are not significant, then to set the significancy level so high that I miss it.  Dr. Montgomery talks about this in DoX talks)  Stage 1 Main Effects of importance are in descending t-ratio order:  *Dropout, FlipVertical, FancyPCA, Crop, ShiftX, ToGray, ZoomIn, Brighten*.  

In Stage 2, "Even Order" Effect Estimates, to find significant Quadratic effects and Interactions of Main Effects, you have to choose whether you assume Quadratic Terms  and Interactions obey Strong Heredity.  In my results, whether you do or do not assume Quadratric Terms obey Strong Heredity, *"ZoomIn"x"ZoomIn"* or *"ZoomIn^2"* is a large negative effect. (0.016)  Interactions is two different results dependingon assumptions: If strong heredity is not assumed: *Brighten*x*Contrast* has a positive effect of 0.0037.  If strong heredity is assumed: *dropout*x*FancyPA* has a semi-large negative effect (0.003).

 

Stage 1 - Main Effect Estimates

Term	    Estimate	Std Error 	t Ratio 	Prob>|t|
dropout	  0.0166	0.0013	      12.924  	<.0001
flipV	    0.0121	0.0012	      9.8295	  <.0001
fancyPCA	0.0028	0.0012	      2.2851	  0.0354
crop	    0.0023	0.0013	      1.8213	  0.0862
shiftX	 -0.003	  0.0013	     -1.986	    0.0634
togray	 -0.003	  0.0012	     -2.722	    0.0145
zoomin	 -0.004	  0.0013	     -2.751	    0.0136
brighten -0.004	  0.0013	     -2.951	    0.0089

Statistic	Value
RMSE	0.0087
DF	17
 
 
![image](https://user-images.githubusercontent.com/13596380/140319002-137e947c-e23e-4e4c-b19c-c040aafca320.png)





Combined Model Parameter Estimates

Term	Estimate	Std Error	t Ratio	Prob>|t|
Intercept	0.5305	0.0043	122.95	<.0001
dropout	0.0166	0.0013	13.132	<.0001
shiftX	 -0.003	0.0013	 -2.017	0.0508
contrast	0.0003	0.0013	0.2299	0.8194
brighten	 -0.004	0.0013	 -3	0.0048
crop	0.0023	0.0013	1.8511	0.0719
zoomin	 -0.004	0.0013	 -2.796	0.0081
flipV	0.0121	0.0012	9.99	<.0001
fancyPCA	0.0028	0.0012	2.3292	0.0253
togray	 -0.003	0.0012	 -2.755	0.0090
contrast*brighten	0.0037	0.0013	2.8656	0.0067
zoomin*zoomin	 -0.016	0.0045	 -3.664	0.0008



Statistic	Value
RMSE	0.0085
DF	38


![image](https://user-images.githubusercontent.com/13596380/140319414-a09d9b7b-e4a3-470c-9cce-7bcedb50a312.png)

