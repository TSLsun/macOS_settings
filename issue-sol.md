# some issues and solutions

### 1. MemoryError when executing vi after update macOS to Mojave 10.14 & 10.14.1, thus powerline will not work

[solution ref](https://github.com/powerline/powerline/issues/1947#issuecomment-431784358)

Comment line 279 in `/System/Library/Frameworks/Python.framework/Versions/2.7/lib/python2.7/ctypes/__init__.py`

```
265 def _reset_cache():
266     _pointer_type_cache.clear()
267     _c_functype_cache.clear()
268     if _os.name in ("nt", "ce"):
269         _win_functype_cache.clear()
270     # _SimpleCData.c_wchar_p_from_param
271     POINTER(c_wchar).from_param = c_wchar_p.from_param
272     # _SimpleCData.c_char_p_from_param
273     POINTER(c_char).from_param = c_char_p.from_param
274     _pointer_type_cache[None] = c_void_p
275     # XXX for whatever reasons, creating the first instance of a callback
276     # function is needed for the unittests on Win64 to succeed.  This MAY
277     # be a compiler bug, since the problem occurs only when _ctypes is
278     # compiled with the MS SDK compiler.  Or an uninitialized variable?
279     CFUNCTYPE(c_int)(lambda: None)
```

PS: The `__init__.py` file is system read-only file, and you need to run command `csrutil disable` in mac recovery mode (press `command+R` when booting up)