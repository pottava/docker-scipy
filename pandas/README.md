Supported tags and respective `Dockerfile` links:

・latest ([pandas/versions/0.x/Dockerfile](https://github.com/pottava/docker-scipy/blob/master/pandas/versions/0.x/Dockerfile))  
・0.19 ([pandas/versions/0.x/Dockerfile](https://github.com/pottava/docker-scipy/blob/master/pandas/versions/0.x/Dockerfile))  

### Usage

Jupyter notebook with Pandas:

```
$ docker run --rm -it -p 80:8888 pottava/pandas
```

Using the Python default interpreter:

```
$ docker run --rm -it pottava/pandas python
Python 3.5.2 (default, Dec 22 2016, 10:15:38)
[GCC 6.2.1 20160822] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
>>> import pandas
>>> print(pandas.__version__)
0.19.2
>>>
>>> import matplotlib
>>> print(matplotlib.__version__)
2.0.0rc2
>>>
```
