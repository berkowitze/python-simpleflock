python-simpleflock
==================

Python module for very simple flock-based file locking.

Features
--------
* Uses Python's ```with``` syntax.
* Doesn't complain if the lock file already exists but is stale.
* Cleans up the lock file after itself.
* Supports a timeout.

Example
-------
```python
import simpleflock

with simpleflock.SimpleFlock("/tmp/foolock"):
   # Do something.
   pass

# Raises an IOError in 3 seconds if unable to acquire the lock.
with simpleflock.SimpleFlock("/tmp/foolock", timeout = 3):
   # Do something.
   pass

# Time to sleep between attempts to acquire the lock (0.1 by default)
with simpleflock.SimpleFlock("/tmp/foolock", refresh_interval = 0.01):
   # Do something.
   pass
```

BUGS
----
Unknown.

Contributing
------------
Contributions welcome!
