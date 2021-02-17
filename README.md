## DynIm (Dynamic-Importance Sampling), Version 0.1

##### Authors: Harsh Bhatia (hbhatia@llnl.gov) and Joseph Y Moon
##### Released: Nov 12, 2020

### Description:
`DynIm` is a pure-python package to perform ***dynamic-importance (DynIm)
sampling*** on a high-dimensional data set.

DynIm is designed to minimize redundancy and maximize the coverage of the
sampled points. DynIm uses the notion of "*dissimilarity*" from previously
selected samples to define the importance of potential selections, and selects
the ones that are most dissimilar. Simply, DynIm provides a *farthest-point*
sampling approach.

Currently, DynIm uses L2 distances in the given high-dimensional space to
define similarity and can be configured to use *exact* as well as *approximate*
distances. Approximate distances are useful for computational viability for
large data sizes and large data dimensionality. DynIm also provides a random
sampler for comparison of sampling quality.

### User Community:	
Researchers who want to run multiscale simulations.

### Usability:	
Requires installation of faiss (outside of DynIm). After that, the code is pure-python and straightforward to use/edit.

The code is robust, however, approximate calculation of distances may require experimentation from the user to identify suitable parameters.

Data does not need to be preprocessed.

### Uniqueness:	
This is the first tool to perform “dynamic” sampling, that is, the input distribution can change over time, and the sampling adapts itself to the new distribution. This is the key feature that makes it possible to use this in-situ and enable large multiscale simulations.

### Components:	

Software: contained in this GitHub repository.

### Technical Details:

#### Dependencies

DynIm uses [`faiss`](https://github.com/facebookresearch/faiss) to implement
nearest neighbor searches for sampling, and has been tested with `faiss v1.6.3`.
Currently, we ask the user to install `faiss` explicitly from source. Please
see [here](https://github.com/facebookresearch/faiss/blob/master/INSTALL.md)
for installation instructions.

Other dependencies are `numpy` and `pyyaml` (if needed, will be installed with
DynIm).

#### Installation

Once the dependencies are installed, DynIm can be installed as follows:

```
git clone https://github.com/CBIIT/NCI-DOE-Collab-Pilot2-DynIm 
cd dynim
pip install .
```

Please test your installation as follows.
```
python3 -m unittest examples/test_dynim.py
```

### Examples

See the `examples` directory.

### License

DynIm is distributed under the terms of the MIT license.

See [LICENSE](./LICENSE) and [NOTICE](./NOTICE) for details.

SPDX-License-Identifier: (MIT)

LLNL-CODE-813147
