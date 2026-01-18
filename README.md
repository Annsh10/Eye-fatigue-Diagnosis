# Comprehensive Eye Health Analysis System

A professional web-based eye health analysis platform combining AI models and health questionnaires for comprehensive diagnosis.

## 🔬 How It Works

The system provides a **comprehensive analysis** by considering ALL of the following factors:

### **AI Detection (3 Models):**
1. **Redness Detection** - Custom trained TensorFlow model
2. **Fatigue Detection** - Roboflow API (eyes-bhltc/1)
3. **Dryness Detection** - Roboflow API (dry-eye-prediction/3)

### **Health Questionnaire (8 Questions):**
1. Burning sensation
2. Itching or irritation
3. Watery eyes
4. Light sensitivity
5. Visible redness
6. Contact lens use
7. Screen time per day
8. Sleep hours per night

### **Final Diagnosis Algorithm:**
The system generates a comprehensive diagnosis by:
- Calculating an **Overall Eye Health Score** (weighted average of all 3 AI detections)
- Analyzing **questionnaire responses** to identify lifestyle risk factors
- Combining **AI findings + symptoms** to detect specific conditions
- Providing **personalized recommendations** based on all inputs
- Issuing **medical consultation alerts** when thresholds are exceeded

**Yes, the final result considers ALL factors** - both AI detection scores and questionnaire responses are analyzed together to provide professional healthcare-grade recommendations!

## Project Structure
```
eye redness/
├── app.py                      # Flask backend application
├── requirements.txt            # Python dependencies
├── models/
│   └── eye_redness_model.keras # Trained model
├── templates/
│   └── index.html             # Main HTML page
├── static/
│   ├── css/
│   │   └── style.css          # Stylesheet
│   ├── js/
│   │   └── script.js          # Frontend JavaScript
│   └── uploads/               # Uploaded images folder
└── myvenv/                    # Virtual environment
```

## Features
- 📸 Image upload via drag & drop or file browser
- 🔍 Real-time eye redness detection
- 📊 Detailed scoring (Redness Score & Normal Score)
- 💻 Modern, responsive UI
- ⚡ Fast prediction using TensorFlow

## Installation

1. Activate virtual environment:
```bash
myvenv\Scripts\activate
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

1. Start the Flask server:
```bash
python app.py
```

2. Open your browser and navigate to:
```
http://localhost:5000
```

3. Upload an eye image and get instant results!

## Model Information
- Input: Eye images (RGB)
- Output: Binary classification (Normal Eye / Red Eye)
- Architecture: Pre-trained model saved in Keras format

## API Endpoint

### POST /predict
Upload an image for eye redness detection.

**Request:**
- Method: POST
- Content-Type: multipart/form-data
- Body: file (image file)

**Response:**
```json
{
    "result": "Red Eye Detected",
    "status": "alert",
    "redness_score": 85.32,
    "normal_score": 14.68,
    "image": "data:image/jpeg;base64,..."
}
```

## Requirements
- flask==3.0.0
- tensorflow==2.19.0
- numpy==1.26.2
- pillow==10.1.0
- werkzeug==3.0.1
- inference-sdk==0.9.15

## License
This project is for educational purposes.
