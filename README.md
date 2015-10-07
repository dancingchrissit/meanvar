# tools4j-meanvar
Tiny Java utility to incrementally calculate Mean and Standard Deviation with a numerically stable algorithm. Contains a simple utility class to incrementally calculate moving average and moving standard deviation of a data series. 

#### Examples
##### MeanVarianceSampler
```java
final MeanVarianceSampler sampler = new MeanVarianceSampler();
sampler.add(1);
sampler.add(2.5);
sampler.add(3.22);
sampler.add(-6.72);
double mean = sampler.getMean();
double var = sampler.getVariance();
double stdDev = sampler.getStdDev();
```

##### MeanVarianceSampler
```java
final int windowSize = 3;
final MeanVarianceSlidingWindow win = new MeanVarianceSlidingWindow(windowSize);

double mean, var, stdDev;

win.update(1);
win.update(2);
win.update(3);
mean = win.getMean();
var = win.getVariance();
stdDev = win.getStdDev();

//window is full
		
//1 drops out now
win.update(4);
mean = win.getMean();
var = win.getVariance();
stdDev = win.getStdDev();

//2 drops out now
win.update(5);
mean = win.getMean();
var = win.getVariance();
stdDev = win.getStdDev();
```

#### More Information
* [MIT License](https://github.com/tools4j/meanvar/blob/master/LICENSE)
* [MeanVarianceSampler.java](https://github.com/tools4j/meanvar/blob/master/src/main/java/org/tools4j/meanvar/MeanVarianceSampler.java): Utility to add, remove or replace values in a running calculation of mean and variance
* [MeanVarianceSlidingWindow.java](https://github.com/tools4j/meanvar/blob/master/src/main/java/org/tools4j/meanvar/MeanVarianceSlidingWindow.java): A fixed length sliding window to calculate moving average and moving standard deviation of a data series
