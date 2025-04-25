
# 🎓 ระบบลงทะเบียนนักศึกษา (Student Registration System)

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📋 สารบัญ
- [📌 ภาพรวมโครงการ](#-ภาพรวมโครงการ)
- [✨ คุณสมบัติหลัก](#-คุณสมบัติหลัก)
- [🛠 เทคโนโลยีที่ใช้](#-เทคโนโลยีที่ใช้)
- [📦 ความต้องการของระบบ](#-ความต้องการของระบบ)
- [🚀 การติดตั้งและรันโปรเจกต์](#-การติดตั้งและรันโปรเจกต์)
- [📁 โครงสร้างโปรเจกต์](#-โครงสร้างโปรเจกต์)
- [📑 คำอธิบายโค้ดแต่ละไฟล์](#-คำอธิบายโค้ดแต่ละไฟล์)
- [📖 การใช้งานระบบ](#-การใช้งานระบบ)
- [⚙️ การกำหนดค่า Media](#-การกำหนดค่า-media)
- [🧩 การปรับแต่งและขยาย](#-การปรับแต่งและขยาย)
- [🚧 การดูแลรักษาและการสนับสนุน](#-การดูแลรักษาและการสนับสนุน)
- [🤝 การมีส่วนร่วมในโครงการ](#-การมีส่วนร่วมในโครงการ)
- [📄 ใบอนุญาต](#-ใบอนุญาต)
- [📞 ติดต่อ](#-ติดต่อ)

---

## 📌 ภาพรวมโครงการ
ระบบลงทะเบียนนักศึกษา พัฒนาด้วย Django Framework ช่วยให้สามารถจัดการข้อมูลนักศึกษา เช่น การเพิ่ม ลบ แก้ไข และแสดงรายชื่อ พร้อมรองรับการอัปโหลดรูปภาพ

---

## ✨ คุณสมบัติหลัก
- เพิ่ม ลบ แก้ไข ข้อมูลนักศึกษา
- อัปโหลดและแสดงรูปภาพ
- ค้นหานักศึกษาจากชื่อ
- ใช้ Bootstrap 5 ในการออกแบบ UI

---

## 🛠 เทคโนโลยีที่ใช้
- Python 3.x
- Django 4.x
- SQLite
- Bootstrap 5

---

## 📦 ความต้องการของระบบ
- Python >= 3.10
- pip
- Git (optional)
- ระบบปฏิบัติการ Windows / macOS / Linux

---

## 🚀 การติดตั้งและรันโปรเจกต์

### 1. สร้าง virtual environment
```bash
python -m venv venv
source venv/bin/activate         # macOS / Linux
venv\Scripts\activate          # Windows
```

### 2. ติดตั้ง Django
```bash
pip install django
```

### 3. รัน migration และเซิร์ฟเวอร์
```bash
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

---

## 📁 โครงสร้างโปรเจกต์
```plaintext
student_register/
├── manage.py
├── db.sqlite3
├── student_register/         # ไฟล์ settings และ config
│   ├── settings.py
│   ├── urls.py
├── students/                 # แอปหลักของระบบ
│   ├── models.py
│   ├── views.py
│   ├── forms.py
│   ├── urls.py
│   └── migrations/
└── templates/                # เทมเพลต HTML
    ├── base.html
    ├── student_form.html
    └── student_list.html
```

---

## 📑 คำอธิบายโค้ดแต่ละไฟล์

### `models.py`
```python
class Student(models.Model):
    name = models.CharField(max_length=100)
    email = models.EmailField()
    image = models.ImageField(upload_to='student_images/')
```
> กำหนดโครงสร้างข้อมูลนักศึกษา เช่น ชื่อ อีเมล และรูป

---

### `forms.py`
```python
class StudentForm(forms.ModelForm):
    class Meta:
        model = Student
        fields = ['name', 'email', 'image']
```
> ฟอร์มใช้รับค่าจากผู้ใช้ โดยอิงจาก model Student

---

### `views.py`
```python
def student_list(request):
    ...
def student_create(request):
    ...
```
> ประมวลผลการแสดงหน้าเว็บ เช่น แสดงรายชื่อ, เพิ่ม, ลบ, แก้ไข

---

### `urls.py`
```python
urlpatterns = [
    path('', views.student_list),
    path('add/', views.student_create),
]
```
> เส้นทางสำหรับเข้าถึงหน้าเว็บต่าง ๆ ในระบบ

---

### `base.html`
> เทมเพลตหลักของเว็บ ใช้ร่วมกับหน้าอื่นเพื่อไม่เขียนซ้ำ

### `student_list.html`
> แสดงรายชื่อนักศึกษาเป็นตาราง พร้อมปุ่มแก้ไข/ลบ

### `student_form.html`
> ฟอร์มสำหรับเพิ่มหรือแก้ไขข้อมูลนักศึกษา

---

## 📖 การใช้งานระบบ
1. ไปที่ `http://127.0.0.1:8000/`
2. เพิ่มนักศึกษาใหม่ผ่านหน้า `/add/`
3. ใช้ปุ่ม "แก้ไข / ลบ" ในตารางจัดการข้อมูล
4. ค้นหาชื่อได้โดยใส่ในช่องค้นหาด้านบน

---

## ⚙️ การกำหนดค่า Media
เพิ่มใน `settings.py`
```python
MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'
```

และใน `urls.py`
```python
from django.conf import settings
from django.conf.urls.static import static
urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

---

## 🧩 การปรับแต่งและขยาย
- เพิ่มระบบล็อกอิน/ยืนยันตัวตน
- ส่งอีเมลแจ้งเตือนเมื่อเพิ่มนักศึกษา
- รองรับ import/export Excel
- ใช้งานฐานข้อมูล PostgreSQL

---

## 🚧 การดูแลรักษาและการสนับสนุน
สามารถเปิด Issue ใน GitHub หากพบข้อผิดพลาด

---

## 🤝 การมีส่วนร่วมในโครงการ
Fork, Clone, และ Pull Request ได้เลยครับ

---

## 📄 ใบอนุญาต
เผยแพร่ภายใต้ MIT License – ใช้ได้อิสระ

---

## 📞 ติดต่อ
ชื่อผู้พัฒนา: วงศกร หวลมานพ  
GitHub: [https://github.com/wonsagorn](https://github.com/wonsagorn)
