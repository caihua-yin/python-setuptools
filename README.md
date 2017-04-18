Hello world for python setupools
==============
#### Install
sudo apt-get install python-setuptools

#### Bootstrap setuptools
wget http://peak.telecommunity.com/dist/ez_setup.py
sudo python ez_setup.py

#### Create setup.py
vi helloworld/setup.py

#### Packaging
* Stuff before packaging:
```
python-setuptools$ tree
.
|-- helloworld
|   |-- demo
|   |   |-- demo.conf
|   |   `-- src
|   |       |-- __init__.py
|   |       `-- math.py
|   `-- setup.py
`-- README.md
```

* Packaging:
```
helloworld$ python setup.py bdist_egg
```

* Stuff after packaging:
```
$ tree
.
|-- helloworld
|   |-- build
|   |   `-- bdist.linux-x86_64
|   |-- demo
|   |   |-- demo.conf
|   |   `-- src
|   |       |-- __init__.py
|   |       `-- math.py
|   |-- dist
|   |   `-- helloworld-0.1-py2.7.egg
|   |-- helloworld.egg-info
|   |   |-- dependency_links.txt
|   |   |-- PKG-INFO
|   |   |-- SOURCES.txt
|   |   `-- top_level.txt
|   `-- setup.py
`-- README.md
```

#### Install the package
```
helloworld$ sudo python setup.py install
```
Package is installed at: /usr/local/lib/python2.7/dist-packages/helloworld-0.1-py2.7.egg

#### Use the installed package
$ python
Python 2.7.6 (default, Oct 26 2016, 20:30:19)
[GCC 4.8.4] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import demo
>>> demo.test()
Hello world!
>>>

#### Clean
helloworld$ rm -rf build dist helloworld.egg-info

#### Reference
http://yansu.org/2013/06/07/learn-python-setuptools-in-detail.html
https://setuptools.readthedocs.io/en/latest/setuptools.html
https://pythonhosted.org/an_example_pypi_project/setuptools.html
