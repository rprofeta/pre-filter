
adaptive_prefilter.py 

Usage filter_lattice, filtered_output, overlap = adaptive_prefilter(N,P,overlap)

You can rum this in the following steps in ipython -pylab 
import adaptive_prefilter
adaptive_prefilter 
from adaptive_prefilter import adaptive_prefilter
filter_lattice, filtered_output, overlap = adaptive_prefilter(N,P,overlap)

It prompts for chosing wav file from folder

The aurguments are 
N = frame size = 128 
P = filter order , usally 10 or 11 
overlap = interpolation depth for filter coefficients. For a frame size of 128, you can choose 
          overlap in the range 16-32, though it supports values from 1-63

The function returns computed filter coefficents in filter_lattice (P x number of frames size matrix) filterd output in filtered_output ( N x number of frames size matrix) and overlap. 

adaptive_prefilter_quant.py 

Usage 
filt_lattice,filter_output,olap,filtered_spectrum,input_spectrum=adaptive_prefilter_quant(N,P,olap,q)

The aurguments are 
N = frame size = 128 
P = filter order , usally 10 or 11 
overlap = interpolation depth for filter coefficients. For a frame size of 128, you can choose 
          overlap in the range 16-32, though it supports values from 1-63

q = is used to change quantization level of the filtered signal,  can give values 2,4,8,...512. 
     ( \hat(x) = q* trunc (x/q )) ie filter output is divided by q, truncates, and then   multiplied by q. 

Post Filter 
post_filter.py

Reconstruct signal back from pre-filtered signal 

usage
reconst = post_filter(fil_coef,filtered,olap,fs)

fil_coef = filter coeefficinet matrix obtined from pre filter
filtered = filtered signal from pre filter 
olap = ineterpolation depth used in pre filter
fs = sampling frequency, used in wavewrite 

The reconstructed signal is returned in reconst 

reconstructed signal is written to reconstructed.wav

I am just copying the python commands used to run the files below. 

In [10]: import adaptive_prefilter

In [11]: adaptive_prefilter
Out[11]: <module 'adaptive_prefilter' from 'adaptive_prefilter.py'>

In [12]: from adaptive_prefilter import adaptive_prefilter

In [13]: filter_lattice, filtered_output, overlap = adaptive_prefilter(128,10,16
    ...: )
16000
(10, 1397)

In [14]: import post_filter

In [15]: post_filter
Out[15]: <module 'post_filter' from 'post_filter.pyc'>

In [16]: from post_filter import post_filter

In [17]: reconst=post_filter(filter_lattice, filtered_output, overlap,16000)

In [18]: 




