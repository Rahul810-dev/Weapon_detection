**A web app that detects weapons** in images, uploaded videos and a live webcam feed, using a custom-trained **YOLOv8** model served through **Flask**.

## Highlights

- **4,000+ images** annotated and used to train the model
- **90%+ accuracy** after training YOLOv8
- **~25 FPS** real-time inference through the Flask backend

## Features

- **Image detection:** upload a JPG, JPEG or PNG and see the annotated result on the page
- **Live webcam detection:** annotated frames streamed to the browser
- **Video detection:** upload an MP4, which is processed frame by frame, with the annotated output saved as `output.mp4`
- **Performance and chart pages** in the web interface

## Tech Stack

**Python 3.10.9**, **Flask**, **YOLOv8 (Ultralytics)**, **OpenCV**, TensorFlow, NumPy, pandas, scikit-learn, Matplotlib

## Setup

**Windows only:** install the [Visual C++ Redistributable](https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0) (x64, `vc_redist.x64.exe`).

```bash
git clone https://github.com/Rahul810-dev/REPO-NAME.git
cd REPO-NAME
python -m venv venv
venv\Scripts\activate
pip install scikit-learn==1.2.2 flask==2.3.2 matplotlib==3.7.1 pandas==2.0.0 numpy==1.23.5 tensorflow==2.12.0 ultralytics==8.0.121
```

Create an empty `uploads` folder in the project root if it doesn't exist. Uploaded videos are saved there.

## Run

```bash
python app.py
```

Open `http://localhost:5000`. To use another port: `python app.py --port 8000`.

## Pages

| Route | Purpose |
|---|---|
| `/` | Home |
| `/image` | Upload an image for detection |
| `/video` | Upload a video for detection |
| `/webcam` | Live webcam detection |
| `/performance` | Model performance |
| `/chart` | Charts |

## Project Structure

```
REPO-NAME/
├── app.py             # Flask server and detection routes
├── best.pt            # trained YOLOv8 weights
├── templates/         # HTML pages
├── uploads/           # uploaded videos
└── requirements.txt
```

## Notes

- Video processing opens an OpenCV preview window, so run the app on a local machine with a display.
- Webcam detection uses the default camera.

## Author

**Rahul N**, final-year CSE student
[LinkedIn](https://linkedin.com/in/rahul-n-a0b5b9314) | [Portfolio](https://rahul810-dev.github.io/MyPortfolio)
