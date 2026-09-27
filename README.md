# 🚀 SkyWatch YOLO

SkyWatch YOLO is a Django-based web application designed as a foundation for an AI-powered flying-object detection platform. The project currently provides a responsive web interface, user registration, secure password hashing, login/logout, session-based authentication, and a personalized dashboard.

> **Project status:** The current uploaded version contains the Django web application and authentication layer. YOLO model files, image/video inference code, and an active detection endpoint are **not included yet**. The dashboard presents the detection feature as a planned/integration-ready component.

## ✨ Features

- 🏠 Modern landing page for the SkyWatch YOLO platform
- 👤 User registration with:
  - Username
  - Password
  - Mobile number
  - Place
- 🔐 Password hashing using Django's password-hashing utilities
- 🔑 Login and logout functionality
- 🛡️ Session-based access control for the dashboard
- 📊 Personalized user dashboard
- 📱 Responsive HTML/CSS interface
- 💾 SQLite database
- ⚙️ Django migration support
- 🤖 Designed for future YOLO-based object-detection integration

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Backend programming |
| Django | Web framework |
| SQLite | Database |
| HTML5 | Web structure |
| CSS3 | Styling and responsive UI |
| Django Sessions | Login/session management |
| Django Password Hashing | Password protection |
| YOLO | Planned object-detection integration |

## 📁 Project Structure

```text
skywatch yolo/
│
├── manage.py
├── db.sqlite3
│
├── skywatch yolo/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
└── users/
    ├── admin.py
    ├── apps.py
    ├── models.py
    ├── urls.py
    ├── views.py
    ├── tests.py
    │
    ├── migrations/
    │   └── 0001_initial.py
    │
    └── templates/
        └── users/
            ├── home.html
            ├── register.html
            ├── login.html
            └── dashboard.html
```

## 🔄 Application Workflow

```text
User
  │
  ├── Home Page
  │
  ├── Register
  │     └── User details stored in SQLite
  │
  ├── Login
  │     └── Password verification
  │
  ├── Dashboard
  │     └── Authenticated user information
  │
  └── Logout
        └── Session cleared
```

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/skywatch-yolo.git
cd skywatch-yolo
```

### 2. Create a virtual environment

Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

macOS/Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Django

The uploaded project was generated with Django 6.1.1.

```bash
pip install Django==6.1.1
```

### 4. Apply migrations

```bash
python manage.py migrate
```

### 5. Start the development server

```bash
python manage.py runserver
```

Open:

```text
http://127.0.0.1:8000/
```

## 🌐 Available Pages

| URL | Description |
|---|---|
| `/` | SkyWatch YOLO landing page |
| `/register/` | Create a new user account |
| `/login/` | User login |
| `/dashboard/` | Authenticated user dashboard |
| `/logout/` | End the current session |
| `/admin/` | Django administration interface |

## 🧠 Current Data Model

The application currently uses a custom `User` model with the following fields:

```text
User
├── user_name
├── password
├── mobile_number
└── place
```

Passwords are stored using Django's `make_password()` function and checked using `check_password()`.

## 🤖 Planned YOLO Integration

The project is structured so that a YOLO-based computer-vision module can be added to the existing dashboard.

A future implementation can include:

1. Upload an image or video.
2. Load a trained YOLO model.
3. Run object detection.
4. Draw bounding boxes around detected objects.
5. Display object labels and confidence scores.
6. Return the processed image/video to the dashboard.
7. Store detection history if required.

A possible future architecture is:

```text
Image / Video
      │
      ▼
Django Upload Interface
      │
      ▼
YOLO Detection Model
      │
      ├── Object Class
      ├── Bounding Box
      └── Confidence Score
      │
      ▼
Detection Result
      │
      ▼
SkyWatch Dashboard
```

## 🔒 Security Notes

Before deploying this project publicly:

- Set `DEBUG = False`.
- Replace the development `SECRET_KEY` with an environment variable.
- Configure `ALLOWED_HOSTS`.
- Do not commit private secrets to GitHub.
- Consider using Django's built-in authentication framework for production-grade user management.
- Validate and sanitize user input.
- Use HTTPS in production.
- Do not commit `db.sqlite3` if it contains real user information.
- Add automated tests for authentication and access control.

## 📌 Limitations of the Current Version

The uploaded version currently focuses on the Django web application and authentication workflow.

The following are **not yet implemented in the uploaded code**:

- YOLO model weights
- YOLO inference pipeline
- Image/video upload for detection
- Bounding-box prediction results
- Detection history
- Live camera detection
- Confidence-score visualization

These can be added as the next development phase.

## 🔮 Future Enhancements

- Integrate YOLOv8/YOLO11 or another suitable YOLO model
- Support image and video detection
- Add webcam/live-stream detection
- Display confidence scores and class labels
- Save detection history
- Add user-specific detection reports
- Add REST API endpoints
- Add model selection and configuration
- Add charts and analytics to the dashboard
- Deploy using Gunicorn/Uvicorn and a production database
- Add automated unit and integration tests

## 📜 License

This project can be released under the MIT License. Add a `LICENSE` file to the repository if you choose to distribute the project under MIT.

## 👩‍💻 Author

**Ananya Sharma**

Computer Science and Engineering  
Interested in Artificial Intelligence, Machine Learning, Deep Learning, NLP, and Computer Vision.
