![Utah_teapot](https://github.com/mdoege/dancing_teapot/raw/master/teapot.gif "Dance teapot, dance!")

## A simple software renderer in Python using Gouraud shading

The input file has to be Wavefront .OBJ with vertex normals ("vn") and all faces have to be triangles. The scaling factor "s" on line 23 needs to be adjusted for different model dimensions.

### How to run

Make sure [Pillow](https://python-pillow.org/) is installed.

```py3d.py``` expects two rotation angles and a frame number on its command line.

The fastest way to create the animation is by piping the command for each frame into [GNU Parallel](https://www.gnu.org/software/parallel/):
```
python3 driver.py | parallel
```
The GIF can then be created with [ImageMagick](https://imagemagick.org/):
```
convert -delay 5 img*.png -loop 0 teapot.gif
```

