# MBG-6133 Bioinformatics Data Skills - Final 

## **Question 1**

The aim of this part is to create a **100x100 numpy array** which composed of **random integers** that vary between **0 and 100**. To achieve this aim, first related libraries were loaded as follows:

```bash
INPUT:	import numpy as np
    	import matplotlib.pylab as plt
      	import seaborn as sns
```

Then, the range of the default random numpy array was assigned to 'rng' and a numpy array that composed of random integers varied between 0 and 100 was created into 'x' to form 100x100 matrix as follows:  

```bash
INPUT:	rng = np.random.default_rng()
	x = rng.integers(101, size=(100, 100))
      	x

OUTPUT:	array([[27, 88, 24, ..., 85, 81, 39],
	       [42,  4, 43, ..., 88,  0, 30],
	       [61, 45, 41, ...,  7, 86, 45],
	       ...,
	       [35, 34, 80, ..., 71, 57, 24],
	       [86, 62,  2, ..., 15, 15, 82],
	       [34, 25, 76, ..., 36, 25, 43]])
```

As a final step, the matrix that composed of random integers was visualized as a heatmap by using seaborn library. In the heat map, I used 'hot' colors and saved in a png file. White to black scale bar which composed of shades of warm colors indicates the numbers that were ranged between 100 and 0.   

```bash
INPUT:	sns.heatmap(x, cmap = 'hot')
      	plt.title("Random Integers Heatmap")
      	plt.savefig("heatmap1.png", dpi=600)
      	plt.show()

OUTPUT:	![HEATMAP 1](/Users/ekinazbazdar/Desktop/DEU-BHT-PhD/Bioinformatics Data Skills/Final/heatmap1.png)
```

## **Question 2**

The aim of this part is to filter out odd numbers, convert True/False statements into 0/1 values and visualize them as a heat map.

The 'odd numbers' were represented as True/False statements using followed formula:

```bash
INPUT:	odd_numbers = x % 2 == 1
      	odd_numbers

OUTPUT:	array([[ True, False, False, ...,  True,  True,  True],
	       [False, False,  True, ..., False, False, False],
	       [ True,  True,  True, ...,  True, False,  True],
	       ...,
	       [ True, False, False, ...,  True,  True, False],
	       [False, False, False, ...,  True,  True, False],
	       [False,  True, False, ..., False,  True,  True]])
```

Odd numbers were also filtered as follows:

```bash
INPUT:	x[odd_numbers]

OUTPUT: array([27, 37, 35, ..., 81, 25, 43])
```

Since the true and false statements are equal to 1 and 0, respectively, odd numbers were multiplied by 1. By this way, true and false statements were resulted in "1" and "0", respectively. 

```bash
INPUT:	y = np.multiply(odd_numbers, 1)
      	y

OUTPUT:	array([[1, 0, 0, ..., 1, 1, 1],
	       [0, 0, 1, ..., 0, 0, 0],
	       [1, 1, 1, ..., 1, 0, 1],
	       ...,
	       [1, 0, 0, ..., 1, 1, 0],
	       [0, 0, 0, ..., 1, 1, 0],
	       [0, 1, 0, ..., 0, 1, 1]])
```

As a final step, same matrix that composed of random integers was visualized as a heatmap by using seaborn library. The numbers were represented as white or black, because the heatmap was composed of 0s and 1s.

```bash
INPUT:	sns.heatmap(y, cmap = 'hot')
      	plt.title("True/False Heatmap")
      	plt.savefig("heatmap2.png", dpi=600)
      	plt.show()

OUTPUT:	![HEATMAP 2](/Users/ekinazbazdar/Desktop/DEU-BHT-PhD/Bioinformatics Data Skills/Final/heatmap2.png)
```
