
# 🧠 DNS Tools - أدوات تحليل واستكشاف نظام أسماء النطاقات  
  
## 📌 مقدمة  
نظام أسماء النطاقات (DNS) هو العمود الفقري لتوجيه أسماء النطاقات إلى عناوين IP على الإنترنت. فهم وتحليل سلوك DNS يساعد في:  
- اكتشاف الأخطاء في إعدادات الشبكة 
- تقييم أمان البنية التحتية 
- جمع معلومات استخباراتية خلال اختبارات الاختراق

  
## 🛠️ أدوات تحليل DNS  
  
🔹 dig (Domain Information Groper)  

-  الوصف : أداة قوية لتنفيذ استعلامات DNS
- الاستخدام : 
 
dig example.com A  
dig @8.8.8.8 example.com 
MX +short

🔹 nslookup

الوصف: أداة تقليدية لاستعلامات DNS، تدعم الوضع التفاعلي.

الاستخدام:

nslookup example.com


🔹 host

الوصف: أداة خفيفة لاستعلامات DNS

الاستخدام:

host example.com


🔹 dnstracer

الوصف: تتبّع المسار الكامل لاستجابة استعلام DNS بدءًا من الـ root servers

الاستخدام:

dnstracer example.com


🔹 dnsenum

الوصف: أداة لاكتشاف المعلومات من نطاقات عبر DNS (مثل subdomains)

الاستخدام:

dnsenum example.com


🔹 fierce

الوصف: أداة استخباراتية شبكية تبحث عن DNS misconfigs وsubdomains

الاستخدام:

fierce -dns example.com


🔹 dnsmap

الوصف: تخمين subdomains بناءً على قائمة معروفة

الاستخدام:

dnsmap example.com


🔹 dnsrecon

الوصف: مسح شامل يتضمن سجلات SOA وAXFR وخدمات أخرى

الاستخدام:

dnsrecon -d example.com


🔹 dmitry

الوصف: أداة متعددة الاستخدامات وتدعم جمع معلومات عن DNS

الاستخدام:

dmitry -w example.com


🔹 whois

الوصف: استخراج معلومات تسجيل النطاق وربطه بعناوين DNS

الاستخدام:

whois example.com


⚠️ ملاحظات أمنية

> تأكد من الحصول على إذن مسبق قبل تنفيذ استعلامات جماعية أو زحف على النطاقات التي لا تملكها


🔗 روابط مرجعية

RFC 1035 - DNS Protocol Specification

دليل dig عبر Linux

dnsrecon GitHub

