# Face Recognition Attendance System

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![OpenCV](https://img.shields.io/badge/opencv-4.x-green.svg)
![face_recognition](https://img.shields.io/badge/face__recognition-1.3.0-yellow.svg)

A Python-based application that uses facial recognition to automate the process of marking attendance and logs the data into an Excel sheet. The system can also calculate its own accuracy based on a test dataset.

## 🌟 Features

-   **Real-time Face Detection**: Captures images via webcam for face detection.
-   **Automated Attendance Logging**: Marks attendance with name, SAP ID, date, and time.
-   **Excel Integration**: Automatically saves attendance records to an `attendance.xlsx` file.
-   **Accuracy Evaluation**: Includes a script to calculate performance metrics like Accuracy, Precision, Recall, and F1-Score.
-   **Easy Setup**: Simple to set up with a dataset of known faces.

## ⚙️ How It Works

1.  **Load Known Faces**: The system loads images from the `dataset` directory. Each image filename should be in the format `Name_SAPID.jpg`.
2.  **Capture Image**: It uses the computer's webcam to capture a live image for recognition.
3.  **Recognize Faces**: The captured face is compared against the known faces from the dataset.
4.  **Mark Attendance**: If a match is found, the system records the person's name, SAP ID, and the current timestamp in `attendance.xlsx`. It ensures a person is marked only once per day.
5.  **Evaluate Performance**: A separate part of the script evaluates the model's accuracy by comparing recognition results against a `testset` directory.

## 🚀 Getting Started

Follow these instructions to get a copy of the project up and running on your local machine.

### Prerequisites

-   Python 3.8 or higher
-   `pip` (Python package installer)
-   A webcam connected to your computer

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
    cd your-repository-name
    ```

2.  **Create and populate the dataset:**
    -   Create a folder named `dataset` in the project's root directory.
    -   Add images of the individuals you want to recognize.
    -   **Important**: Rename the image files to the format `Name_SAPID.jpg` (e.g., `JohnDoe_12345.jpg`).

3.  **Install dependencies:**
    It's recommended to use a virtual environment.
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```
    Install the required packages using pip:
    ```bash
    pip install opencv-python face_recognition numpy pandas openpyxl
    ```

### Usage

1.  **Run the main application:**
    Execute the Python script to start the attendance system.
    ```bash
    python ai.py
    ```

2.  **Capture Image:**
    -   The console will prompt you to press `Enter` to capture an image.
    -   A window will open showing the feed from your webcam.
    -   Once the image is captured, the system will perform recognition.

3.  **Check Attendance:**
    -   After a successful recognition, the attendance will be logged.
    -   You can find the records in the `attendance.xlsx` file created in the project directory.

## 📊 Performance Evaluation

To test the accuracy of the face recognition model:

1.  **Create a test set:**
    -   Create a folder named `NewTestset`.
    -   Add test images to this folder. Some images should be of people in your dataset, and some can be of unknown individuals.
    -   Label the images in the same `Name_SAPID.jpg` format. For unknown individuals, you can name the file `Unknown_1.jpg`, `Unknown_2.jpg`, etc.

2.  **Run the evaluation:**
    The script contains a section to calculate accuracy metrics. Ensure the paths to `NewDataset` and `NewTestset` are correctly configured in the script and run it. The console will print the Accuracy, Precision, Recall, and F1-Score.

## 📂 Project Structure


.
├── dataset/
│   ├── JohnDoe_12345.jpg
│   └── JaneSmith_67890.jpg
├── NewTestset/
│   ├── JohnDoe_12345.jpg
│   └── Unknown_1.jpg
├── ai.py
├── attendance.xlsx (generated after running)
└── README.md


-   `dataset/`: Directory containing images of known individuals for training the recognition model.
-   `NewTestset/`: Directory containing images for evaluating the model's performance.
-   `ai.py`: The main Python script containing all the logic for face recognition and attendance marking.
-   `attendance.xlsx`: The Excel file where attendance records are stored.

## 🛠️ Dependencies

-   **OpenCV (`opencv-python`)**: For image processing and webcam access.
-   **face_recognition**: A simple and powerful library for face recognition.
-   **NumPy**: For numerical operations.
-   **Pandas** & **Openpyxl**: For creating and managing the Excel attendance sheet.

## 💡 Future Improvements

-   [ ] Develop a graphical user interface (GUI) using Tkinter or PyQt for a more user-friendly experience.
-   [ ] Implement liveness detection to prevent spoofing attacks using static photos.
-   [ ] Optimize for performance to handle a larger number of faces in real-time.
-   [ ] Store attendance data in a more robust database system like SQLite or PostgreSQL.

## Preview
<img width="640" height="480" alt="LakshyaDubey_70022200396" src="https://github.com/user-attachments/assets/e9ba270c-2955-4621-804d-2ebe7a215c52" />
<img width="640" height="480" alt="SuhaniKhandelwal_70022200380" src="https://github.com/user-attachments/assets/85c0a913-a5b5-4c66-b5f8-a3fb4b9348f7" />
<img width="1919" height="1002" alt="image" src="https://github.com/user-attachments/assets/b80f9a0a-c66a-4c20-a46c-0169c28a359d" />
<img width="1919" height="993" alt="image" src="https://github.com/user-attachments/assets/73f4e4c1-9665-4ead-9647-25a32c8b8a39" />


