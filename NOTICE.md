# Notices and Third-Party Licenses

Local STT for Windows includes or can use third-party open source software and machine learning models.

This project is not affiliated with or endorsed by the third-party projects listed below.

## Core Components

### faster-whisper

- Project: https://github.com/SYSTRAN/faster-whisper
- License: MIT
- Used for offline speech recognition through CTranslate2.

### CTranslate2

- Project: https://github.com/OpenNMT/CTranslate2
- License: MIT
- Used as the inference runtime for faster-whisper models.

### whisper.cpp

- Project: https://github.com/ggml-org/whisper.cpp
- License: MIT
- Used for CPU-friendly Whisper inference.

### OpenAI Whisper

- Project: https://github.com/openai/whisper
- License: MIT
- Whisper model weights and code are used through compatible runtimes.

### Systran faster-whisper models

- Project: https://huggingface.co/Systran
- License: MIT
- Converted Whisper models for CTranslate2/faster-whisper.

## Speaker Diarization

### SpeechBrain

- Project: https://github.com/speechbrain/speechbrain
- License: Apache-2.0

### speechbrain/spkrec-ecapa-voxceleb

- Model: https://huggingface.co/speechbrain/spkrec-ecapa-voxceleb
- License: Apache-2.0
- Used for speaker embedding and speaker separation features.

## Python Runtime and Libraries

The Windows installer may include Python runtime and Python packages such as:

- FastAPI
- Uvicorn
- Jinja2
- PyTorch
- torchaudio
- transformers
- NumPy
- SciPy
- ONNX Runtime
- safetensors

Each package is distributed under its own license. License files are included in the installed Python package metadata where available.

## Model Notice

This release may include or support additional model files. Users are responsible for confirming that model files are appropriate for their organization and use case.

## Disclaimer

All third-party copyrights remain with their respective owners.

This software is provided without warranty. Speech recognition results may contain errors and should be reviewed before official use.

