----------------------------------------------------------------------
CONVERTED TO PYTHON BY 
----------------------------------------------------------------------
Matheus Bento - matheus.costa@inpe.br
<br>
INPE - 2019
----------------------------------------------------------------------
HOW TO USE

EXAMPLE 1:
x = pmodel(noValues=2**12, p=0.52, slope=-1.66)

----------------------------------------------------------------------
This function generates a multifractal time series using the p-model.
Optionally you can also filter the result from the p-model in Fourier
space to give it another fractal slope, e.g. to make it continuous and
nonstationary. This is also called fractional integration. The p-model 
itself can only produce stationary time series, i.e time series where 
the variance is finite if you would extrapolate its power spectrum to 
infinite large scales.

The parameter of the p-model is p. With p values close to 1 or 0 the time
series is very peaked. With values close to 0.5 the p-model is much
calmer; p=0.5 results in a constant unity vector.
The parameter for the fractal integration is the slope of the power
spectrum. Davis et al. calls slopes flatter than -1 stationary, and
slopes between -1 and -3 nonstationary, with stationary increments. 
These nonstationary cases are at least continuous, but not
differentiable. Slopes steeper than -3 are nonstionary and
differentiable.

Possible calls:
[pModelTimeSeries] = pmodel
[pModelTimeSeries] = pmodel(noValues)
[pModelTimeSeries] = pmodel(noValues, p)
[fractionalIntegratedTimeSeries] = pmodel(noValues, p, slope)
[fractionalIntegratedTimeSeries, pModelTimeSeries] = pmodel(noValues, p, slope)
If no number of values (noValues) is specified or it is empty, the
default value of 256 is used.
If no p is specified or it is empty, the default value of 0.375 is used.
If no slope is specified, you will get a time series without fractional
integration.
If a slope is specified you will get the fractionally integrated time
series, or if you use two output variables you will get both the p-model
time series as well as its fractionally integrated version.

This Matlab function is based on the article: Davis, A., A. Marshak, R.
Cahalan, and W. Wiscombe, The landsat scale break in stratocumulus as a
three-dimensional radiative transfer effect: implications for cloud
remote sensing. Journal of the Atmospheric Sciences, Vol. 54, no. 2,
1997.
First version by Victor Venema, Victor.Venema@uni-bonn.de, 25 January
2006.
----------------------------------------------------------------------
