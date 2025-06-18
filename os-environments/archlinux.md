
# 🏗️ تثبيت وإعداد Arch Linux داخل Termux  
  
## 📌 مقدمة  
Arch Linux هي توزيعة خفيفة ومرنة تمنح المستخدم تحكمًا كاملاً في النظام مما يجعلها مثالية لتشغيل بيئة Linux داخل
Termux على أجهزة Android
سنستخدم  proot-distro 
لتثبيت Arch داخل Termux بطريقة آمنة دون الحاجة لصلاحيات root
  
💡 ملاحظة: هذا الدليل مخصص لمستخدمي Termux على Android، مع مراعاة الأداء والموارد المحدودة للهواتف المحمولة

  
## 🛠️ تثبيت Arch Linux داخل Termux
### 🔹 1️⃣ تحديث المستودعات وتحضير البيئة
 
pkg update && pkg upgrade -y  
pkg install proot-distro -y

🔹 2️⃣ تثبيت Arch Linux عبر proot-distro

proot-distro install archlinux

🔹 3️⃣ تسجيل الدخول إلى النظام

proot-distro login archlinux

✅ عند تنفيذ الأمر، سيتم فتح بيئة Arch داخل Termux ويمكنك بدء استخدام النظام!

⚙️ تهيئة النظام داخل Arch Linux
🔹 تحديث الحزم:

pacman -Syu

🔹 تثبيت حزم أساسية:

pacman -S nano git curl wget neofetch

🔹 ضبط اللغة واللوحة:

echo "export LANG=en_US.UTF-8">> ~/.bashrc  
source ~/.bashrc


🖥️ تشغيل سطح المكتب داخل Arch عبر VNC
✅ تثبيت بيئة XFCE والتشغيل عبر VNC

pacman -S xfce4 xfce4-goodies tigervnc  
vncserver:1

ثم الدخول عبر تطبيق VNC Viewer إلى:

localhost:5901

🔄 إدارة Arch Linux داخل Termux
الأمرالوظيفة

proot-distro login archlinux
تسجيل الدخول إلى النظام
pacman -S package
تثبيت حزمة
pacman -R package
إزالة حزمة
exit
الخروج من Arch---

⚠️ الاعتبارات الأمنية

 لا تُعطل آلية التحديثات لتجنب وجود ثغرات أمنية

استخدم بيئة افتراضية داخل Arch لحماية النظام من الفوضى

احذر من تثبيت حزم غير موثوقة لضمان سلامة البيئه


🔗 روابط مفيدة

Arch Wiki - دليل المستخدم

Termux Proot Distro Wiki

كيفية تشغيل Arch داخل Android




✨ المساهمة
هل لديك تحسينات على إعداد Arch داخل Termux؟ يمكنك إرسال Pull Request لإثراء هذا الدليل! 🚀
