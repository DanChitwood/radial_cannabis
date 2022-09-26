# radial cannabis 🍁
*a function that models Cannabis leaflets continuously*

# `radial_leaf` function

**A function `radial_leaf` that takes inputs of:**

1. leaf trace coordinates
2. landmark coordinates
3. number of points to interpolate for the trace
4. number of landmarks (interpolated points within each leaflet)
5. polynomial degree to model each landmark across leaflets in polar coordinates
6. frames (or x values) to model across the leaf, apportioned to intervals between leaflets by rounding

**The function returns:**

1. overall modeled x and y values. for both x and y values, this is a double list of lists structured first by frame, and the for each frame, modeled values for each landmark. models are using polar coordinates
2. interpolated trace lists for plotting
3. landmark lists that have been aligned to the trace (for plotting)

**IMPORTANT NOTE:** for now, only the right side of leaves is considered. The `np.arctan` function returns phi values only between +/- pi/2. There are also with problems in quadrant 4, in addition to 2 and 3, as well. This is a bug to figure out in the future, but is circumvented here by only considering the right side of leaves for the radial modeling step.
