# Money Detection System

This repository contains a computer vision-based money detection system designed to assist visually impaired individuals by identifying the value of bills shown to a camera. The system uses YOLOv5 for object detection and includes a text-to-speech feature for vocal feedback.
This work was done as an end of the year project at Enstab

### Features
- **Object Detection**: Detects the value of bills using a trained YOLOv5 model.
- **Text-to-Speech**: Announces the detected bill value aloud to assist visually impaired users.
- **Classification Model**: Includes a ResNet-50 classification model for additional purposes.

### Data Collection
The data used for training was manually captured. Each image of a bill was taken in various lighting conditions and angles to ensure robustness in real-world scenarios.

### Data Labeling
Labeling was performed using [Label Studio](https://labelstud.io/), an open-source data labeling tool. The annotations are saved in `.txt` format compatible with YOLOv5.

### Model Training
To train the YOLOv5 model:
1. Clone the YOLOv5 repository and navigate to it:
    ```bash
    git clone https://github.com/ultralytics/yolov5
    cd yolov5
    pip install -r requirements.txt
    ```
2. Prepare the data folder structure and split the data into training and validation sets as shown in the notebook.
3. Run the training command:
    ```bash
    python3 train.py --img 243 --epochs 30 --data dataset.yaml --weights yolov5s.pt --cache
    ```
4. **Note**: Make sure to apply necessary modifications to the YOLOv5 repository to suit the specific requirements of this project.

### Detection
The detection script is implemented in `detect.py`. It uses the trained YOLOv5 model to identify bills in real-time. The script also includes a text-to-speech feature, which announces the detected value to the user.

To run detection:
```bash
python detect.py --source 0  # Replace 0 with the path to the video file or camera index
```

### Modifications to YOLOv5 Repository
Several changes were made to the YOLOv5 codebase to integrate the text-to-speech feature and optimize the detection process. Please review the `detect.py` file for specific changes.

### Additional Models
The repository also includes a simple classification model based on ResNet-50, available in the `model_classification` notebook.

### Requirements
- Python 3.x
- PyTorch
- YOLOv5 dependencies
- Text-to-Speech libraries (e.g., `pyttsx3`)

### Future Work
- Enhance model accuracy with more diverse data.
- Expand support to detect additional currencies.

### Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

### Contact
For any inquiries, please contact Rayen Souli:
- **Email**: soulirayen@gmail.com
- **LinkedIn**: [Rayen Souli](https://www.linkedin.com/in/rayen-souli)

### License
This project is licensed under the ENSTAB License.
