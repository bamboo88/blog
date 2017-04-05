---
title: python
keywords: sample
summary: "Python Dictionary"
sidebar: python_sidebar
permalink: python_dic.html
folder: python
---

<pre><code>
class dict(object):
    """
    dict() -> new empty dictionary
    dict(mapping) -> new dictionary initialized from a mapping object's (key, value) pairs
    dict(iterable) -> new dictionary initialized as if via:
        d = {}
        for k, v in iterable:
            d[k] = v
    dict(**kwargs) -> new dictionary initialized with the name=value pairs
        in the keyword argument list.  For example:  dict(one=1, two=2)
    """
    def clear(self): 
        """ D.clear() -> None.  Remove all items from D. """
        pass

    def copy(self): 
        """ D.copy() -> a shallow copy of D """
        pass

    @staticmethod # known case
    def fromkeys(S, v=None): 
        """
        dict.fromkeys(S[,v]) -> New dict with keys from S and values equal to v.
        v defaults to None.
        """
        pass

    def get(self, k, d=None): 
        """ D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None. """
        pass

    def has_key(self, k):
        """ D.has_key(k) -> True if D has a key k, else False """
        return False

    def items(self): 
        """ D.items() -> list of D's (key, value) pairs, as 2-tuples """
        return []

    def iteritems(self): 
        """ D.iteritems() -> an iterator over the (key, value) items of D """
        pass

    def iterkeys(self): 
        """ D.iterkeys() -> an iterator over the keys of D """
        pass

    def itervalues(self): 
        """ D.itervalues() -> an iterator over the values of D """
        pass

    def keys(self): 
        """ D.keys() -> list of D's keys """
        return []

    def pop(self, k, d=None):
        """
        D.pop(k[,d]) -> v, remove specified key and return the corresponding value.
        If key is not found, d is returned if given, otherwise KeyError is raised
        """
        pass

    def popitem(self): 
        """
        D.popitem() -> (k, v), remove and return some (key, value) pair as a
        2-tuple; but raise KeyError if D is empty.
        """
        pass

    def setdefault(self, k, d=None): 
        """ D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D """
        pass

    def update(self, E=None, **F): 
        """
        D.update([E, ]**F) -> None.  Update D from dict/iterable E and F.
        If E present and has a .keys() method, does:     for k in E: D[k] = E[k]
        If E present and lacks .keys() method, does:     for (k, v) in E: D[k] = v
        In either case, this is followed by: for k in F: D[k] = F[k]
        """
        pass

    def values(self): 
        """ D.values() -> list of D's values """
        return []

    def viewitems(self): 
        """ D.viewitems() -> a set-like object providing a view on D's items """
        pass

    def viewkeys(self): 
        """ D.viewkeys() -> a set-like object providing a view on D's keys """
        pass

    def viewvalues(self): 
        """ D.viewvalues() -> an object providing a view on D's values """
        pass

    def __cmp__(self, y): 
        """ x.__cmp__(y) ==> cmp(x,y) """
        pass

    def __contains__(self, k): 
        """ D.__contains__(k) -> True if D has a key k, else False """
        return False

    def __delitem__(self, y): 
        """ x.__delitem__(y) ==> del x[y] """
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

    def __ge__(self, y):
        """ x.__ge__(y) ==> x>=y """
        pass

    def __gt__(self, y): 
        """ x.__gt__(y) ==> x>y """
        pass

    def __init__(self, seq=None, **kwargs): # known special case of dict.__init__
        """
        dict() -> new empty dictionary
        dict(mapping) -> new dictionary initialized from a mapping object's
            (key, value) pairs
        dict(iterable) -> new dictionary initialized as if via:
            d = {}
            for k, v in iterable:
                d[k] = v
        dict(**kwargs) -> new dictionary initialized with the name=value pairs
            in the keyword argument list.  For example:  dict(one=1, two=2)
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

    @staticmethod
    def __new__(S, *more):
        """ T.__new__(S, ...) -> a new object with type S, a subtype of T """
        pass

    def __ne__(self, y):
        """ x.__ne__(y) ==> x!=y """
        pass

    def __repr__(self): # 
        """ x.__repr__() ==> repr(x) """
        pass

    def __setitem__(self, i, y): 
        """ x.__setitem__(i, y) ==> x[i]=y """
        pass

    def __sizeof__(self): 
        """ D.__sizeof__() -> size of D in memory, in bytes """
        pass

    __hash__ = None
<code/><pre/>

{% include links.html %}
