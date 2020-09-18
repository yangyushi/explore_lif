# explore_lif

Load 3D confocal images from `lif` files as `numpy` arrays.

## Install

- The most convenient way would be: `pip install -e .` from the directory where you have cloned or downloaded the code.
- You can also Include the file `explore_lif` in your project directory

## How to Use It

### For 3D Image

```python
from explore_lif import Reader

reader = Reader('lif_file.lif')
series = reader.getSeries()
chosen = series[0]  # choose first image in the lif file
# get a numpy array corresponding to the 1st time point & 1st channel
# the shape is (x, y, z)
image = chosen.getXYZ(T=0, channel=0)
```

### For 2D Image with Multiple Channels

```python
from explore_lif import Reader

reader = Reader('lif_file.lif')
series = reader.getSeries()
chosen = series[0]  # choose first image in the lif file
# get a numpy array corresponding to the 1st time point
# the shape is (x, y, channel_number)
image = chosen.getXYC(T=0)
```
