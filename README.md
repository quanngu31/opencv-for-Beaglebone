# opencv-for-Beaglebone

These are the binaries that I built on my beaglebone black `armv7l`. You can do `apt install` but it only comes with opencv3.2. Apparently I don't find anything like this anywhere (maybe I didn't look hard enough), and somebody (you know you who are) suggested I should post it here so here we are. It took me a *couple* of hours so I thought I might as well document it

If you want to you it with `python3.7` that comes with the board, there are some extra steps. Check `python3.7 -m site` to see where the `USER_SITE` is.

```
mkdir -p /home/debian/.local/lib/python3.7/site-packages
cp -r lib/python3.7/site-packages/cv2 /home/debian/.local/lib/python3.7/site-packages
```

Check to see if it has been installed with
```
python3 -c 'import cv2; print(cv2.__path__); print(cv2.__version__); '
```

If you are developing with `C` or `C++`, remember to link the libraries when you compile. For example:
```
gcc -Llib -lopencv_core -o <blah>
```

### Disclaimer: i don't own anything, and what works for me might not work for you, so please don't come for me!
