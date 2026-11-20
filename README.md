# 🖼️ Image Captioning Using Machine Learning

An end-to-end AI-powered web application built with **Streamlit** that generates
detailed captions and analysis for uploaded images, converts captions to speech,
and lets each registered user keep a personal history of everything they've captioned.

**[🚀 Try the Live Demo](https://YOUR-APP-NAME.streamlit.app)** &nbsp;|&nbsp;
**[🐛 Report a Bug](https://github.com/sahilBr28/Image-Captioning-Using-Machine-Learning/issues)** &nbsp;|&nbsp;
**[✨ Request a Feature](https://github.com/sahilBr28/Image-Captioning-Using-Machine-Learning/issues)**

---

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [Deployment](#-deployment)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

---

## 📌 About the Project

Image captioning is the task of automatically generating a natural-language
description of an image. This project turns that idea into a **complete, usable
web app** — not just a model demo.

A user creates an account, logs in, uploads any image, and instantly receives:

- A detailed AI-generated **caption** describing the image
- A deeper **analysis** of that caption
- An **audio version** of the caption via text-to-speech
- A saved entry in their **personal history**

Everything is stored per-user in a cloud database, so the experience is
persistent across sessions and devices.

The goal of this project is to demonstrate a full machine-learning workflow —
from model inference through to a secure, multi-user, production-deployed web
application.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔐 **User Authentication** | Register and log in with a custom username and password |
| 🖼️ **Image Upload** | Supports `.png`, `.jpg`, and `.jpeg` formats |
| 🤖 **AI-Generated Captions** | Produces a detailed, natural-language description of any uploaded image |
| 🔍 **Caption Analysis** | Provides a deeper breakdown of the generated caption |
| 🔊 **Text-to-Speech** | Converts the caption into playable audio directly in the browser |
| 📚 **Per-User History** | Every caption and analysis is saved and displayed on each login |
| ☁️ **Cloud Database** | Persistent storage so user data survives app restarts and redeploys |
| 🌐 **Always Live** | Publicly accessible 24/7 via Streamlit Community Cloud |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend / App Framework** | [Streamlit](https://streamlit.io/) |
| **Image Handling** | [Pillow (PIL)](https://python-pillow.org/) |
| **Image Captioning Model** | <!-- e.g. BLIP, ViT-GPT2, Gemini Vision, GPT-4V --> |
| **Caption Analysis** | <!-- describe how analysis is produced --> |
| **Text-to-Speech** | <!-- e.g. gTTS, pyttsx3, Google TTS --> |
| **Database** | <!-- e.g. Turso (cloud SQLite), Supabase --> |
| **Deployment** | [Streamlit Community Cloud](https://share.streamlit.io/) |
| **Language** | Python 3.9+ |

---

## 📁 Project Structure

```
Image-Captioning-Using-Machine-Learning/
│
├── app.py                  # Main Streamlit application (UI + routing)
├── database.py             # All database operations (users & captions)
├── image_captioning.py     # Caption generation and analysis logic
├── text_to_speech.py       # Text-to-speech conversion
├── utils.py                # Helper functions (e.g. saving uploaded images)
│
├── requirements.txt        # Python dependencies
├── .gitignore              # Excludes secrets, DB files, and caches
└── README.md               # You are here
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.9 or newer
- `pip`
- Git

### 1. Clone the repository

```bash
git clone https://github.com/sahilBr28/Image-Captioning-Using-Machine-Learning.git
cd Image-Captioning-Using-Machine-Learning
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv

# macOS / Linux
source venv/bin/activate

# Windows
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure secrets

Create a `.streamlit/secrets.toml` file in the project root and add your database
credentials (see [Configuration](#-configuration) below).

### 5. Run the app

```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`.

---

## ⚙️ Configuration

This app uses Streamlit's secrets system to keep credentials out of source
control. Create `.streamlit/secrets.toml` locally (and add it to Streamlit Cloud
via the app dashboard — **never** commit it to GitHub).

Example for a Turso cloud SQLite database:

```toml
[turso]
url = "libsql://your-database-name.turso.io"
auth_token = "your-turso-auth-token"
```

> **Note:** `.streamlit/secrets.toml` is listed in `.gitignore` and must never
> be pushed to the repository.

---

## 🧑‍💻 Usage

1. **Register** a new account from the sidebar.
2. **Log in** with your credentials.
3. **Upload an image** (PNG, JPG, or JPEG).
4. The app will:
   - Display the uploaded image
   - Generate a **caption**
   - Show a detailed **analysis** of the caption
   - Provide an **audio playback** of the caption
   - Save the entry to your **history**
5. Scroll down to view **all your previous captions and analyses**.
6. Click **Logout** when finished.

---

## ☁️ Deployment

This app is deployed on **Streamlit Community Cloud**, which builds directly
from this GitHub repository and provides a permanent public URL.

To deploy your own copy:

1. Fork this repository.
2. Go to [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub.
3. Click **New app**, select your fork, branch `main`, and main file `app.py`.
4. In **Advanced settings → Secrets**, paste your database credentials in TOML format.
5. Click **Deploy**.

> **Important:** Streamlit Cloud does not persist local files. This is why the
> database is hosted on a cloud service rather than a local `SQLite` `.db` file.

---

## 🗺️ Roadmap

- [ ] Multiple caption styles (short / detailed / creative)
- [ ] Support for multiple languages in captions and TTS
- [ ] Password reset via email
- [ ] Caption export (PDF / CSV)
- [ ] Image batch upload

Contributions and suggestions are welcome — open an issue!

---

## 🤝 Contributing

Contributions make the open-source community an amazing place to learn and
grow. Any contributions you make are **greatly appreciated**.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

## 👤 Author

**Sahil** — [@sahilBr28](https://github.com/sahilBr28)

Project Link: [https://github.com/sahilBr28/Image-Captioning-Using-Machine-Learning](https://github.com/sahilBr28/Image-Captioning-Using-Machine-Learning)

---

<p align="center">
  ⭐ If you found this project useful, please consider giving it a star!
</p>