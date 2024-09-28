# Requirements:
Please install ultralytics, cv2, numpy and pandas before opening.\
`pip install ultralytics`\
`pip install opencv-python`\
`pip install numpy`\
`pip install pandas`\

# Problem:
Create an inference solution that can observe a real-time camera stream and will raise an alert if more than n (for example 4) people are visible continuously for more than 2 minutes. You may mark a region to observe.
The code should have a script that can take an image or video and demo the alerts. You may use free videos at https://www.pexels.com/search/videos/crowd/

# Approach:
I am using a YOLO pre-trained model from the Ultralytics library to be able to deploy models quickly and with minimum effort. Extra logic like timers and data saving is then applied to the model's output.

The YOLO version that we’ll be using is YOLOv8x, which stands at around 130 MB. The most advanced YOLO solutions recently released by Ultralytics itself. Since the model is already pre-trained using some really big datasets, we don’t need to train it anymore, just cap the target classes to label ‘0’ to only detect instances of person in the image.

Ultralytics YOLO model output is already structured so we can easily pull what we need from the data, this data can be processed to produce a ‘trailing’ effect in the video stream that can be customized. The output can also be easily saved to a CSV file by putting it in a dataframe.

Other libraries used are opencv2 for video or webcam handling, NumPy for handling tensor data, and pandas for the dataframe. Built-in Python libraries that are used are defaultdict for output handling and time for time for timer.
