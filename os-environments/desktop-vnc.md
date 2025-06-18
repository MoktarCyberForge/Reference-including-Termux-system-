
# 🖥️ تشغيل بيئة سطح المكتب في Termux باستخدام VNC  
  
## 📌 مقدمة  
يمكن لمستخدمي Termux على Android تشغيل بيئة رسومية كاملة (Desktop Environment) باستخدام خوادم VNC، مما يتيح الوصول إلى تجربة Linux حقيقية برسوميات كاملة داخل الهاتف  
تُعد هذه الطريقة مثالية لتشغيل تطبيقات رسومية محررات كود متصفحات وغيرها دون الحاجة لصلاحيات root 
  
💡ملاحظة: هذه الإعدادات تعمل على أجهزة Android داخل Termux بدون صلاحيات root
 
  
## 🛠️ الأدوات المطلوبة  
- Termux 

- حزمة proot-distro لتثبيت توزيعة Linux  
- خادم VNC server مثل tigervnc 
- تطبيق VNC Viewer على Android (مثل RealVNC أو bVNC)  
 
  
## 🐧 تثبيت توزيعة Ubuntu  
```bash  
pkg update && pkg install proot-distro -y  
proot-distro install ubuntu  
proot-distro login ubuntu


🖥️ تثبيت سطح المكتب داخل التوزيعة
✅ داخل بيئة Ubuntu:

apt update && apt install xfce4 xfce4-goodies tightvncserver -y

أدخل الأمر التالي لإنشاء كلمة مرور:

vncserver:1

🔐 سيسألك عن كلمة مرور VNC (من 6-8 أحرف)

🎛️ تشغيل جلسة VNC مع XFCE
لتهيئة الجلسة:

vncserver -kill:1  
nano ~/.vnc/xstartup

استبدل محتوى الملف بالتالي:

#!/bin/sh  
unset SESSION_MANAGER  
unset DBUS_SESSION_BUS_ADDRESS  
startxfce4 &

ثم:

chmod +x ~/.vnc/xstartup  
vncserver:1


📲 الدخول إلى واجهة سطح المكتب من هاتفك

1. حمّل تطبيق VNC Viewer من المتجر


2. أنشئ اتصالًا جديدًا إلى:



localhost:5901

3. أدخل كلمة المرور التي حددتها


4. استمتع ببيئة سطح مكتب كاملة!




🔄 أوامر مفيدة
الأمرالوظيفةvncserver:1بدء الخادمvncserver -kill:1إيقاف الجلسةproot-distro login ubuntuالدخول إلى التوزيعة---

⚠️ الاعتبارات الأمنية

 اختر كلمة مرور قوية لجلسات VNC

لا تفتح المنفذ إلى الإنترنت إلا إذا كنت تستخدم نفقًا آمنًا (SSH tunnel)

تأكد من إيقاف الخادم بعد الانتهاء لحماية البطارية والموارد




🔗 مصادر مفيدة

Proot Distro Guide

XFCE Desktop

TigerVNC GitHub


✨ المساهمة
إذا كانت لديك تحسينات أو توزيعات بديلة تود مشاركتها أرسل Pull Request لإثراء هذا الملف! 🚀
