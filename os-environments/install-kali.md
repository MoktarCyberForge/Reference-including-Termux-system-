
# 🛡️ تثبيت Kali Linux داخل Termux  
  
## 📌 مقدمة  
Kali Linux 
هي توزيعة مختصة في اختبار الاختراق والأمن السيبراني وتوفر مجموعة قوية من الأدوات لتقييم أمان الأنظمة والشبكات  
يمكن لمستخدمي Termux على Android تشغيل Kali Linux عبر proot-distro بدون الحاجة لصلاحيات root
  
💡 ملاحظة: هذا الدليل مخصص لمستخدمي Termux ويُراعي الأداء والموارد المحدودة للهواتف المحمولة
  
## 🛠 تثبيت Kali Linux داخل Termux
### 🔹 تحديث الحزم الأساسية:  

pkg update && pkg upgrade -y

🔹 تثبيت proot-distro:

pkg install proot-distro -y

🔹 تثبيت Kali Linux عبر proot-distro:

proot-distro install kali

🔹 تسجيل الدخول إلى Kali:

proot-distro login kali

✅ بعد الدخول، يمكنك البدء باستخدام بيئة Kali داخل Termux.



📦 إعداد الأدوات داخل Kali
✅ تحديث النظام:

apt update && apt upgrade -y

✅ تثبيت أدوات الاختبار الأساسية:

apt install nmap hydra metasploit-framework sqlmap -y

✅ التحقق من التثبيت:

nmap --version  
msfconsole


🖥️ تشغيل بيئة سطح المكتب داخل Kali
✅ تثبيت XFCE وتشغيل VNC

apt install xfce4

 xfce4-goodies tightvncserver -y  
vncserver:1

ثم الدخول عبر VNC Viewer إلى:

localhost:5901


🔄 إدارة Kali Linux 
داخل Termux
الأمرالوظيفة
proot-distro login kali
تسجيل الدخول إلى النظام
apt install package
تثبيت حزمة
apt remove package
إزالة حزمة
exit
الخروج من Kali---

⚠️ الاعتبارات الأمنية

 لا تستخدم الأدوات ضد أي شبكة أو نظام بدون إذن رسمي

تأكد من تحديث Kali بانتظام لضمان حماية الأدوات من الثغرات

استخدم VPN عند اختبار الاختراق لتأمين الاتصال

🔗 روابط مفيدة

Kali Linux Documentation

Proot Distro Guide

Metasploit Framework Guide



✨ المساهمة
هل لديك تحسينات على إعداد Kali داخل Termux؟ يمكنك إرسال Pull Request لإثراء هذا الدليل! 🚀
