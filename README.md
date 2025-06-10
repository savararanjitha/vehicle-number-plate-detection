
Vehicle Number Plate Detection Using YOLOv8 and OpenCV
This project performs Automatic Number Plate Recognition (ANPR) on vehicles in a video using YOLOv8-based detections and OpenCV for visualization. It reads detection results from a CSV file, extracts license plate crops, overlays these on the video frames, draws stylish bounding boxes around cars and plates, and finally outputs an annotated video.
Project Overview
Automatic Number Plate Recognition (ANPR) is widely used for vehicle monitoring, traffic management, and security. This project utilizes YOLOv8 for detecting cars and license plates, then uses OpenCV to highlight detected vehicles and license plates on each video frame, along with overlaying the recognized license plate numbers and cropped plate images.
Features
•	Reads vehicle and license plate detection results from CSV
•	Draws custom corner-style green bounding boxes around vehicles
•	Draws red bounding boxes around license plates
•	Extracts and resizes the best license plate image per vehicle
•	Overlays cropped license plate images and license numbers above each vehicle
•	Saves the annotated video as output

Requirements
•	Python 3.7+
•	OpenCV (cv2)
•	NumPy
•	Pandas
Install the dependencies using:
Pip install opencv-python numpy pandas

Setup and Usage
1.	Place your input video file (e.g., car.mp4) in the project directory.
2.	Provide the detection results CSV file (e.g., test_interpolated.csv), which contains detection bounding boxes and license plate recognition results.
3.	Run the Python script:
python main.py
4.	The processed video with annotations will be saved as out.mp4 in the current directory.
Note: Update the paths of the video and CSV files in the script if they differ from the defaults.
Input Data Format
The CSV file must have the following columns:
Column Name	Description
frame_nmr	Frame number in the video
car_id	Unique ID assigned to each detected car
car_bbox	Bounding box coordinates of the car [x1, y1, x2, y2]
license_plate_bbox	Bounding box coordinates of the license plate [x1, y1, x2, y2]
license_number	Recognized license plate number (string)
license_number_score	Confidence score of the license number recognition

How It Works
•	Step 1: The script reads the CSV to gather detection data.
•	Step 2: For each unique car, it finds the frame where the license plate recognition confidence is highest and extracts the license plate crop from that frame.
•	Step 3: Iterates through all video frames:
o	Draws green corner-style bounding boxes around detected cars.
o	Draws red rectangles around detected license plates.
o	Overlays the cropped license plate image above the vehicle bounding box.
o	Prints the recognized license plate number above the crop.
•	Step 4: Writes the annotated frames to a new video file (out.mp4).

Output
•	An .mp4 video file (out.mp4) with the following annotations:
o	The green corner borders on the cars
o	Red rectangles on license plates
o	Cropped license plate image displayed above each car
o	Recognized license plate number displayed above the crop

Future Improvements
•	Add CLI arguments to specify video and CSV paths dynamically.
•	Integrate YOLOv8 model and OCR directly for end-to-end detection and recognition.
•	Support multiple license plates per vehicle.
•	Develop a web-based interface for real-time video stream processing.
•	Add error handling and logging for better robustness.

Contact
For questions, suggestions, or contributions, please feel free to open an issue or submit a pull request.

Thank you for checking out this project! 🚗🔍

