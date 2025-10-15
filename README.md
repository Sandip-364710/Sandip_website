# 🌀 Django Project with Docker Setup

This is a Django-based web application fully containerized using Docker. It includes a working Docker setup, SQLite database, and is easy to deploy on local or production environments.
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## 🧱 Project Structure
 -------------------------------------
# 📁 Project Structure

project-root/
|
├── Dockerfile  
├── docker-compose.yml  
├── requirements.txt  
├── manage.py  
├── db.sqlite3  
|
├── veterinary/  
│   ├── settings.py  
│   ├── urls.py  
│   ├── wsgi.py  
│   └── ...
|
├── media/  
│   ├── about/  
│   ├── gallery/  
│   
|
├── templates/        # HTML Templates  
├── static/           # Static files  
└── README.md


---

## 🐳 Docker Setup

### Dockerfile

```dockerfile
FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /portfolio

COPY requirements.txt /portfolio/
RUN pip install -r requirements.txt

COPY veterinary /portfolio

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
-----------------------------------------------------------
docker-compos.yml/

services:
  web:
    build: .
    ports:
      - "8000:8000"
    volumes:
      - .:/app
    command: python manage.py runserver 0.0.0.0:8000
version: '3.9'
--------------------------------------------------------
requirements.txt/
Django>=4.2
-------------------------------------------------------
🚀 Run with Docker

# Build the image
docker-compose build

# Run the container
docker-compose up

# Visit in browser
http://localhost:8000
-------------------------------------------------------
💻 Run Without Docker (Local Setup)

python -m venv venv
source venv/Scripts/activate   # Windows: venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
-------------------------------------------------------
📂 Static & Media Setup

MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')

STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
--------------------------------------------------------
## 🌐 Live Demo

[Visit the Live Website](https://dr-sachinpatel.onrender.com/)

---

## ✨ Sign Up Page

Create an account on the live site to explore the authenticated sections.

---

## 📸 Screenshots

> Below are previews of key pages from the site.

### Home
![Home](veterinary/portfolio/static/portfolio/image/Home_page.png)

### About
![About](veterinary/portfolio/static/portfolio/image/About_page.png)

### Services
![Services](veterinary/portfolio/static/portfolio/image/Services_page.png)

### Gallery
![Gallery](veterinary/portfolio/static/portfolio/image/Gallery_page.png)

### Contact
![Contact](veterinary/portfolio/static/portfolio/image/Contact_page.png)

### Login
![Login](veterinary/portfolio/static/portfolio/image/login_page.png)

### Sign Up
![Sign Up](veterinary/portfolio/static/portfolio/image/signup_page.png)















