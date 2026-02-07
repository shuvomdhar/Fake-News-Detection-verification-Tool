# 🛡️ TruthGuard

**Advanced AI-powered platform to detect fake news and misinformation**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.0%2B-green.svg)](https://flask.palletsprojects.com/)
[![Gemini AI](https://img.shields.io/badge/Gemini-2.5%20Flash-red.svg)](https://ai.google.dev/)

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [API Endpoints](#-api-endpoints)
- [Screenshots](#-screenshots)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)

---

## 🌟 Overview

TruthGuard is an intelligent fake news detection system developed as part of the **Infosys Springboard 6.0 Internship**. This web-based platform leverages cutting-edge AI and machine learning techniques to help users verify the authenticity of news articles and online content in real-time.

With the rise of misinformation on social media and news platforms, TruthGuard provides a reliable solution to analyze text content, detect suspicious patterns, and classify news as **Reliable**, **Suspicious**, or **Fake** with confidence scores.

---

## ✨ Features

### Core Functionality
- ⚡ **Ultra-Fast Analysis**: Get results in under 100ms with optimized processing
- 🔍 **Multi-Input Support**: Analyze text content or URLs directly
- 🎯 **AI-Powered Detection**: Integration with Google Gemini 2.5 Flash for enhanced accuracy
- 📊 **Comprehensive Scoring**: Confidence, credibility, and sensationalism metrics
- 💾 **Analysis History**: Track all your previous analyses with detailed reports

### User Experience
- 🤖 **AI Chatbot Assistant**: Interactive help using Gemini AI
- 📈 **Visual Dashboard**: Real-time statistics and analysis trends
- 👤 **User Accounts**: Secure authentication and personalized experience
- 🎨 **Modern UI**: Clean, responsive interface with gradient designs

### Advanced Features
- 🔄 **Smart Caching**: Improved performance with intelligent result caching
- 📝 **Key Findings**: Detailed breakdown of misinformation indicators
- 🌐 **URL Content Extraction**: Automatic web scraping for link analysis
- 👨‍💼 **Admin Dashboard**: User management and system analytics

---

## 🛠️ Tech Stack

### Backend
- **Python 3.8+**: Core programming language
- **Flask**: Web framework for routing and API handling
- **SQLAlchemy**: ORM for database management
- **Flask-Login**: User authentication and session management

### AI & Machine Learning
- **Google Gemini API**: Advanced AI for content analysis
- **NLTK**: Natural Language Processing toolkit
- **Sentiment Analysis**: Emotional tone detection
- **Pattern Recognition**: Custom ML algorithms for fake news detection

### Frontend
- **HTML5/CSS3**: Structure and styling
- **JavaScript**: Dynamic interactions
- **Bootstrap/Custom CSS**: Responsive design

### Database
- **SQLite**: Lightweight embedded database

### Additional Libraries
- **BeautifulSoup4**: Web scraping
- **Requests**: HTTP library for URL fetching
- **Pandas & NumPy**: Data manipulation
- **Werkzeug**: Security utilities

---

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- Git

### Step 1: Clone the Repository
```bash
git clone https://github.com/shuvomdhar/Fake-News-Detection-verification-Tool
cd Fake-News-Detection-verification-Tool
```

### Step 2: Create Virtual Environment
```bash
# Windows
python -m venv .venv
.venv\Scripts\activate

# Linux/macOS
python3 -m venv .venv
source .venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Download NLTK Data
```python
python -c "import nltk; nltk.download('punkt'); nltk.download('stopwords'); nltk.download('wordnet'); nltk.download('vader_lexicon')"
```

---

## ⚙️ Configuration

### 1. Create Environment File
Create a `.env` file in the root directory:

```env
# Flask Configuration
SECRET_KEY=your-super-secret-key-change-in-production
FLASK_ENV=development

# Gemini AI Configuration
GEMINI_API_KEY=your-gemini-api-key-here
GEMINI_MODEL=gemini-2.5-flash

# Database (Optional - defaults to SQLite)
SQLALCHEMY_DATABASE_URI=sqlite:///instance/truthguard.db
```

### 2. Get Gemini API Key
1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Create a new API key
3. Copy and paste it into your `.env` file

### 3. Initialize Database
The database will be automatically created on first run, or you can initialize it manually:

```bash
python -c "from app import init_database; init_database()"
```

---

## 🚀 Usage

### Starting the Application

```bash
python app.py
```

The application will be available at: `http://localhost:5000`

### Default Admin Credentials
- **Email**: `admin@truthguard.com`
- **Password**: `Admin123!`

⚠️ **Important**: Change the admin password immediately after first login!

### Using TruthGuard

1. **Register/Login**: Create an account or log in
2. **Analyze Content**: 
   - Paste text directly into the analyzer
   - Or provide a URL to analyze
3. **View Results**: Get instant classification with detailed metrics
4. **Check History**: Access all your previous analyses
5. **Use Chatbot**: Ask the AI assistant about misinformation detection

---

## 📁 Project Structure

```
FAKE_NEWS_DETECTION_AND_VERIFICATION_TOOL/
│
├── .venv/                      # Virtual environment (auto-generated)
│
├── instance/
│   └── truthguard.db          # SQLite database (auto-generated)
│
├── logs/
│   └── truthguard.log         # Application logs (auto-generated)
│
├── static/
│   └── uploads/               # User uploaded files
│
├── templates/
│   ├── about.html             # About page
│   ├── analysis_History.html  # Analysis history page
│   ├── analyze.html           # Analysis page
│   ├── base.html              # Base template
│   ├── contact.html           # Contact page
│   ├── dashboard.html         # User dashboard
│   ├── index.html             # Landing page
│   ├── login.html             # Login page
│   ├── profile.html           # User profile
│   └── register.html          # Registration page
│
├── .env                        # Environment variables (create this)
├── .gitignore                 # Git ignore file
├── app.py                      # Main application file
└── README.md                   # Project documentation
```

---

## 🔌 API Endpoints

### Authentication
- `POST /register` - Register new user
- `POST /login` - User login
- `GET /logout` - User logout

### Analysis
- `POST /analyze` - Analyze text/URL content
- `GET /analysis/<id>` - Get specific analysis details
- `GET /history` - View analysis history

### Gemini AI Chat
- `POST /api/gemini/chat` - Chat with AI assistant
- `POST /chat` - Alternative chat endpoint
- `POST /api/chat/simple` - Simple chat without authentication

### Admin
- `GET /admin` - Admin dashboard
- `GET /admin/users` - User management
- `GET /admin/analyses` - View all analyses
- `POST /admin/user/<id>/toggle` - Toggle user status
- `POST /admin/user/<id>/make_admin` - Make user admin

### Utilities
- `GET /api/health` - Health check endpoint
- `GET /api/gemini/status` - Check Gemini AI status

---

## 📸 Screenshots

### Home Page
![TruthGuard Home](screenshots/home.png)
*Modern landing page with gradient design and shield logo*

### Dashboard
![Dashboard](screenshots/dashboard.png)
*Comprehensive analytics with charts and recent analyses*

### Analysis Page
![Analysis](screenshots/analysis.png)
*Real-time content analysis with detailed metrics*

---

## 📄 Documentation

Watch the documentation of the project below:
- PDF Link: [Fake-News-Detection-Verification-Tool.pdf](https://github.com/shuvomdhar/Fake-News-Detection-verification-Tool/blob/main/Fake-News-Detection-Verification-Tool.pdf)
- PPT Link: [Fake-News-Detection-Verification-Tool.pptx](https://www.canva.com/design/DAHAXjCacGo/BtRSzjdAtiRyjTPWdgXpyA/edit?utm_content=DAHAXjCacGo&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create your feature branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit your changes** (`git commit -m 'Add some AmazingFeature'`)
4. **Push to the branch** (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

### Development Guidelines
- Follow PEP 8 style guide for Python code
- Write clear commit messages
- Add tests for new features
- Update documentation as needed

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/shuvomdhar/Fake-News-Detection-verification-Tool?tab=MIT-1-ov-file) file for details.


---

## 🙏 Acknowledgments

- **Infosys Springboard 6.0** - For providing the internship opportunity
- **Google AI** - For the Gemini API integration
- **NLTK Community** - For NLP tools and resources
- **Flask Community** - For the excellent web framework
- **Open Source Contributors** - For various libraries used in this project

---

## 📞 Contact

**Project Maintainer**: [Shuvom Dhar]
- Email: shuvomdhar8@gmail.com
- GitHub: [@shuvomdhar](https://github.com/shuvomdhar)
- LinkedIn: [shuvom-dhar](https://www.linkedin.com/in/shuvom-dhar/)

**Project Link**: [Fake-News-Detection-verification-Tool](https://github.com/shuvomdhar/Fake-News-Detection-verification-Tool)

---

## 🎓 About Infosys Springboard 6.0

This project was developed as part of the Infosys Springboard 6.0 internship program, focusing on AI/ML applications for social good. The program provides hands-on experience in developing real-world solutions using cutting-edge technologies.

---

<div align="center">

**Made with ❤️ for a world with less misinformation**

⭐ Star this repository if you found it helpful!

</div>