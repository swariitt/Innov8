# Sign Reader

A browser app that recognizes four hand signs from your webcam (Hello, Yes, No, Thanks) and shows the matching sign image when you speak or type a word.

## Features
- **Sign to text:** MediaPipe Hand Landmarker finds 21 points on your hand, and a small neural network (trained in the browser at startup from the embedded photos) classifies the sign.
- **Speech to sign:** speak or type a word and see its sign image. Supports English and Hindi input (for example "hello", "namaste", "haan", "nahi", "dhanyavad").
- **Input and output language:** separate English/Hindi menus for what the microphone listens for and for the displayed words and spoken voice.
- **Improve accuracy:** record 3-second webcam samples for any sign; the model retrains automatically. Samples are saved in the browser (localStorage).

## Run it
1. Open `index.html` in Chrome (internet is needed to load MediaPipe and its model).
2. Wait for "Training done", then press **Start camera**.
3. If the camera does not open from a file, run `python -m http.server` in this folder and open `http://localhost:8000`.

## Notes
- Only fixed hand shapes are recognized, not movement.
- With so few training photos the model can make mistakes, so use the Record buttons to add more samples.
- `index.html` contains the training photos embedded inside it. Keep the repository private if the photos show your face.

## Built with
HTML, CSS, JavaScript, [MediaPipe Tasks Vision](https://developers.google.com/mediapipe), Web Speech API.
