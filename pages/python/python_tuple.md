---
title: python
keywords: sample
summary: "Python Tuple"
sidebar: python_sidebar
permalink: python_tuple.html
folder: python
---


<pre><code>class tuple(object):
    """
    tuple() -> empty tuple
    tuple(iterable) -> tuple initialized from iterable's items
    
    If the argument is a tuple, the return value is the same object.
    """
    def count(self, value): 
        """ T.count(value) -> integer -- return number of occurrences of value """
        return 0

    def index(self, value, start=None, stop=None): 
        """
        T.index(value, [start, [stop]]) -> integer -- return first index of value.
        Raises ValueError if the value is not present.
        """
        return 0

    def __add__(self, y): 
        """ x.__add__(y) ==> x+y """
        pass

    def __contains__(self, y): 
        """ x.__contains__(y) ==> y in x """
        pass

    def __eq__(self, y): 
        """ x.__eq__(y) ==> x==y """
        pass

    def __getattribute__(self, name): 
        """ x.__getattribute__('name') ==> x.name """
        pass

    def __getitem__(self, y): 
        """ x.__getitem__(y) ==> x[y] """
        pass

    def __getnewargs__(self, *args, **kwargs): 
        pass

    def __getslice__(self, i, j):
        """
        x.__getslice__(i, j) ==> x[i:j]
        Use of negative indices is not supported.
        """
        pass

    def __ge__(self, y): 
        """ x.__ge__(y) ==> x>=y """
        pass

    def __gt__(self, y): 
        """ x.__gt__(y) ==> x>y """
        pass

    def __hash__(self): 
        """ x.__hash__() ==> hash(x) """
        pass

    def __init__(self, seq=()): 
        """
        tuple() -> empty tuple
        tuple(iterable) -> tuple initialized from iterable's items
        
        If the argument is a tuple, the return value is the same object.
        # (copied from class doc)
        """
        pass

    def __iter__(self): 
        """ x.__iter__() ==> iter(x) """
        pass

    def __len__(self): 
        """ x.__len__() ==> len(x) """
        pass

    def __le__(self, y): 
        pass

    def __lt__(self, y): 
        pass

    def __mul__(self, n): 
        """ x.__mul__(n) ==> x*n """
        pass

    @staticmethod # known case of __new__
    def __new__(S, *more): 
        """ T.__new__(S, ...) -> a new object with type S, a subtype of T """
        pass

    def __ne__(self, y): 
        """ x.__ne__(y) ==> x!=y """
        pass

    def __repr__(self): 
        """ x.__repr__() ==> repr(x) """
        pass

    def __rmul__(self, n): 
        """ x.__rmul__(n) ==> n*x """
        pass

    def __sizeof__(self): 
        """ T.__sizeof__() -- size of T in memory, in bytes """
        pass 
<code/><pre/>
 
          
{% include links.html %}
