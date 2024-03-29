<div dir="rtl">
  
# بخش ۲ - شروع با آجرها: الگوهای برنامه‌نویسی</br>
در آغاز این بخش در مورد تاریخچه‌ی زبان‌‌های برنامه نویسی و تکامل آن‌ها صحبت می‌کند و  سپس به اشاره می‌کند که سه نوع الگوی برنامه‌ نویسی وجود دارد. در سه فصل بعدی به توضیح هر کدام از این سه الگوی برنامه نویسی پرداخته است

## فصل ۳ - دیدگاه کلی در مورد الگوها
-  برنامه نویسی ساخت‌یافته: این الگو توسط آقای دایکسترا کشف شد و در آن دستورات goto را حذف و به حای آن دستورات زیر را جایگزین نمود:
  if/then/else & do/while/until</br>
  این الگو نظمی در مورد انتقال مستقیم کنترل طرح می‌کند
- برنامه نویسی شی‌گرا: توسط دال و نایگارد کشف شد. در این الگو اشاره‌گرهای توابع حذف شدند.</br>
  درواقع نظمی در مورد انتقال غیرمستقیم کنترل بیان می‌کند
- اولین الگوی کشف شده توسط آقای چرچ بود. در این الگو انتصاب حالات و متغیرها حذف شد :(FP)functional برنامه نویسی 

تمام این سه ساختار به بحث معماری نرم‌افزار مربوط می‌شوند به عنوان مثال از ویژگی چند ریختی برنامه نویسی شی‌گرا به عنوان یک مکانیزم عبور از مرز و محدودیت‌های معماری استفاده کرد یا از FP برای بیان نظم در مورد مکان و دسترسی داده 

## فصل ۴ - برنامه نویسی ساخت یافته
دایکسترا معتقد بود که کسی علم یا نظم برنامه نویسی رو درک نمی‌کند و ساختاری هم برای آن نیست. اون برروی این موضوع کار کرد و سعی کرد تا از ساختار اثباتی ریاضی استفاده کند. با جستجوهایی که انجام داد متوجه شد که دستور goto باعث غیر اثبات‌پذیری برنامه نویسی می‌شود و این دستور را مضر دانست به همین جهت دستورات do/while/until و if/else/then را جایگزین کرد اما باز هم ویژگی غیراثبات‌پذیر بودن را نتوانستند حل کنند.
برنامه نویس‌ها با توشتن تست سعی می‌کنند تا درستی برنامه خود را اثبات کنند اما آقای دکسترا در این زمینه گفتند:

> تست تنها حضور یک باگ را نشان می‌دهد نه نبود آن را</br>

بنابراین تست‌هایی که برنامه نویس‌ها می‌نویسند برای اثبات حضور باگ است تا بتوانند آن را رفع کنند و برنامه را به سمتی ببرند که کمترین خطا را داشته باشد.
در این جا به کمک معماری درست می‌توان به گونه‌ای اجزای برنامه را طراحی کرد و نوشت که تست آن‌ها راحت باشد

## فصل ۵ - برنامه نویسی شی‌گرا
درک مفاهیم و کاربر طراحی شی‌گرا اساس یک معماری خوب است. برنامه نویسی شی‌گرا ترکیب داده و عملکرد یا به عبارت دیگر راهی برای طراحی جهان واقعی است. برنامه نویسی شی‌گرا با سه ویژگی تعریف می‌شود:
 - چند ریختی (polymorphism): اجازه می‌دهد تا یک تابع را بتوانیم کلی‌تر بنویسیم و مختص یک حالت خاص نباشد. قدرتی است که اجازه می‌دهد تا بدون آنکه تغییر در کد منبع داده شود چند حالت خاص(مانند کار با یک تابع اما با data type های مختلف) را تست کرد 
 - ایزوله کردن (encapsulation): در واقع ایزوله سازی توابع و داده را راحت و موثر می‌کند و می‌توان گفت که مخفی کردن یک سری داده و توابع از دید کاربر است
 - ارث بری (inheritance): کمک می‌کند که از تعریف و استفاده مجدد توابع و متغیرها پرهیز کنیم
مفهوم دیگری که در این فصل توضیح داده شده است وارونگی وابستگی (dependency inversion) نام دارد. این ویژگی این امکان را فراهم می‌کند تا با قسمت‌های مختلف نرم‌افزار مانند یک پلاگین رفتار و طراحی کنیم. که مفهوم درواقع هسته‌ی معماری تمیز است.
به کمک مفاهیم شی‌گرایی سیستم را به گونه‌ای تصمیم گرفت که کدام قسمت‌ها از کدهای برنامه(درواقع کلاس‌ها و کامپوننت‌ها) به یکدیگر وابسته باشند. از مزیت این کار می‌توان به این مورد اشاره کرد هنگامی که یک قسمت از برنامه تغییر می‌کند نیازی نیست که تمام برنامه deploy شود و تنها می‌توان آن قسمت‌هایی را deploy کرد که وابسته به کامپوننت تغییر داده شده بودند

## فصل ۶ - برنامه نویسی Functional
در این فصل ابتدا یک مثال مانند کد زیر، از زبان LISP نشان داد که یک زبان Functional است. در این مثال هیچ متغیری تعریف نشده است و صرفا چند تابع فراخوانی شده است و در نهایت توسط تابع println خروجی مورد نظر چاپ می‌شود

<div dir="ltr">
  
```lisp
  (println (take 25 (map (fn [x] (* x x)) (range))))
```
  
</div>
تفاوتی که زبان‌های functional با زبان‌های شی‌گرا دارند در آن است که متغیرها در زبان‌های شی‌گرا mutable هستند اما در زبان‌های functional اینگونه نیست و به گونه‌ای طراحی شدند که متغیری برای تغییر دادن و اصلاحا mutate کردن وجود ندارد.
این ویژگی از بروز مشکلاتی مانند race condition، بن بست (deadlock) و بروز رسانی همزمان (cuncurrent updates) جلوگیری می‌کند
موضوع mutability در طراحی سیستم‌های چند نخی بسیار اهمیت پیدا می‌کند  به همین جهت برای حل این مشکل می‌توان برنامه یا سرویس‌ها را جدا کرد. یعنی برنامه یا سرویس‌ها را به دو کامپوننت mutable و immutable تقسیم کرد. آن کامپوننت‌هایی که قرار نیست بروز شوند و نباید تغییر کنند immutable خواهند بود که این کامپوننت‌ها با چند کامپوننت دیگر که mutable هستند در ارتباط خواهند بود. این کامپوننت‌ها نیز متغیرها را در حافظه‌ی transactional نگهداری می‌کنند.
سعی معمار باید در آن باشد که تا حد امکان پردازش‌ها را سمت کامپوننت‌های immutable ببرد و کدهای mutable را از immutable جدا کند.
موضوع آخری که در این فصل به آن اشاره شد منبع یابی رویداد است. در این قسمت یک برنامه بانکی را مثال می‌زند که در آن موجودی حساب یک کاربر با هر تراکنش حساب می‌کند و به کمک mutation این عمل را انجام می‌دهد.
اما این برنامه‌ی بانکی می‌تواند بدون mutation هم کار کند. به این صورت که تنها تاریخچه‌ی تراکنش‌ها را برنامه نگه می‌دارد و هنگامی که نیاز شد به محاسبه‌ی موجودی می‌پردازد. دلیل ارائه‌ی این راه حل آن است که تراکنش‌های بانکی بسیار زیاد است و محاسبه‌ی آن در هر لحظه بسیار هزینه بر است. درمنبع‌یابی رویداد هیچ چیزی حذف یا بروز نمی‌شود تنها رکوردهای جدید ایجاد می‌شوند و حالت فعلی نتیجه‌ی نمایش تمام رکوردهاست

 
</div>
