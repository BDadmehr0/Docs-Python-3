# 2. استفاده از مفسر پایتون

## 2.1. فراخوانی مفسر

مفسر پایتون معمولاً در مسیر `/usr/local/bin/python3.13` نصب شده است، در ماشین‌هایی که این برنامه در دسترس است؛ قرار دادن `/usr/local/bin` در مسیر جستجوی شل یونیکس شما این امکان را می‌دهد که با وارد کردن دستور زیر آن را شروع کنید:

``` bash
python3.13
```

به شل. [^1] از آنجایی که انتخاب دایرکتوری که مفسر در آن قرار دارد یک گزینه نصب است، مکان‌های دیگری نیز ممکن است؛ با کارشناس محلی پایتون یا مدیر سیستم خود مشورت کنید. (به عنوان مثال، `/usr/local/python` یک مکان جایگزین محبوب است.)

در ماشین‌های ویندوز که پایتون را از [فروشگاه مایکروسافت](https://docs.python.org/3/using/windows.html#windows-store) نصب کرده‌اید، دستور `python3.13` در دسترس خواهد بود. اگر برنامه [راه‌انداز py.exe](https://docs.python.org/3/using/windows.html#launcher) را نصب کرده‌اید، می‌توانید از دستور `py` استفاده کنید. برای روش‌های دیگر راه‌اندازی پایتون، به بخش «[پیش‌زمینه: تنظیم متغیرهای محیطی](https://docs.python.org/3/using/windows.html#setting-envvars)» مراجعه کنید.

نوشتن کاراکتر پایان فایل (`Control-D` در یونیکس و `Control-Z` در ویندوز) در پروپمت اصلی باعث خروج مفسر با وضعیت خروجی صفر می‌شود. اگر این کار نتیجه نداد، می‌توانید با نوشتن فرمان زیر مفسر را ترک کنید: `quit()`.

ویژگی‌های ویرایش خط مفسر شامل ویرایش تعاملی، جایگزینی تاریخچه و تکمیل کد در سیستم‌هایی است که از کتابخانه [GNU Readline](https://tiswww.case.edu/php/chet/readline/rltop.html) پشتیبانی می‌کنند. شاید سریع‌ترین راه برای بررسی اینکه آیا ویرایش خط فرمان پشتیبانی می‌شود یا نه، این باشد که `Control-P` را در اولین پروپمت پایتون که دریافت می‌کنید، تایپ کنید. اگر صدای بوق ایجاد شود، به این معنی است که ویرایش خط فرمان فعال است؛ به پیوست [ویرایش ورودی تعاملی و جایگزینی تاریخچه برای آشنایی با کلیدها](https://docs.python.org/3/tutorial/interactive.html#tut-interacting) مراجعه کنید. اگر هیچ اتفاقی نیفتد یا `^P‍‍` بازتاب شود، به این معنی است که ویرایش خط فرمان در دسترس نیست؛ در این صورت تنها می‌توانید از کلید حذف (Backspace) برای حذف کاراکترها از خط فعلی استفاده کنید.

مفسر به‌طور مشابهی مانند شل یونیکس عمل می‌کند: زمانی که با ورودی استاندارد متصل به یک دستگاه tty فراخوانی می‌شود، به‌صورت تعاملی دستورات را می‌خواند و اجرا می‌کند؛ و زمانی که با یک آرگومان نام فایل یا با یک فایل به‌عنوان ورودی استاندارد فراخوانی می‌شود، یک اسکریپت را از آن فایل می‌خواند و اجرا می‌کند.

روش دوم شروع مفسر استفاده از دستور`python -c command [arg] ...` است که بیانیه‌های موجود در command را اجرا می‌کند و مشابه گزینه [-c](https://docs.python.org/3/using/cmdline.html#cmdoption-c) در شل است. از آنجا که دستورات پایتون معمولاً شامل فضاها یا کاراکترهای دیگری هستند که برای شل خاص هستند، معمولاً توصیه می‌شود که کل command را در داخل کوتیشن قرار دهید.

برخی از ماژول‌های پایتون به عنوان اسکریپت نیز مفید هستند. این ماژول‌ها می‌توانند با استفاده از دستور `python -m module [arg] ...` فراخوانی شوند، که فایل منبع ماژول را به گونه‌ای اجرا می‌کند که گویی نام کامل آن را در خط فرمان نوشته‌اید.

هنگامی که از یک فایل اسکریپت استفاده می‌شود، گاهی اوقات مفید است که بتوانید اسکریپت را اجرا کرده و سپس به حالت تعاملی بروید. این کار می‌تواند با قرار دادن `-i` قبل از اسکریپت انجام شود.

تمام گزینه‌های خط فرمان در بخش "[خط فرمان و محیط](https://docs.python.org/3/using/cmdline.html#using-on-general)" توضیح داده شده‌اند.

## 2.1.1. انتقال آرگومان‌ها

زمانی که نام اسکریپت و آرگومان‌های اضافی به مفسر شناخته می‌شوند، این موارد به یک لیست از رشته‌ها تبدیل شده و به متغیر `argv` در ماژول `sys` اختصاص داده می‌شوند. شما می‌توانید به این لیست با اجرای `import sys` دسترسی پیدا کنید. طول این لیست حداقل یک است؛ وقتی هیچ اسکریپت و هیچ آرگومانی داده نشود، `sys.argv[0]` یک رشته خالی خواهد بود. زمانی که نام اسکریپت به عنوان `'-'` (به معنای ورودی استاندارد) داده می‌شود، `sys.argv[0]` به `'-'` تنظیم می‌شود. زمانی که از `-c command` استفاده می‌شود، `sys.argv[0]` به `'-c'` تنظیم می‌شود. زمانی که از `-m module` استفاده می‌شود، `sys.argv[0]` به نام کامل ماژول شناسایی شده تنظیم می‌شود. گزینه‌هایی که پس از `-c command` یا `-m module` پیدا می‌شوند، توسط پردازش گزینه‌های مفسر پایتون مصرف نمی‌شوند و در `sys.argv` باقی می‌مانند تا توسط فرمان یا ماژول مدیریت شوند.

## 2.1.2. حالت تعاملی

زمانی که دستورات از یک دستگاه tty خوانده می‌شوند، گفته می‌شود که مفسر در حالت تعاملی است. در این حالت، مفسر با پروپمت اولیه، که معمولاً شامل سه علامت بزرگتر از (`>>>`) است، برای دریافت فرمان بعدی درخواست می‌کند؛ برای خطوط ادامه‌دار، با پروپمت ثانویه که به‌طور پیش‌فرض شامل سه نقطه (`...`) است، درخواست می‌کند. مفسر قبل از نمایش اولین پروپمت، یک پیام خوش‌آمدگویی که شماره نسخه و یادداشت حق چاپ آن را اعلام می‌کند، چاپ می‌کند.

``` bash
$ python3.13
Python 3.13 (default, April 4 2023, 09:25:04)
[GCC 10.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

خطوط ادامه‌دار زمانی نیاز هستند که شما یک ساختار چندخطی را وارد می‌کنید. به عنوان مثال، به این عبارت شرطی if نگاه کنید:
``` bash
>>> the_world_is_flat = True
>>> if the_world_is_flat:
...     print("Be careful not to fall off!")
...
Be careful not to fall off!
```

برای اطلاعات بیشتر درباره حالت تعاملی، به [حالت تعاملی](https://docs.python.org/3/tutorial/appendix.html#tut-interac) مراجعه کنید.

# 2.2. مترجم و محیط آن

## 2.2.1. کدگذاری کد منبع

به طور پیش‌فرض، فایل‌های منبع پایتون به عنوان فایل‌های کدگذاری شده در UTF-8 در نظر گرفته می‌شوند. در این کدگذاری، کاراکترهای بیشتر زبان‌های دنیا می‌توانند به طور همزمان در رشته‌های متنی، شناسه‌ها و نظرات استفاده شوند — اگرچه کتابخانه استاندارد فقط از کاراکترهای ASCII برای شناسه‌ها استفاده می‌کند که یک قاعده است که هر کد قابل حملی باید از آن پیروی کند. برای نمایش صحیح همه این کاراکترها، ویرایشگر شما باید تشخیص دهد که فایل UTF-8 است و باید از فونتی استفاده کند که از همه کاراکترهای موجود در فایل پشتیبانی کند.

برای اعلام یک کدگذاری غیر از کدگذاری پیش‌فرض، باید یک خط نظر ویژه به عنوان اولین خط فایل اضافه شود. نحو آن به صورت زیر است:

```python
# -*- coding: encoding -*-
```

جایی که رمزگذاری یکی از [codecs](https://docs.python.org/3/library/codecs.html#module-codecs) های معتبر پشتیبانی شده توسط پایتون است.

به عنوان مثال، برای اعلام اینکه از کدگذاری Windows-1252 استفاده خواهد شد، اولین خط فایل کد منبع شما باید به صورت زیر باشد:

```python
# -*- coding: cp1252 -*-
```

یک استثنا برای قاعده خط اول زمانی است که کد منبع با یک خط "شبانگ" یونیکس شروع می‌شود. در این حالت، اعلام کدگذاری باید به عنوان خط دوم فایل اضافه شود. به عنوان مثال:

```python
#!/usr/bin/env python3
# -*- coding: cp1252 -*-
```

### پانویس‌ها

[^1]: در یونیکس، مفسر python 3.x به طور پیش فرض با فایل اجرایی به نام `python` نصب نشده است، به طوری که با یک فایل اجرایی python 2.x که به طور همزمان نصب شده است در تضاد نباشد.