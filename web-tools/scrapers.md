# 🕷️ Web Scraping - تقنيات وأدوات جمع البيانات  
  
## 📌 مقدمة  
Web Scraping هو عملية جمع واستخراج البيانات من مواقع الويب بطريقة تلقائية تُستخدم هذه التقنية في العديد من المجالات، مثل:  
- تحليل البيانات التسويقية والمنافسة  
- جمع الأخبار والمقالات من مصادر مختلفة 
- إنشاء قواعد بيانات ضخمة بناءً على المعلومات المستخرجة
  
- 🛠️ أدوات وتقنيات Web Scraping  

🔹BeautifulSoup
 
- الوصف: مكتبة Python تُستخدم لتحليل HTML و XML واستخراج البيانات بسهولة
-  الاستخدام :  
 
from bs4 import BeautifulSoup  
  import requests  
  
  url = "https://example.com"  
  response = requests.get(url)  
  soup = BeautifulSoup(response.text, "html.parser")  
  print(soup.title.text)

المزايا: سهلة الاستخدام وتعمل بكفاءة عالية


🔹 Scrapy

الوصف: إطار عمل قوي لجمع البيانات يُستخدم لإنشاء روبوتات Web Crawlers

الاستخدام:

import scrapy  

class ExampleSpider(scrapy.Spider):  
    name = "example"  
    start_urls = ["https://example.com"]  

    def parse(self, response):  
        yield {"title": response.xpath("//title/text()").get()}

المزايا: سريع يدعم التعامل مع قواعد البيانات والـ APIs ويسمح بجمع البيانات بطريقة منظمة


🔹 Selenium

الوصف: أداة تُستخدم للتحكم في المتصفحات وتنفيذ عمليات مثل تسجيل الدخول أو التعامل مع المواقع الديناميكية

الاستخدام:

from selenium import webdriver  

driver = webdriver.Chrome()  
driver.get("https://example.com")  
print(driver.title)  
driver.quit()

المزايا: مفيد لجمع البيانات من المواقع التي تعتمد على JavaScript.


🔹 Puppeteer

الوصف: أداة تعتمد على Node.js للتحكم في متصفح Chrome وجمع البيانات

الاستخدام:

const puppeteer = require('puppeteer');  

(async () => {  
    const browser = await puppeteer.launch();  
    const page = await browser.newPage();  
    await page.goto('https://example.com');  
    console.log(await page.title());  
    await browser.close();


})();

- المزايا: يوفر تحكمًا كاملًا في المتصفح ويعمل بكفاءة عالية مع التطبيقات التفاعلية

⚠️ الاعتبارات القانونية

يجب التأكد من أن جمع البيانات يتم بشكل قانوني وبما يتوافق مع سياسات المواقع المختلفة. بعض المواقع قد تمنع Web Scraping أو تتطلب إذنًا مسبقًا


🔗 روابط مفيدة 
- [دليل BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/)  
- [التوثيق الرسمي لـ Scrapy](https://docs.scrapy.org/en/latest/)  
- [التوثيق الرسمي لـ Selenium](https://www.selenium.dev/documentation/)  
- [مستودع Puppeteer على GitHub](https://github.com/puppeteer/puppeteer)  

✨ المساهمة
هل لديك أدوات أخرى تود إضافتها؟ يمكنك إرسال Pull Request لإثراء هذا الدليل! 🚀
