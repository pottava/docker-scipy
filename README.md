Supported tags and respective `Dockerfile` links:

・latest ([versions/0.x/Dockerfile](https://github.com/pottava/docker-scipy/blob/master/versions/0.x/Dockerfile))  
・0.18 ([versions/0.x/Dockerfile](https://github.com/pottava/docker-scipy/blob/master/versions/0.x/Dockerfile))  
・0.18-notebook ([jupyter/versions/4.2/Dockerfile](https://github.com/pottava/docker-scipy/blob/master/jupyter/versions/4.2/Dockerfile))


### Usage

SciPy was installed with OpenBLAS & LAPACK.

```
$ docker run --rm pottava/scipy:0.18 -c 'import scipy; scipy.show_config()'
```

Using the Python default interpreter:

```
$ docker run --rm -it pottava/scipy:0.18
Python 3.5.2 (default, Dec 22 2016, 10:15:38)
[GCC 6.2.1 20160822] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
>>> import scipy
>>> print(scipy.__version__)
0.18.1
>>>
>>> import numpy
>>> print(numpy.__version__)
1.11.3
>>>
```

With Jupyter notebook:

```
$ docker run --rm -p 80:8888 pottava/scipy:0.18-notebook
```
