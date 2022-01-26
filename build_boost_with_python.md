Build boost with python support
===

Install python and numpy first.

    ./bootstrap --with-python=/path/to/python
    ./b2 install link=static cxxflags=-fPIC cflags=-fPIC
