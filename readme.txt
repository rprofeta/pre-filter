

def adaptive_prefilter(N,P,olap):
# Author : K Suresh sureshk@ieee.org
# Adaptive Pre Filter 
# Interpolates Reflex coefficients across Frame 
# Lattice FIR implementation
# Autocorrelation sequence is derived from psychoacoustic threshold
# Reflexion coefficients are derived from ACF using Levinson-Durbin Recursion
# N = Frame Size, P = Filter Order, olap = Interpolation Depth
# Returns filt_lattice=filter coefficients (ki),filter_output=filtered signal,olap = extend of interpolation used 

def adaptive_prefilter_quant(N,P,olap,q):
# Author : K Suresh sureshk@ieee.org
# Adaptive Pre Filter followed by Quantization 	
# Interpolates Reflex coefficients across Frame 
# Lattice FIR implementation
# Autocorrelation sequence is derived from psychoacoustic threshold
# Reflexion coefficients are derived from ACF using Levinson-Durbin Recursion
# N = Frame Size, P = Filter Order, olap = Interpolation Depth , q = quantization
# Returns filt_lattice=filter coefficients (ki),filter_output=filtered signal,olap = extend of interpolation used 
# filtered_spectrum = DFT Spectrum of the filtered signal ,input_spectrum = DFT Spectrum of the input signal
# filtered signal is written to the wavfile filt_quantized.wav

def post_filter(fil_coef,filtered,olap,fs):
# Author : K Suresh sureshk@ieee.org
# Adaptive  Post Filtering, inverse filter for pre-filtered signal	
# Interpolates Reflex coefficients across Frame 
# fil_coef=filter coefficients used in pre-filter in clolumns, filtered = filtered frames in columns,
# olap = Interpolation Depth used in pre-filter
# fs= sampling frequency 
# Returns reconst = Reconstructed Signal
# Reconstructed signal is written to the wavfile reconstructed.wav

