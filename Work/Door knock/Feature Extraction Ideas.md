1. Instead of spectral features and moving average, I would recommend wavelet features. You could either do a **continuous wavelet transform (CWT)** or a **Short Wavelet Transform (SWT)** and identify the peaks / drop where the potholes show up. The advantage with wavelet is that it is well resistant to noise and you can also preserve the time axis information to pin point the location of peaks. The trick is just to choose an appropriate wavelet. Those which have spike shapes like Daubechies and Symlets would be ideal. With proper feature extraction, you can even do the detection without machine learning.
2. **Partial autocorrelation function** (**PACF**)
3. **Periodogram for spectral analysis**
4. **(X,Y,Z)max**
5. **(X,Y,Z)min**
6. **(X,Y,Z)mean**
7. **(X,Y,Z)std**
8. **mean-x, mean-y, mean-z, SD-X, SD-Y, SD-Z**
9. SMA(signal magnitude area) = **|X|+|Y|+|Z**| - The SMA variable is used to distinguish mobility (activity) and rest period in a time series.
10.**PCA** (principal component analysis)

- ### 18 simple statistical features
1. mean  
2. standard deviation  
3. average absolute deviation  
4. minimum value  
5. maximum value  
6. difference of maximum and minimum values  
7. median  
8. median absolute deviation  
9. interquartile range  
10. negative values count  
11. positive values count  
12. number of values above mean  
13. **number of peaks**  
14. **skewness**  
15. kurtosis  
16. energy  
17. average resultant acceleration  
18. signal magnitude area



Serializes into 32bit signed integer
