<div align="center">

#  Froggy AI — AI Document & Signature Intelligence Frontend

**A premium Flutter Web interface for document OCR, conversational PDF chat, AI image generation, and signature verification.**

[![Flutter](https://img.shields.io/badge/Flutter-Web-02569B?logo=flutter&logoColor=white)](https://flutter.dev/)
[![Dart](https://img.shields.io/badge/Dart-SDK%20%5E3.9.2-0175C2?logo=dart&logoColor=white)](https://dart.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-Auth%20%7C%20Firestore-FFCA28?logo=firebase&logoColor=black)](https://firebase.google.com/)
[![Gemini](https://img.shields.io/badge/Gemini-2.5%20Flash-4285F4?logo=googlegemini&logoColor=white)](https://ai.google.dev/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](#license)

</div>

---

##  Overview

Forrgy AI is the AI-powered document intelligence platform. It brings together OCR, conversational document Q&A, generative image creation, and signature generation/verification into a single, polished Flutter Web experience backed by a FastAPI server.

---

##  Features

###  Secure Authentication
Firebase Authentication integration with interactive Login, Sign Up, and Email Verification screens.

### Document OCR
Image upload interface that runs backend preprocessing and Tesseract OCR to extract editable text from scanned documents.

### Conversational PDF Chat
An interactive chat client built on **Gemini 2.5 Flash** that lets users upload PDF or TXT documents and discuss their content in natural language.

### AI Image Generation
A text-to-image prompt interface powered by **Flux-dev** via the backend server, with instant PNG downloads.

### Stylistic Signature Flow
- **Generation** — Produces 3 signature options using procedural canvas rendering combined with learned GAN textures.
- **Verification** — Uses a Siamese neural network to distinguish genuine signatures from forgeries with high confidence.
- **Metrics & Graphs** — Visualizes model metrics and CNN confidence scores through interactive graphs and bar charts.

---

## Tech Stack

| Category | Technologies |
|-----------|--------------|
| **Core Framework** | [Flutter Web](https://flutter.dev) (SDK `^3.9.2`) |
| **State Management** | Provider |
| **AI Integration** | `google_generative_ai` (Gemini chat), REST/HTTP calls for image & signature processing |
| **Data Visualization** | `fl_chart` for CNN evaluation graphs |
| **UI & Animation** | `google_fonts` (Space Grotesk, Inter), `flutter_staggered_animations` |
| **Authentication & Data** | `firebase_core`, `firebase_auth`, `cloud_firestore` |

---

## Getting Started

### Prerequisites

- [Flutter SDK](https://docs.flutter.dev/get-started/install) installed and configured for web development
- A running instance of the DocuMind FastAPI backend
- A Firebase project with Authentication and Firestore enabled

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/DocuMind.git
cd DocuMind
```

### 2. Install dependencies

```bash
flutter pub get
```

### 3. Configure environment variables

Create a `.env` file in the project root:

```env
API_KEY=your_gemini_api_key_here
```



### 4. Configure the backend API URL

The frontend connects to a FastAPI backend. Set the backend host and port in:

```
lib/config/api_config.dart
```

### 5. Run locally

Launch the app on a local development server (port `8000` avoids conflicts with the backend):

```bash
flutter run -d chrome --web-port 8000
```

---

##  Project Structure

```
lib/
├── config/
│   └── api_config.dart          # Centralized API URLs
├── features/
│   ├── auth/                    # Auth screens (Login, Signup, Landing)
│   ├── dashboard/                # Main navigation panel
│   ├── image_generation/         # Image generation page
│   ├── ocr/                      # Image-to-text OCR page
│   ├── pdf_chat/                 # PDF text extraction and Gemini Chat
│   └── signature_flow/           # Signature generation, metrics & verification
├── models/                       # Data models (e.g., UserModel)
├── services/                     # Firebase Auth integration
├── widgets/                      # Reusable UI widgets (e.g., AnimatedBackground)
├── app.dart                      # Main MaterialApp definition
└── main.dart                     # Application entry point
```

---

