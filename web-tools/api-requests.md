# 🌐 API Requests - تنفيذ طلبات API  
  
## 📌 مقدمة  
تُستخدم واجهات برمجة التطبيقات (API) كوسيلة للتفاعل مع الخدمات المختلفة عبر الإنترنت سواء للحصول على البيانات أو تنفيذ عمليات معينة
 
في هذا الدليل سنتعرف على كيفية إرسال طلبات API باستخدام عدة لغات برمجية مع أمثلة عملية 
  
  
## 🛠️ أنواع طلبات API الأساسية 

### 🔹 GET

-  الوصف : يُستخدم لجلب البيانات من الخادم.  
-  الاستخدام :  
  curl -X GET "https://api.example.com/data"

🔹 POST

الوصف: يُستخدم لإرسال بيانات إلى الخادم.

الاستخدام:

curl -X POST -H "Content-Type: application/json" -d '{"name": "John"}' "https://api.example.com/users"


🔹 PUT

الوصف: يُستخدم لتحديث البيانات الموجودة

الاستخدام:

curl -X PUT -H "Content-Type: application/json" -d '{"name": "Jane"}' "https://api.example.com/users/1"


🔹 DELETE

الوصف: يُستخدم لحذف بيانات معينة.

الاستخدام:

curl -X DELETE "https://api.example.com/users/1"


🔧 إرسال طلبات API عبر لغات مختلفة
🐍 Python - باستخدام requests

import requests  
  
url = "https://api.example.com/data"  
response = requests.get(url)  
  
if response.status_code == 200:  
    print(response.json())

💡 المزايا: سهلة الاستخدام وتدعم مصادقة OAuth وHeaders المخصصة


🌍 JavaScript - باستخدام fetch

fetch("https://api.example.com/data")  
.then(response => response.json())  
.then(data => console.log(data))  
.catch(error => console.error("Error:", error));

💡 المزايا: تعمل بسلاسة داخل المتصفحات وتدعم Async/Await


💎 Ruby - باستخدام Net::HTTP

require 'net/http'  
require 'json'  
  
url = URI("https://api.example.com/data")  
response = Net::HTTP.get(url)  
puts JSON.parse(response)

💡 المزايا: دعم مباشر لبروتوكولات HTTP/HTTPS


⚙️ إضافة Headers ومصادقة API
عند التعامل مع API يتطلب مصادقة عبر مفتاح API ، يمكن استخدام Headers لضمان أمان الطلب:

curl -H "Authorization: Bearer YOUR_ACCESS_TOKEN" "https://api.example.com/protected-data"


⚠️ الاعتبارات الأمنية

 تجنب مشاركة مفاتيح API في المستودعات العامة

استخدم HTTPS لضمان تشفير البيانات أثناء النقل

تحقق من إدارة الأخطاء لضمان التعامل الآمن مع الاستجابات غير المتوقعة




🔗 روابط مفيدة

التوثيق الرسمي لـ requests في Python

دليل fetch في JavaScript

مكتبة Net::HTTP في Ruby


✨ المساهمة
هل لديك تحسينات أو لغات أخرى لإضافتها؟ يمكنك تقديم Pull Request لإثراء هذا الدليل! 🚀
