
# 🎓 ระบบลงทะเบียนนักศึกษา (Student Registration System)

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📋 สารบัญ
- [📌 ภาพรวมโครงการ](#-ภาพรวมโครงการ)
- [✨ คุณสมบัติหลัก](#-คุณสมบัติหลัก)
- [🛠 เทคโนโลยีที่ใช้](#-เทคโนโลยีที่ใช้)
- [📦 ความต้องการของระบบ](#-ความต้องการของระบบ)
- [🚀 การติดตั้ง](#-การติดตั้ง)
- [📁 โครงสร้างโปรเจกต์](#-โครงสร้างโปรเจกต์)
- [📑 คำอธิบายโค้ด](#-คำอธิบายโค้ด)
- [📖 การใช้งาน](#-การใช้งาน)
- [⚙️ การกำหนดค่า](#-การกำหนดค่า)
- [🧩 การปรับแต่งและขยาย](#-การปรับแต่งและขยาย)
- [🚧 การดูแลรักษาและการสนับสนุน](#-การดูแลรักษาและการสนับสนุน)
- [🤝 การมีส่วนร่วมในโครงการ](#-การมีส่วนร่วมในโครงการ)
- [📄 ใบอนุญาต](#-ใบอนุญาต)
- [📞 ติดต่อ](#-ติดต่อ)

## 📌 ภาพรวมโครงการ
ระบบลงทะเบียนนักศึกษา เป็นเว็บแอปพลิเคชันที่พัฒนาโดยใช้ Django Framework สำหรับจัดการข้อมูลนักศึกษา เช่น การเพิ่ม แก้ไข ลบ และแสดงรายชื่อนักศึกษา พร้อมรองรับการอัปโหลดรูปภาพผู้ใช้

## ✨ คุณสมบัติหลัก
- ลงทะเบียนนักศึกษา พร้อมข้อมูลส่วนตัวและรูปภาพ
- ระบบค้นหาและแก้ไขข้อมูลนักศึกษา
- ลบข้อมูลนักศึกษา
- แสดงรายชื่อทั้งหมดในรูปแบบตาราง
- จัดการผ่าน Web Interface ที่สวยงามด้วย Bootstrap

## 🛠 เทคโนโลยีที่ใช้
- Python 3.x
- Django 4.x
- SQLite3
- HTML5/CSS3
- Bootstrap 5

## 📦 ความต้องการของระบบ
- Python >= 3.10
- Django >= 4.2
- pip (Python package manager)

## 🚀 การติดตั้ง
```bash
git clone https://github.com/yourusername/student_register.git
cd student_register
python -m venv venv
source venv/bin/activate   # หรือใช้ venv\Scripts\activate สำหรับ Windows
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

## 📁 โครงสร้างโปรเจกต์
```plaintext
student_register/
├── db.sqlite3
├── manage.py
├── student_register/
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── students/
│   ├── models.py
│   ├── forms.py
│   ├── views.py
│   ├── urls.py
│   └── migrations/
└── templates/
    ├── base.html
    ├── student_form.html
    └── student_list.html
```

## 📑 คำอธิบายโค้ด
- `models.py` → สร้างโครงสร้างข้อมูลนักศึกษา
- `forms.py` → แบบฟอร์มรับข้อมูล
- `views.py` → ฟังก์ชันจัดการหน้าเพิ่ม/ลบ/แก้ไข
- `urls.py` → เส้นทางเชื่อมโยง URL กับ View
- `templates/` → หน้าเว็บ HTML

## 📖 การใช้งาน
1. เข้าผ่านเบราว์เซอร์ที่ `http://127.0.0.1:8000/`
2. เพิ่มนักศึกษาที่ `/add/`
3. แก้ไขที่ `/edit/<id>/`, ลบที่ `/delete/<id>/`
4. ค้นหาชื่อนักศึกษาได้จากหน้าแรก

## ⚙️ การกำหนดค่า
```python
# settings.py
MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'

# urls.py
from django.conf import settings
from django.conf.urls.static import static
urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

## 🧩 การปรับแต่งและขยาย
- เพิ่มระบบล็อกอิน/ยืนยันตัวตน
- ส่งอีเมลยืนยัน
- รองรับ import/export Excel
- ใช้ฐานข้อมูล PostgreSQL

## 🚧 การดูแลรักษาและการสนับสนุน
เปิด Issue ใน GitHub หากพบปัญหา

## 🤝 การมีส่วนร่วมในโครงการ
Pull Request และ Fork ได้เต็มที่ครับ!

## 📄 ใบอนุญาต
เผยแพร่ภายใต้ MIT License – ใช้เพื่อการศึกษาและพัฒนาต่อได้

## 📞 ติดต่อ
ชื่อผู้พัฒนา: วงศกร หวลมานพ  
GitHub: [https://github.com/wonsagorn](https://github.com/wonsagorn)
