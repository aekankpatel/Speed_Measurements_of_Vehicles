# Speed Measurement of Vehicles

## Code Explanation

### Code 1: Background Subtraction and Contour Detection
This code focuses on detecting moving vehicles in a video using background subtraction. Key steps include:

1. **Video Input**: The video is read frame-by-frame using `cv2.VideoCapture`.
2. **Background Subtraction**: `cv2.createBackgroundSubtractorMOG2` is used to separate moving objects from the background.
3. **Noise Reduction**: Morphological operations (erosion and dilation) are applied to clean the foreground mask.
4. **Contour Detection**: `cv2.findContours` is used to detect contours representing moving vehicles.
5. **Bounding Boxes**: Detected contours are filtered by size, and bounding boxes are drawn around the vehicles.
6. **Display**: The processed frames with bounding boxes are displayed in real-time.

### Code 2: Vehicle Tracking and Speed Measurement
This code builds on the first one by adding vehicle tracking and speed measurement. Key steps include:

1. **Vehicle Detection**: Similar to the first code, moving vehicles are detected using background subtraction and contour detection.
2. **Vehicle Tracking**: Detected vehicles are tracked across consecutive frames to calculate their positions over time.
3. **Speed Calculation**: 
   - The pixel distance traveled by a vehicle is converted to real-world distance using a calibration factor.
   - Speed is calculated based on the time taken to travel the known distance.
4. **Annotations**: The calculated speed is displayed on the video along with bounding boxes for the vehicles.
5. **Display**: The video with speed annotations is shown in real-time.

