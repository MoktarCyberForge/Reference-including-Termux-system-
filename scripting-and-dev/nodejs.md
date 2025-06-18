# 🚀 تطوير التطبيقات باستخدام Node.js في Termux  
  
## 📌 مقدمة  
Node.js هو بيئة تشغيل JavaScript على الخوادم تعتمد على محرك V8 الخاص بـ Google، مما يجله سريعة وخفيفة

يمكن تشغيل Node.js داخل Termux لتطوير تطبيقات Backend واجهات API وأدوات برمجية مباشرة على الهاتف!  
  
💡ملاحظة: هذا الدليل مخصص لمستخدمي Termux ويُراعي بيئة التشغيل المحمولة

  
## 🛠 تثبيت Node.js في Termux
  
### 1️⃣ تحديث المستودعات  

pkg update && pkg upgrade -y

2️⃣ تثبيت Node.js

pkg install nodejs -y

✅ بعد التثبيت، تحقق من الإصدار:

node -v


📑 إدارة الحزم عبر npm
🔹 التحقق من وجود npm

npm -v

🔹 تثبيت حزمة جديدة

npm install express

🔹 تشغيل مشروع Node.js

node app.js



🔄 إنشاء خادم API بسيط في Termux
📌 يمكن تشغيل Express.js لإنشاء خادم ويب بسيط:

const express = require('express');  
const app = express();  
  
app.get('/', (req, res) => {  
    res.send('🚀 مرحبًا بك في API عبر Termux!');  
});  
  
app.listen(3000, () => {  
    console.log('✅ الخادم يعمل على http://localhost:3000');  
});

حفظه كـ server.js ثم تشغيله:

node server.js



⚙️ إدارة عمليات Node.js في Termux
🔹 تشغيل تطبيق في الخلفية

nohup node server.js &

🔹 إيقاف العملية

pkill node

🔹 عرض العمليات النشطة

ps aux | grep node


⚠️ الاعتبارات الأمنية

 تجنب تشغيل أكواد غير موثوقة داخل بيئة Termux

لا تحتفظ بمفاتيح API داخل ملفات JavaScript المكشوفة

استخدم pm2 لإدارة العمليات بأمان




🔗 روابط مفيدة

توثيق Node.js الرسمي

دليل Express.js

أفضل الممارسات في إدارة عمليات Node.js


✨ المساهمة
هل لديك تحسينات أو تقنيات أخرى يمكنك إضافتها؟ ساهم عبر إرسال Pull Request لإثراء هذا الدليل! 🚀
