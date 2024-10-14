# **Pose Estimation and Tracking Project Handout**

## **Project Overview**

In this project, you will implement a Python program to perform pose estimation and object tracking using YOLO and OpenCV. Your program will support video, webcam, and image inputs, visualize the tracking results, and save the annotated images or videos. You will also work with batch processing by applying the pose estimation to multiple images in a folder.

---

### **Project Steps and Requirements**

### **Step 1: Setup Environment**

- Install the necessary Python libraries:
  - `opencv-python`
  - `ultralytics`
  - `argparse`
  - `numpy`
- Download the YOLO pose estimation model (`yolov8l-pose.pt`).

**Deliverables**:

- A working environment where you can run Python code with the required dependencies installed.

**Verification**:

- Submit a screenshot of your environment setup with the necessary packages installed.

---

### Step 2: Pose Estimation with Keypoint Detection and Object ID Tracking**

- **Objective**:
  - Implement a function that can detect keypoints (such as eyes, shoulders, and other body parts) for any person detected in the image or video.
  - Track the object ID of each person entering the frame. Each person should have a unique ID (e.g., ID1, ID2, etc.), and if someone leaves and returns, they should be assigned a new ID.

#### **Requirements**:

- **Keypoint Detection**:
  
  - You need to utilize the YOLO model’s pose estimation feature to detect keypoints on each detected person.
  - Keypoints should be clearly labeled in the image or video output, similar to the eyes, shoulders, and other body parts in the sample image.
  
  ![image.png](https://files.slack.com/files-tmb/TMG35UR27-F07RT9FTE8K-a6a843dc06/image_360.png)

- **Object ID Tracking**:
  
  - Implement a tracking mechanism that assigns a unique ID to each new detection.
  - Ensure that once an object (person) leaves the frame and re-enters, they are assigned a new ID.

#### **Implementation**:

- Modify the `pose_estimation` function to:
  - Track keypoints for each person detected, as shown in the example image (e.g., eyes, shoulders).
  - Assign unique IDs for each person entering the frame. The IDs should not be reused when the person leaves and comes back into the frame.
- The keypoint detection should be visualized by drawing small circles at each detected keypoint (e.g., green dots), and the bounding box for each person should display their ID and confidence score.

#### **Testing**:

- Test with both an image and a video:
  - Use an image containing multiple people and ensure that keypoints and IDs are correctly displayed.
  - Test with a video where a person leaves and re-enters the frame. Ensure that the person is assigned a new ID when they re-enter.
- **Deliverables**:
  - Submit the Python code implementing keypoint detection and object tracking.
  - Provide a sample output image similar to the one shown (with keypoints and IDs annotated).
  - Provide a video showing object ID tracking in action.

#### **Sample Expected Output**:

- For an image or video like the one shown, you should:
  - Detect keypoints (e.g., eyes, shoulders) and mark them with small circles.
  - Display bounding boxes around detected people with a label showing the ID (`id: 1, id: 2, etc.`) and confidence score.

By being specific in these requirements, you ensure that students understand exactly what is expected in terms of object tracking and keypoint detection, leading to better clarity and outcome.

---

### **Step 3: Add Command-Line Interface (CLI)**

- Implement an easy-to-use command-line interface (CLI) for your script using the `argparse` library.
- The user should be able to specify:
  - The model path.
  - The input source (image/video/webcam/folder).
  - Whether to display (`--view-img`) or save (`--save-img`) the results.

**Deliverables**:

- The modified script that can take input arguments from the command line.

**Verification**:

- Run the script using at least two different input sources (e.g., an image and a video). Document the CLI command you used.

---

### **Step 4: Video and Image Tracking with Output**

- Extend your pose estimation function to allow the saving of annotated images and videos.
- Implement the `increment_path` function to avoid overwriting files.
- Ensure the program can:
  - Save processed videos and images to the correct output directory.

**Deliverables**:

- The code that allows users to save the output video or image with annotated results.
- Make sure that files are saved in unique directories to avoid overwriting.

**Verification**:

- Submit one saved video and one saved image showing the tracking and pose estimation results.

---

### **Step 5: Batch Processing of Folder of Images**

- Extend the program to process an entire folder of images and apply the pose estimation function to each image.
- Ensure the results are saved in a separate folder.

**Deliverables**:

- The code for the `process_folder` function, along with a test folder of images that has been processed.

**Verification**:

- Submit the folder with the processed images.

---

### **Step 6: Optimization and Error Handling**

- Add error handling for invalid inputs (e.g., non-existent file paths).
- Ensure the program gracefully handles cases such as empty input files or unsupported file types.
- Optimize the video processing pipeline for real-time use.

**Deliverables**:

- The updated code with error handling and optimized for real-time use.

**Verification**:

- Submit the final Python file with optimizations and demonstrate error handling with example invalid input cases.

---

### **Bonus Step: Additional Features (Optional)**

- Add any extra features to your project, such as:
  - GPU acceleration for real-time processing.
  - A graphical user interface (GUI) for user interaction.
  - Implement additional models for pose estimation or tracking.

**Deliverables**:

- Document any additional features and submit the updated code.

**Verification**:

- Demonstrate the working of the additional feature with a video or image.

---

## **Grading Rubric**

| **Criteria**                              | **Points** | **Description**                                                                                     |
| ----------------------------------------- | ---------- | --------------------------------------------------------------------------------------------------- |
| **Step 1: Environment Setup**             | 5          | Successful setup of the environment with necessary packages installed.                              |
| **Step 2: Pose Estimation Function**      | 20         | Function to estimate poses and track objects in images and videos implemented correctly.            |
| **Step 3: CLI Interface**                 | 10         | CLI interface implemented correctly with options for model, source, and output.                     |
| **Step 4: Output Saving**                 | 15         | Correct implementation of saving annotated images and videos, with proper handling of file paths.   |
| **Step 5: Batch Processing**              | 10         | Successfully process a folder of images and apply pose estimation to each.                          |
| **Step 6: Optimization & Error Handling** | 10         | Program includes error handling for invalid inputs and is optimized for real-time video processing. |
| **Code Quality and Documentation**        | 10         | Clean, well-organized code with proper comments and documentation.                                  |
| **Bonus Step (Optional)**                 | 10         | Implement any additional features (GPU acceleration, GUI, etc.)                                     |
| **Total**                                 | 80 + 10    | Maximum score is 80, with up to 10 bonus points for additional features.                            |

---

### **Submission Guidelines**

- Submit your Python files in a zip folder.
- Include any output videos, images, and screenshots as separate files in the zip.
- Clearly label each step and the associated deliverables.
- Make sure your code is clean, well-commented, and easy to understand.

### **Deadline**

- The project must be submitted by **[insert due date]**.
