# دليل استخدام sqlmap في Termux

## ما هو sqlmap؟

sqlmap هو أداة مفتوحة المصدر لأتمتة اكتشاف واستغلال ثغرات SQL Injection في تطبيقات الويب. تساعد الباحثين في الأمن السيبراني في اختبار أمان قواعد البيانات المرتبطة بالمواقع


## 1. تثبيت sqlmap على Termux

Termux يحتوي على مستودعات محدودة وبعض الأدوات قد لا تكون محدثة أو غير موجودة بشكل مباشر. لكن يمكن تثبيت sqlmap باتباع الخطوات التالية:

### 1.1 تحديث مستودعات Termux

```bash
pkg update && pkg upgrade -y

1.2 تثبيت Python (ضروري لتشغيل sqlmap)

pkg install python -y

1.3 تثبيت Git (لاستنساخ المستودع الرسمي)

pkg install git -y

1.4 استنساخ sqlmap من GitHub

git clone --depth=1 https://github.com/sqlmapproject/sqlmap.git

1.5 تشغيل sqlmap

cd sqlmap
python3 sqlmap.py --help



2. استخدام sqlmap

2.1 فحص هدف بسيط

python3 sqlmap.py -u "http://example.com/vuln.php?id=1"

هذا الأمر يفحص إذا كانت صفحة الويب معرضة لهجوم SQL Injection.

2.2 فحص مع تحديد طريقة طلب POST

python3 sqlmap.py -u "http://example.com/login.php" --data="username=admin&password=admin"


3. أوامر مهمة في sqlmap

الأمر	الشرح

-u URL	تحديد رابط الهدف
--data=DATA	تحديد بيانات POST
--dbs	جلب أسماء قواعد البيانات
--tables	جلب جداول قاعدة البيانات
--columns	جلب أعمدة جدول معين
--dump	استخراج بيانات من الجدول
--os-shell	فتح شيل نظام التشغيل (إن أمكن)
--batch	تشغيل بدون تأكيد المستخدم




4. نصائح لاستخدام sqlmap على Termux

تأكد من وجود اتصال إنترنت مستقر عند استنساخ الأداة أو تثبيت الحزم.

بعض الأوامر قد تحتاج صلاحيات root أو لا تعمل على بعض الأهداف بسبب حماية السيرفر.

استخدم خيار  --batch ل
لتشغيل الآلي دون تدخل

دائماً اختبر على بيئة اختبار خاصة أو بعد الحصول على إذن قانوني


5. حل مشاكل شائعة

5.1 خطأ في استيراد مكتبات Python

إذا ظهر خطأ متعلق بمكتبات مفقودة، قم بتثبيتها يدوياً:

pip install requests
pip install urllib3

5.2 الأداة لا تعمل أو تظهر أخطاء في Termux

تأكد من تحديث Termux وأدواته

أعد تثبيت Python وGit

جرب حذف مجلد sqlmap وإعادة استنساخه


6. مصادر إضافية

صفحة sqlmap الرسمية على GitHub

مستندات الاستخدام داخل مجلد sqlmap (README.md)

دروس فيديو على YouTube خاصة باستخدام sqlmap مع Termux


الخلاصة

sqlmap أداة قوية لاكتشاف واستغلال ثغرات SQL Injection. تثبيتها على Termux سهلة عبر استنساخ المستودع الرسمي وتشغيلها بواسطة Python. يجب دائماً استخدام الأداة بطريقة قانونية وتحت إذن مسبق.
