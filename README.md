# Proteins

Some of my tools for protein related work
<br/>
# Contents
### [Voxel maps](https://github.com/jamesengleback/Proteins/blob/master/20181003-Voxel%20maps.ipynb)
This was some early work I was doing on [KDEEP](https://pubs.acs.org/doi/abs/10.1021/acs.jcim.7b00650) by Jiménez et al. in 2018.
This paper is very cool, it's a 3D convolutional neural network that predicts how tightly a chemical will [bind](https://en.wikipedia.org/wiki/Dissociation_constant) to a protein.


The model was trained on the [PDB-bind](http://www.pdbbind.org.cn/) database, which contains protein structures, the structures of chemicals that bind to them and a [metric that measures binding tightness](https://en.wikipedia.org/wiki/Dissociation_constant). 

It's a very cool paper, I encourage you to have a read.
  
The notebook here uses [Biopandas](https://rasbt.github.io/biopandas/) which can read and fetch PDB files and show the file as a [pandas dataframe](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html) which is really nice to work wtih.
I turned this into a 3D [numpy](https://www.numpy.org/) matrix, where each indice was meant to represent a 1 [Angstrom](https://en.wikipedia.org/wiki/Angstrom) cube by rounding down each atoms' coordinate to the nearest integer and[,](https://en.wikipedia.org/wiki/Serial_comma) and indexing the array with those integers. I also segregated the carbons, nitrogens etc into their own arrays, which the KDEEP team do to treat each atom type like a different [color channel](https://en.wikipedia.org/wiki/Channel_(digital_image))

There's also a rendering of the protein in there using [Matplotlib's Pyplot](https://matplotlib.org/) using their [Volumetric Plots](https://matplotlib.org/gallery/mplot3d/voxels.html). I never found out how to shade the faces properly, if anyone knows how to do that please let me know!
