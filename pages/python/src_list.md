---
title: python
keywords: sample
summary: "Python List Source"
sidebar: python_sidebar
permalink: python_src_list.html
folder: python
---

<pre><code>class list(object):
    """
    list() -> new empty list
    list(iterable) -> new list initialized from iterable's items
    """
    def append(self, p_object): 
        """ L.append(object) -- append object to end """
        pass

    def count(self, value): 
        """ L.count(value) -> integer -- return number of occurrences of value """
        return 0

    def extend(self, iterable):
        """ L.extend(iterable) -- extend list by appending elements from the iterable """
        pass

    def index(self, value, start=None, stop=None): 
        """
        L.index(value, [start, [stop]]) -> integer -- return first index of value.
        Raises ValueError if the value is not present.
        """
        return 0

    def insert(self, index, p_object): 
        """ L.insert(index, object) -- insert object before index """
        pass

    def pop(self, index=None):
        """
        L.pop([index]) -> item -- remove and return item at index (default last).
        Raises IndexError if list is empty or index is out of range.
        """
        pass

    def remove(self, value): 
        """
        L.remove(value) -- remove first occurrence of value.
        Raises ValueError if the value is not present.
        """
        pass

    def reverse(self):
        """ L.reverse() -- reverse *IN PLACE* """
        pass

    def sort(self, cmp=None, key=None, reverse=False): 
        """
        L.sort(cmp=None, key=None, reverse=False) -- stable sort *IN PLACE*;
        cmp(x, y) -> -1, 0, 1
        """
        pass

    def __add__(self, y): 
        """ x.__add__(y) <==> x+y """
        pass

    def __contains__(self, y): 
        """ x.__contains__(y) <==> y in x """
        pass

    def __delitem__(self, y): 
        """ x.__delitem__(y) <==> del x[y] """
        pass

    def __delslice__(self, i, j): 
        """
        x.__delslice__(i, j) <==> del x[i:j]
        Use of negative indices is not supported.
        """
        pass

    def __eq__(self, y):
        """ x.__eq__(y) <==> x==y """
        pass

    def __getattribute__(self, name): 
        """ x.__getattribute__('name') <==> x.name """
        pass

    def __getitem__(self, y): 
        """ x.__getitem__(y) <==> x[y] """
        pass

    def __getslice__(self, i, j):
        """
        x.__getslice__(i, j) <==> x[i:j]
        Use of negative indices is not supported.
        """
        pass

    def __ge__(self, y): 
        """ x.__ge__(y) <==> x>=y """
        pass

    def __gt__(self, y):
        """ x.__gt__(y) <==> x>y """
        pass

    def __iadd__(self, y): 
        """ x.__iadd__(y) <==> x+=y """
        pass

    def __imul__(self, y): 
        """ x.__imul__(y) <==> x*=y """
        pass

    def __init__(self, seq=()): 
        """
        list() -> new empty list
        list(iterable) -> new list initialized from iterable's items
        # (copied from class doc)
        """
        pass

    def __iter__(self): 
        """ x.__iter__() <==> iter(x) """
        pass

    def __len__(self): 
        """ x.__len__() <==> len(x) """
        pass

    def __le__(self, y):
        """ x.__le__(y) <==> x<=y """
        pass

    def __lt__(self, y): 
        """ x.__lt__(y) <==> x<y """
        pass

    def __mul__(self, n): 
        """ x.__mul__(n) <==> x*n """
        pass

    @staticmethod # known case of __new__
    def __new__(S, *more): 
        """ T.__new__(S, ...) -> a new object with type S, a subtype of T """
        pass

    def __ne__(self, y): 
        """ x.__ne__(y) <==> x!=y """
        pass

    def __repr__(self): 
        """ x.__repr__() <==> repr(x) """
        pass

    def __reversed__(self): 
        """ L.__reversed__() -- return a reverse iterator over the list """
        pass

    def __rmul__(self, n): 
        """ x.__rmul__(n) <==> n*x """
        pass

    def __setitem__(self, i, y):
        """ x.__setitem__(i, y) <==> x[i]=y """
        pass

    def __setslice__(self, i, j, y): 
        """
        x.__setslice__(i, j, y) <==> x[i:j]=y
        Use  of negative indices is not supported.
        """
        pass

    def __sizeof__(self): 
        """ L.__sizeof__() -- size of L in memory, in bytes """
        pass

    __hash__ = None </code></pre>
    

{% include links.html %}
