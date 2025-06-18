# 🐧 تشغيل Ubuntu داخل Termux باستخدام PRoot  
  
## 📌 مقدمة  
يُتيح proot
إمكانية تشغيل توزيعات Linux داخل Termux على Android دون الحاجة لصلاحيات root  
يمكن لمستخدمي Termux تثبيت Ubuntu والاستفادة من بيئة Linux الكاملة داخل هواتفهم، مما يُسهل إدارة التطبيقات الاختبار والتطوير
  
💡ملاحظة: هذا الدليل مخصص لمستخدمي Termux ويُراعي أداء النظام وقيود Android
 
  
## 🛠️ تثبيت Ubuntu داخل Termux باستخدام PRoot

### 🔹 تحديث وإعداد بيئة Termux:  
pkg update && pkg upgrade -y  
pkg install proot-distro -y

🔹 تثبيت Ubuntu باستخدام proot-distro:

proot-distro install ubuntu

✅ بعد التثبيت، يمكنك تسجيل الدخول إلى Ubuntu باستخدام:

proot-distro login ubuntu


⚙️ تهيئة وإدارة النظام داخل Ubuntu
✅ تحديث الحزم الأساسية:

apt update && apt upgrade -y

✅ تثبيت أدوات أساسية:

apt install nano git curl wget neofetch -y

✅ التحقق من بيئة النظام:

lsb_release -a  
neofetch


🖥️ تشغيل بيئة سطح المكتب داخل Ubuntu عبر VNC
✅ تثبيت بيئة XFCE وتشغيل VNC

apt install xfce4 xfce4-goodies tightvncserver -y  
vncserver:1

ثم الدخول عبر VNC Viewer إلى:

localhost:5901

🔄 إدارة Ubuntu
 داخل Termux
الأمرالوظيفة
proot-distro login ubuntuتسجيل الدخول إلى النظام
apt install package. تثبيت حزمة
apt remove packageإزالة حزمة
exit الخروج من Ubuntu---

⚠️ الاعتبارات الأمنية

 لا تُعطل التحديثات لتجنب وجود ثغرات أمنية

استخدم بيئة افتراضية داخل Ubuntu لضمان استقرار النظام

احذر من تثبيت برامج غير موثوقة داخل بيئة التشغيل





🔗 روابط مفيدة

Ubuntu Official Documentation

Termux Proot Distro Guide

XFCE Desktop Environment


✨ المساهمة
هل لديك تحسينات على إعداد Ubuntu داخل Termux؟ يمكنك إرسال Pull Request لإثراء هذا الدليل! 🚀
