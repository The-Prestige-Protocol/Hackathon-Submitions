#Kop Coders
## problem statement
Deepfake Detection System
Problem Context
AI-generated fake videos, voices, and images are becoming increasingly realistic and accessible. Deepfakes are now being used for misinformation, scams, identity fraud, political manipulation, fake evidence creation, and impersonation attacks.
The challenge today is not generating deepfakes — it is identifying them quickly and reliably before they spread. Existing users often cannot distinguish between authentic and manipulated content, especially on social media and messaging platforms.
Challenge
Build a system capable of detecting manipulated or AI-generated media content and helping users verify authenticity.
The solution should focus on identifying suspicious patterns in videos, audio, images, or text-based media while presenting results in a way that is understandable and actionable for users

Team members:
Gino barros
Kiara Fernandes
joylen Fernandes
lysander Barreto

Github repo:
https://github.com/kiaraLuan/DeepShield

Features
AI Audio Deepfake Detection: Upload voice notes or audio clips and analyze whether the audio appears human or AI-generated.
Authenticity Score: Displays a percentage score showing how authentic the audio appears.
Risk Classification: Classifies results as LOW, MEDIUM, HIGH, or ERROR risk based on model prediction.
Audio Feature Extraction: Uses signal-processing features such as MFCCs, spectral centroid, zero-crossing rate, and RMS energy.
Machine Learning Classification: Uses a trained Random Forest model to classify audio as real or synthetic.
Secure Temporary Upload Handling: Uploaded files are saved temporarily for analysis and deleted immediately after processing.
Clean Web Interface: React frontend provides file upload, loading state, progress feedback, and result display.
Model-Based Analysis: Loads a pre-trained audio_model.pkl file for local inference without requiring retraining.
Tech Stack
Frontend: React.js, JavaScript, CSS
Backend: Python, FastAPI, Uvicorn
Machine Learning: scikit-learn, RandomForestClassifier
Audio Processing: librosa, NumPy
Model Storage: joblib
API Communication: Fetch API, multipart file upload
Development Tools: Node.js, npm, Python virtual environment

Screenshot:
 
