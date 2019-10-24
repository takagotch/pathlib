### pathlib
---
https://github.com/python/cpython/blob/3.7/Lib/pathlib.py

https://docs.python.org/3/library/pathlib.html

```py

class _PathParents(Sequence):
  __slots__ = ('_patchcls', '_drv', '_root', '_parts')
  __slots__ = ('_pathcls', '_drv', '_root', '_parts')
  
  def __init__(self, path):
    self._patchcls = type(path)
    self.drv = path._drv
    self._root = path._root
    self._parts = path._parts
    
  def __len__(self):
    if self._drv or self._root:
      return len(self._parts) - 1
    else:
      return len(self._parts)
      
  def __getitem__(self, idx):
    if idx < 0 or idx >= len(self):
      raise IndexError(idx)
    return self._pathcls._from_parsed_parts(self._drv, self._root,
        self._parts[:-idx - 1])
  
  def __repr__(self):
    return "<{}.parents>".format(self._pathcls.__name__)
  
class PurePath(object):
  
  __slots__ = (
  
  )
  
  def __new__(cls, *args):
  
  
```

```
```

```
```
