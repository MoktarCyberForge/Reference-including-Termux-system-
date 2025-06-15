
# طريقة تنزيل Metasploit Framework على Termux بالطريقة الصحيحة

---

## مقدمة

Metasploit Framework هو أشهر إطار عمل لاختبار الاختراق والاستغلال، وهو يدعم مجموعة واسعة من الثغرات والبرمجيات الخبيثة. تثبيت Metasploit على Termux يسمح لك باستخدامه على أجهزة أندرويد بشكل متنقل.

---

## المتطلبات الأساسية

- جهاز أندرويد يعمل بنظام حديث.
- تطبيق Termux مُثبت ومُحدث.
- اتصال إنترنت مستقر.
- مساحة تخزين كافية (حوالي 1.5 جيجابايت على الأقل).

---

## خطوات التثبيت

### 1. تحديث وإعداد Termux

ابدأ بتحديث الحزم الأساسية:

```bash
pkg update && pkg upgrade -y
pkg install curl wget git -y


---

2. تثبيت بيئة البناء الأساسية

لتثبيت الأدوات اللازمة لبناء بعض مكونات Metasploit:

pkg install unstable-repo
pkg install metasploit

ملاحظة: في بعض نسخ Termux، متاح تثبيت Metasploit مباشرة من المستودعات غير المستقرة unstable-repo. تحقق أولاً من هذا الخيار لأنه الأسهل.


---

3. (اختياري) تثبيت يدوي إذا لم يتوفر في المستودعات

إذا لم يكن متاحًا عبر pkg install metasploit، يمكنك تثبيته يدويًا كالتالي:

3.1 تثبيت متطلبات Ruby والأدوات

pkg install ruby
pkg install ruby-dev
pkg install clang make git curl -y
pkg install postgresql

3.2 إعداد PostgreSQL

pg_ctl -D $PREFIX/var/lib/postgresql start

إذا لم يبدأ، قم بتهيئة قاعدة البيانات أولاً:

initdb $PREFIX/var/lib/postgresql
pg_ctl -D $PREFIX/var/lib/postgresql start


---

3.3 تنزيل Metasploit Framework

cd $HOME
git clone https://github.com/rapid7/metasploit-framework.git
cd metasploit-framework


---

3.4 تثبيت الجواهر (gems) المطلوبة

gem install bundler
bundle install

قد يستغرق هذا بعض الوقت.


---

4. تشغيل Metasploit

لتشغيل msfconsole:

./msfconsole


---

نصائح مهمة

تحديث مستمر: لتحديث Metasploit، استخدم داخل مجلد metasploit-framework الأمر:


git pull
bundle install

إدارة قواعد البيانات: تأكد أن خدمة PostgreSQL تعمل قبل تشغيل Metasploit.

صلاحيات: بعض الأوامر قد تحتاج صلاحيات root على بعض الأجهزة، لكن Termux يعمل بشكل جيد بدونها عادة.

المشاكل الشائعة:

إذا ظهرت أخطاء في تثبيت الجواهر، حاول تثبيت حزم البناء (build-essential equivalents) وأدوات التطوير.

تحقق من اتصال الإنترنت ومستودعات Git.




---

خاتمة

باتباع هذه الخطوات يمكنك تثبيت وتشغيل Metasploit Framework على Termux بشكل صحيح، مما يتيح لك بيئة اختبار اختراق قوية على جهازك المحمول.
