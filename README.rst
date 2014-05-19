=======
pyjstat
=======

**pyjstat** is a python module for **JSON-stat** formatted data manipulation
which allows reading and writing JSON-stat [1]_ format with python,using the
DataFrame structures provided by the widely accepted pandas library [2]_.
The JSON-stat format is a simple lightweight JSON format for data
dissemination. Pyjstat is inspired in rjstat [3]_, a library to read and write
JSON-stat with R, by ajschumacher. Note that, like in the rjstat project,
not all features are supported (i.e. not all metadata are converted).

Installation
============

pyjstat requires pandas package. For installation::

pip install pyjstat

Usage
=====

From JSON-stat to pandas DataFrame
-----------------------------------

Typical usage often looks like this::

    #!/usr/bin/env python

    import pyjstat
    import urllib2
    import json
    
    results = pyjstat.from_json_stat(json.load(urllib2.urlopen(
                             'http://json-stat.org/samples/oecd-canada.json')))
    print results

From pandas DataFrame to JSON-stat
----------------------------------

The same data can be converted into JSON-stat, with some unavoidable metadata
loss::

    #!/usr/bin/env python

    import pyjstat
    import urllib2
    import json
    
    results = pyjstat.from_json_stat(json.load(urllib2.urlopen(
                             'http://json-stat.org/samples/oecd-canada.json')))
    print results