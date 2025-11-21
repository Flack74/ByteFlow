# 🐦 ByteFlow

[![Django](https://img.shields.io/badge/Django-5.2.8-092E20?style=for-the-badge&logo=django&logoColor=white)](https://djangoproject.com/)
[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org/)
[![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

> 🚀 A modern Django-based social media application where users can create, edit, and delete tweets with optional photo attachments.

## ✨ Features

- 🔐 **User Authentication** - Registration, login, logout
- 📝 **Tweet Management** - Create, edit, delete tweets
- 📸 **Photo Upload** - Optional image attachments
- 📅 **Chronological Feed** - View all tweets in order
- 👤 **User-Specific Management** - Manage your own content
- 📱 **Responsive Design** - Works on all devices

## 🛠️ Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| **Django** | 5.2.8 | Backend Framework |
| **Python** | 3.x | Programming Language |
| **SQLite** | Default | Database (Development) |
| **Pillow** | 12.0.0 | Image Processing |
| **HTML/CSS** | - | Frontend |

## 📁 Project Structure

```
ByteFlow/
├── 📂 SocialFeedApp/
│   ├── 📂 SocialFeedApp/          # 🔧 Project settings
│   │   ├── settings.py
│   │   ├── urls.py
│   │   ├── wsgi.py
│   │   └── asgi.py
│   ├── 📂 tweet/                  # 🐦 Main app
│   │   ├── models.py              # 📊 Tweet model
│   │   ├── views.py               # 🎯 View logic
│   │   ├── forms.py               # 📋 Form definitions
│   │   ├── urls.py                # 🔗 App URLs
│   │   ├── migrations/            # 🗄️ Database migrations
│   │   └── templates/             # 🎨 App templates
│   ├── 📂 templates/              # 🎨 Project templates
│   │   ├── registration/          # 🔐 Auth templates
│   │   ├── layout.html
│   │   └── index.html
│   ├── 📂 static/                 # 🎨 CSS, JS, images
│   ├── 📂 media/                  # 📸 User uploads
│   ├── manage.py
│   └── db.sqlite3
├── requirements.txt
├── .gitignore
├── README.md
└── IMPROVEMENTS.md
```

## 🚀 Quick Start

### 1️⃣ Clone Repository
```bash
git clone <repository-url>
cd ByteFlow
```

### 2️⃣ Setup Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # 🐧 Linux/Mac
# venv\Scripts\activate   # 🪟 Windows
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 4️⃣ Navigate to Project
```bash
cd SocialFeedApp
```

### 5️⃣ Database Setup
```bash
python manage.py migrate
python manage.py createsuperuser
```

### 6️⃣ Run Development Server
```bash
python manage.py runserver
```

### 7️⃣ Access Application
- 🏠 **Main App**: http://localhost:8000
- ⚙️ **Admin Panel**: http://localhost:8000/admin

## 📖 Usage Guide

### 🐦 Creating a Tweet
1. 🔑 Log in to your account
2. ➕ Click "Create Tweet"
3. ✍️ Enter tweet text (max 180 characters)
4. 📸 Optionally upload a photo
5. 📤 Click "Post"

### ✏️ Editing a Tweet
1. 🔍 Navigate to your tweet
2. ✏️ Click "Edit"
3. 📝 Modify the content
4. 💾 Click "Save"

### 🗑️ Deleting a Tweet
1. 🔍 Navigate to your tweet
2. 🗑️ Click "Delete"
3. ✅ Confirm deletion

## 🛣️ API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/` | 🏠 Home page |
| `GET` | `/tweet/` | 📋 View all tweets |
| `GET/POST` | `/tweet/create/` | ➕ Create tweet |
| `GET/POST` | `/tweet/<id>/edit/` | ✏️ Edit tweet |
| `GET/POST` | `/tweet/<id>/delete/` | 🗑️ Delete tweet |
| `GET/POST` | `/accounts/register/` | 📝 User registration |
| `GET/POST` | `/accounts/login/` | 🔑 User login |
| `GET` | `/accounts/logout/` | 🚪 User logout |

## 🗄️ Database Schema

### Tweet Model
```python
class Tweet(models.Model):
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    text = models.TextField(max_length=180)
    photo = models.ImageField(upload_to='photos/', blank=True, null=True)
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)
```

## ⚙️ Configuration

Key settings in `settings.py`:
- `DEBUG = True` - 🔧 Development mode
- `ALLOWED_HOSTS = []` - 🌐 Add domains for production
- `DATABASES` - 🗄️ SQLite for development
- `MEDIA_URL` - 📸 User upload URL
- `LOGIN_REDIRECT_URL` - 🔄 Post-login redirect
- `LOGOUT_REDIRECT_URL` - 🔄 Post-logout redirect

## 🧪 Development

### Running Tests
```bash
python manage.py test
```

### Creating Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### Accessing Admin Panel
1. 🌐 Go to http://localhost:8000/admin
2. 🔑 Log in with superuser credentials
3. ⚙️ Manage tweets and users

## 🚀 Production Deployment

### Pre-deployment Checklist
- [ ] Set `DEBUG = False`
- [ ] Update `ALLOWED_HOSTS`
- [ ] Use environment variables for `SECRET_KEY`
- [ ] Switch to PostgreSQL/MySQL
- [ ] Configure static files serving
- [ ] Set up HTTPS
- [ ] Use production WSGI server (Gunicorn/uWSGI)

## 🤝 Contributing

1. 🍴 Fork the repository
2. 🌿 Create a feature branch (`git checkout -b feature/amazing-feature`)
3. 💾 Commit your changes (`git commit -m 'Add amazing feature'`)
4. 📤 Push to the branch (`git push origin feature/amazing-feature`)
5. 🔄 Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- 🐛 **Issues**: [GitHub Issues](https://github.com/Flack74/ByteFlow/issues)
- 📧 **Email**: puspendrachawlax@example.com
- 💬 **Discussions**: [GitHub Discussions](https://github.com/Flack74/ByteFlow/discussions)

## 🙏 Acknowledgments

- Django community for the amazing framework
- Contributors and testers
- Open source community

---

<div align="center">
  <p>Made with ❤️ by <a href="https://github.com/Flack74">Flack74</a></p>
  <p>⭐ Star this repo if you found it helpful!</p>
</div>
