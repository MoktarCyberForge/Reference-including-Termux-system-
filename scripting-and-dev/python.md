
# 🐍 Python في Termux - دليل تطوير وأتمتة متكامل  
  
## 📌 مقدمة  
Python هي لغة برمجة عالية المستوى تُستخدم في عدة مجالاتمثل: تطوير الويب تحليل البيانات، الذكاء الاصطناعي الأتمتة والأمن السيبراني
 
داخل بيئة  Termux على Android يمكن استخدام Python لأداء مهام متقدمة دون الحاجة إلى صلاحيات root  
  
💡 ملاحظة : جميع الأوامر الواردة في هذا الدليل صالحة للاستخدام داخل تطبيق Termux على هواتف Android
  
  
## 🛠️ تثبيت Python في Termux  
### 🔹 تحديث الحزم الأساسية:  

pkg update && pkg upgrade -y

🔹 تثبيت Python:

pkg install python -y

🔹 التحقق من التثبيت:

python --version  
pip --version


📦 إدارة الحزم باستخدام pip

تثبيت مكتبة خارجية:

pip install requests

ترقية pip:

pip install --upgrade pip

عرض المكتبات المثبتة:

pip list


🧪 تنفيذ سكريبتات Python
🔹 كتابة سكريبت بسيط:

# file: hello.py  
print("مرحبًا بك في Python داخل Termux!")

🔹 تشغيل السكريبت:

python hello.py


⚙️ تنفيذ المهام التلقائية باستخدام Python

الوصول إلى نظام الملفات:

import os  
print(os.listdir("/data/data/com.termux/files/home"))

تنفيذ أوامر Linux:

import subprocess  
subprocess.run(["ls", "-la"])

تنفيذ Cron Job باستخدام سكريبت:
دمج Python مع crontab لتشغيل السكريبت بشكل دوري


🔍 مكتبات مفيدة داخل Termux
مكتبةالاستخدامrequestsإرسال واستقبال طلبات HTTPbs4 (BeautifulSoup)استخراج البيانات من HTMLsubprocessتنفيذ أوامر النظامtermcolorطباعة نصوص ملونة في الطرفيةjson / csvالتعامل مع البيانات المهيكلة---

⚠️ نصائح أمنية

لا تشغل سكريبتات Python من مصادر غير موثوقة

تجنّب حفظ كلمات المرور ومفاتيح API داخل السكريبتات

استخدم البيئة الافتراضية venv لعزل المشاريع:




python -m venv myenv  
source myenv/bin/activate


🔗 مصادر موثوقة

التوثيق الرسمي لـ Python

PyPI - مكتبة حزم Python

دليل Termux Wiki


✨ المساهمة
هل لديك سكريبتات أو أدوات Python مفيدة داخل Termux؟ يمكنك مشاركتها من خلال Pull Request لإثراء هذا الدليل!
