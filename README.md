# Swimming Pool Garbage Detection

AI-powered Flask web app for detecting garbage in swimming pool images, uploaded videos, and a live webcam feed using a trained YOLO model.

## Features

- Professional landing page at `/`
- Detection dashboard at `/detect-media`
- Upload and analyze pool images
- Upload and analyze pool videos
- Live webcam/CCTV-style monitoring
- Popup notifications for:
  - garbage detected
  - pool clean / no garbage detected
- Annotated output saved in `static/results`

## Project Structure

```text
pool_garbage_flask_app/
├── app.py
├── README.md
├── requirements.txt
├── requirement.txt
├── yolov8n.pt
├── model/
│   └── swimming_pool_garbage_yolo.pt
├── static/
│   ├── uploads/
│   └── results/
└── templates/
    ├── index.html
    └── landing.html
```

## Requirements

- Python 3.10 or newer recommended
- Git
- Webcam if you want to use the live camera feed

## Run On Another Laptop

### 1. Clone the repository

```bash
git clone https://github.com/teamcore38-droid/Swimming-pool-garbage-detection.git
cd Swimming-pool-garbage-detection
```

### 2. Create a virtual environment

Windows PowerShell:

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

Windows CMD:

```cmd
python -m venv venv
venv\Scripts\activate
```

macOS / Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

Note: `requirements.txt` is the standard install file. The older `requirement.txt` is also kept in the project for compatibility.

### 4. Run the app

```bash
python app.py
```

### 5. Open in browser

```text
http://127.0.0.1:5000/
```

Landing page:

- `/`

Detection dashboard:

- `/detect-media`

## How To Use

### Upload image or video

1. Open the dashboard.
2. Upload a swimming pool image or video.
3. Click `Analyze Upload`.
4. Review the popup result:
   - alert if garbage is detected
   - safe notification if no garbage is detected

### Live camera feed

1. Open the dashboard.
2. Scroll to the live monitoring section.
3. The app will try to use the laptop webcam by default.

## Important Notes

- The trained model is loaded from:

```text
model/swimming_pool_garbage_yolo.pt
```

- Generated uploads are saved in:

```text
static/uploads
```

- Generated annotated results are saved in:

```text
static/results
```

- If the webcam does not open on another laptop:
  - make sure no other app is using the camera
  - allow camera permissions for Python if prompted

- Video codec support can vary between laptops because OpenCV uses the local system video backend.

## Troubleshooting

### `ModuleNotFoundError`

Make sure the virtual environment is activated and reinstall dependencies:

```bash
pip install -r requirements.txt
```

### Model file not found

Make sure this file exists:

```text
model/swimming_pool_garbage_yolo.pt
```

### Port 5000 already in use

Close the app using port `5000`, or change the port in `app.py`.

## Main Dependencies

- Flask
- Ultralytics
- OpenCV
- NumPy
- Pillow
- Matplotlib
- Pandas
- PyYAML
