# Face Detection

Face & eye detection: simple demo based on haar-cascade samples in OpenCV.

### Setup
| Name |  Version |
| :--: | :---: |
| Python | 3.7 (3.x) |
| OpenCV | 4.0 |

Run with `python face_detection.py image_path/name.png` to provide file name as argument:

e.g. `python face_detection.py friends.png`

Or just run `python face_detection.py` and add file name later.

### Modify

This can be used with any other [haar-cascades](https://github.com/opencv/opencv/tree/master/data/haarcascades).

Whole body detection by simply changing to `haarcascade_fullbody.xml`

* Change `face_cascade` to `body_cascade`

* Switch face detection to whole body detection with:
```
bodies = body_cascade.detectMultiScale(
    gray,
    # your settings
    scaleFactor=1.5,
    minNeighbors=5,
    minSize=(30, 30)
)
```

and

```
for (x, y, w, h) in bodies:
    cv2.rectangle(img, (x, y), (x+w, y+h), (0, 255, 0), 2)
```

### TO DO features list

Here sample ideas for future development.

Create fork of this repo.
Add features:

1. Check if a file (or path to file) exists. Ask user again to provide correct file
2. Detect both faces and whole bodies. Return count of detected objects
3. Automate the attachment of images. Allow user to specify the path to the folder
4. ...your ideas...

### Contact
Created by ritaly, you can find me on my blog [www.flynerdpl](https://www.flynerd.pl/) - feel free to contact me!

Inspiration [Face recognition with Python](https://realpython.com/blog/python/face-recognition-with-python/)