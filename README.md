

<p align="center" style="text-align:center" >
  <img src="https://cdn.iconscout.com/icon/free/png-512/redis-3-1175053.png" alt="Redis image"/>
</p>


 <div align="center">
  تهیه کنندگان : زینب احیایی - نرگس جاوید - آتنا ساقی 
</div>
 
<div dir="rtl">

##  مقدمه 


Redis که کوتاه‌ شده‌ی Remote Dictionary Server می باشد؛ یک نوع پایگاه داده‌ی ‌ in-memory (به این معنای که از memory برای ذخیره سازی استفاده می‌کند) و توزیع شده‌است که داده‌ها به صورت دوتایی key-value ذخیره می‌شوند. 
Redis از انواع مختلف ساختارهای داده  ، مانند رشته ها ، لیست ها ،maps ، مجموعه ها ، مجموعه های مرتب شده ، HyperLogLogs ، bitmaps ،  streams spatial indexes پشتیبانی می کند.
این پروژه توسط تیم اصلی پروژه توسعه و نگهداری و از سال 2015 توسط آزمایشگاه های Redis حمایت مالی می شود. 

## تاریخچه 
پروژه Redis از آنجا شروع شد که Salvatore Sanfilippo ، ملقب به antirez ، توسعه دهنده اصلی Redis ، در تلاش بود مقیاس پذیری استارتاپ ایتالیایی خود را بهبود بخشد ، و یک تحلیلگر real-time  سیستم وب ایجاد کند. Sanfilippo پس از مواجهه با مشکلات قابل توجه در مقیاس بندی برخی از انواع بارهای کاری با استفاده از سیستم های پایگاه داده سنتی ، شروع به ساخت نمونه اولیه اولین نسخه مفهوم Redis در Tcl کرد. مدتی بعد Sanfilippo آن نمونه اولیه را به زبان C ترجمه كرد و لیست را پیاده سازی كرد. بعد از چند هفته استفاده موفقیت آمیز از پروژه ، سان فیلیپو آن را open-source کرد . این پروژه مورد توجه قرار گرفت ، بیشتر در بین جامعه Ruby ، با GitHub و اینستاگرام از جمله اولین شرکت هایی بودند که آن را به کار گرفتند. 

Sanfilippo در مارس 2010 توسط VMware استخدام شد.

در ماه مه 2013 ، Redis توسط نرم افزار Pivotal (یک بخش تبلیغاتی VMware) حمایت مالی شد.

در ژوئن 2015 ، توسعه توسط آزمایشگاه های Redis حمایت مالی شد.

در اکتبر 2018 Redis 5.0 با معرفی Redis Stream - ساختار داده ای جدیدی که امکان ذخیره چندین زمینه و مقادیر رشته را با توالی خودکار و مبتنی بر زمان در یک کلید فراهم می کند ، منتشر شد. 


## محبوبیت 


با توجه به رتبه بندی DB-engines اغلب Redis به عنوان محبوب‌ترین پایگاه داده‌ی key-value قرار دارد. هم چنین در بین پایگاه‌ داده‌های NoSQL رتبه چهارم را در رضایت مشتری و حضور در مارکت را بر اساس نظرات کاربران به خود اختصاص داده است و به عنوان محبوب‌ترین پایگاه داده‌ی NoSQl در container ها انتخاب شده‌است.
طبق آمارهای سایت Stackoverflow نیز ، Redis مورد علاقه ترین پایگاه داده  برنامه نویسان در سال‌های ۲۰۱۷ تا ۲۰۲۰ بوده‌است.


##  تفاوت Redis با سایر سیستم‌های پایگاه داده‌ 

Redis ایده سیستمی را رایج کرد که می تواند همزمان یک محل ذخیره‌سازی و یک حافظه پنهان باشد ، با استفاده از طرحی که در آن داده ها در حافظه اصلی رایانه اصلاح می شوند و از آن خوانده میشوند ، اما همچنین بر روی دیسک با قالبی که برای دسترسی تصادفی به داده مناسب نیست ذخیره میشوند ، اما فقط پس از راه اندازی مجدد سیستم ، داده ها را دوباره در حافظه بازسازی می کنیم.
 در همان زمان ، Redis یک مدل داده را ارائه می دهد که در مقایسه با سیستم مدیریت پایگاه داده رابطه ای (RDBMS) بسیار غیر معمول است. دستورات کاربر به صورت کوئری که باید توسط موتور پایگاه داده اجرا شود توصیف نمی شوند بلکه به شکل عملیات خاصی که بر روی داده های abstract انجام می شود ، توصیف می کنند. از این رو ، داده ها باید به روشی ذخیره شوند که بعداً برای بازیابی سریع مناسب باشد  بدون کمک از سیستم پایگاه داده به صورت ایندکس های ثانویه ، تجمع یا سایر ویژگی های مشترک RDBMS قدیمی. 
در پیاده سازی Redis از فراخوان سیستمی fork استفاده زیادی می شود ، تا پردازه ای که داده‌ها را  نگهداری می‌کند کپی کند و پردازه والد همچنان به سرویس دهی به client ادامه دهد ، در حالی که فرآیند فرزند نسخه ای از داده ها را بر روی دیسک ایجاد می کند.


##
زبان‌های پشتیبانی شده
از نسخه 2.6 ،   Redis از امکان اسکریپت نویسی سمت سرور به زبان Lua برخوردار است.
بسیاری از زبان‌های برنامه نویسی دارای Redis language bindings در سمت کلاینت خود می‌باشند.زبان‌هایی که برای آن‌ها کتابخانه کلاینت ردیس وجود دارد، شامل موارد ذیل است:
اکشن‌اسکریپت، سی، سی++، سی شارپ، کلوژر، لیسپ معمولی، دارت، ارلنگ، گو، هسکل، هکس، آی‌او، جاوا، جاوااسکریپت، لوا، آبجکتیو-سی، پرل، پی‌اچ‌پی، پیور داتا، پایتون، آر، روبی، اسکالا، اسمال‌تاک، تی‌سی‌ال که چندین برنامه نرم افزاری کلاینت در این زبانها وجود دارد.

## آموزش نصب 

در این قسمت آموزش نصب Redis 5.0.x بر روی سیستم‌ عامل Ubuntu 20.04 را بررسی می‌کنیم.

برای نصب دستورات زیر را وارد می‌کنیم:



<div dir="ltr">

```
sudo apt update
sudo apt install redis-server
```

</div>




پس از پایان نصب ، سرویس Redis به طور خودکار آغاز می‌شود. برای مشاهده وضعیت سرویس از دستور زیر استفاده می‌کنیم:


<div dir="ltr">

```
sudo systemctl status redis-server
```

</div>



خروجی مانند زیر باید باشد:



<div dir="ltr">

```
redis-server.service - Advanced key-value store
     Loaded: loaded (/lib/systemd/system/redis-server.service; enabled; vendor preset: enabled)
     Active: active (running) since Sat 2020-06-06 20:03:08 UTC; 10s ago
...
```

</div>


اکنون Redis برای سیستم عامل نصب می‌باشد. ولی به طور خودکار Redis اتصالات remote را نمی‌پذیرد و تنها از localhost ( جایی که Redis اجرا میشود) می‌توان به آن متصل شد بنابراین برای اینکه بتوان به صورت remote هم متصل شد باید آن را تنظیم کنیم:

ابتدا فایل configure را با دستور زیر باز کنید:


<div dir="ltr">

```
sudo nano /etc/redis/redis.conf
```

</div>

خطی که با bind 127.0.0.1 ::1 شروع میشود را پیدا کرده و کامنت کنید. 


 
<div dir="ltr">

```
#bind 127.0.0.1 ::1
```

</div>

توجه : در صورتی که client ای که به پایگاه داده متصل میشود روی همان سیستمی که host قرار دارند، نباید این کار را انجام دهید!

سپس فایل را ذخیره کرده و با دستور زیر سرویس Redis را آپدیت کنید.



<div dir="ltr">

```
sudo systemctl restart redis-server
```

</div>

سپس با دستور زیر می‌توان مطمئن شد که Redis بر روی تمام interface  های پورت مورد نظر(در اینجا 6379) در حال listen است:


<div dir="ltr">

```
ss -an | grep 6379
```

</div>


خروجی دستور مشابه زیر هست که در آن 0.0.0.0 بیانگر آدرس‌های IPv4 هست.



<div dir="ltr">

```
tcp  LISTEN 0   511   0.0.0.0:6379   0.0.0.0:*
tcp  LISTEN 0   511      [::]:6379      [::]:* 
```

</div>

 در قدم بعدی باید تنظیمات firewall خود را به گونه قرار دهید که ترافیک‌های TCP در پورت 6379 را فعال کند.
 (مطمئن شید که firewall شما اتصالات معتبر و بدون خطری رو قبول کند)
معمولا میخوایم که IP address های خاصی اجازه دسترسی به سرور Redis داشته باشند، مثلا اگر بخواهیم فقط اتصالاتی که از زیرشبکه‌ی 192.168.121.0/24 هستند دسترسی داشته باشند ، دستور زیر را اجرا میکنیم:


<div dir="ltr">

```
sudo ufw allow proto tcp from 192.168.121.0/24 to any port 6379
```

</div>
 
 
 الان شما می‌توانید یک اتصال TCP روی پورت 6379 به Redis از remote connections داشته باشید.
 
اگر خواستید مطمئن بشید که همه چی به درستی تنظیم شده کافی است  سرور Redis در ماشین remote را با دستور زیر ping کنید:

<div dir="ltr">

```
redis-cli -h <REDIS_IP_ADDRESS> ping
```

</div>


دستور باید خروجی زیر را نشان دهد:

 


<div dir="ltr">

```
PONG
```

</div>



 
</div>
