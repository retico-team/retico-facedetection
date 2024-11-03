# Face-Detection #


A ReTiCo module for Face detection. This module uses YoloV8 to detect faces from a camera feed and display a bounding box around a person's face when detected.

### Installation and requirements ###
*Clone retico repository : 
```
git clone http+git@github.com:retico-team/retico.git
```

*intsall cv2 which is OpenCV: 
```
pip istall cv2
```

### Example ###
```
import sys, os

os.environ['PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION'] = 'python'

os.environ['RETICO'] = 'retico-core'
os.environ['RETICOV'] = 'retico-vision'

sys.path.append(os.environ['RETICO'])
sys.path.append(os.environ['RETICOV'])

from retico_core import *
from retico_core.debug import DebugModule
from retico_vision.vision import WebcamModule 
from face_detect import FaceDetectionModule


webcam = WebcamModule()
detect = FaceDetectionModule()
debug = DebugModule()  

webcam.subscribe(detect)      
detect.subscribe(debug)

webcam.run()  
detect.run()
debug.run()  

print("running now!")
input()

webcam.stop()  
detect.stop()   
debug.stop()  
```

## Citation ##