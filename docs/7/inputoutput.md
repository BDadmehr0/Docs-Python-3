# 7. ورودی و خروجی

چندین روش برای ارائه خروجی یک برنامه وجود دارد؛ داده‌ها می‌توانند به صورت قابل خواندن برای انسان چاپ شوند یا برای استفاده در آینده در یک فایل نوشته شوند. این فصل به برخی از این امکانات خواهد پرداخت.

## 7.1 فرمت‌بندی خروجی پیشرفته‌تر 

تا کنون با دو روش برای نوشتن مقادیر آشنا شده‌ایم: دستورات بیان (expression statements) و تابع [print()](https://docs.python.org/3/library/functions.html#print)‎. (روش سوم استفاده از متد ‎[write()‎](https://docs.python.org/3/library/io.html#io.TextIOBase.write) برای اشیای فایل است؛ فایل خروجی استاندارد را می‌توان به عنوان ‎`sys.stdout`‎ ارجاع داد. برای اطلاعات بیشتر به **مرجع کتابخانه** مراجعه کنید.)

اغلب، ممکن است بخواهید کنترل بیشتری بر فرمت‌بندی خروجی خود داشته باشید تا صرفاً چاپ مقادیر جدا شده با فاصله. چندین روش برای فرمت‌بندی خروجی وجود دارد:

- برای استفاده از **رشته‌های قالب‌بندی‌شده** ([formatted string literals](https://docs.python.org/3/tutorial/inputoutput.html#tut-f-strings))، رشته را با ‎`f`‎ یا ‎`F`‎ قبل از علامت نقل قول آغاز کنید. داخل این رشته، می‌توانید یک عبارت پایتونی را بین کاراکترهای ‎`{`‎ و ‎`}`‎ بنویسید که می‌تواند به متغیرها یا مقادیر ثابت اشاره کند.
``` python
>>> year = 2016
>>> event = 'Referendum'
>>> f'Results of the {year} {event}'
'Results of the 2016 Referendum'
```

- متد [‎str.format()‎](https://docs.python.org/3/library/stdtypes.html#str.format) برای رشته‌ها نیاز به تلاش بیشتری به صورت دستی دارد. همچنان از ‎`{`‎ و ‎`}`‎ برای مشخص کردن محل جایگزینی یک متغیر استفاده می‌کنید و می‌توانید دستورالعمل‌های دقیق‌تری برای فرمت‌دهی ارائه دهید، اما همچنین باید اطلاعاتی که قرار است فرمت شوند را به‌طور صریح فراهم کنید. در بلوک کد زیر دو مثال از چگونگی فرمت‌دهی متغیرها آورده شده است:

``` python
>>> yes_votes = 42_572_654
>>> total_votes = 85_705_149
>>> percentage = yes_votes / total_votes
>>> '{:-9} YES votes  {:2.2%}'.format(yes_votes, percentage)
' 42572654 YES votes  49.67%'
```

توجه کنید که چگونه مقادیر ‎`yes_votes`‎ با فاصله‌ها پر شده‌اند و علامت منفی فقط برای اعداد منفی نمایش داده می‌شود. این مثال همچنین درصد را که در عدد 100 ضرب شده است، با دو رقم اعشار و به همراه علامت درصد چاپ می‌کند (برای جزئیات بیشتر به **[زبان کوچک مشخصات قالب‌بندی](https://docs.python.org/3/library/string.html#formatspec)** مراجعه کنید).

- در نهایت، می‌توانید تمام مدیریت رشته‌ها را خودتان انجام دهید، با استفاده از عملیات برش (slicing) و الحاق (concatenation) رشته‌ها، هر نوع چیدمانی را که تصور کنید ایجاد کنید. نوع داده‌ی رشته دارای متدهایی است که عملیات مفیدی برای پر کردن رشته‌ها تا عرض مشخص یک ستون انجام می‌دهند.

وقتی نیازی به خروجی‌های پیچیده ندارید و فقط می‌خواهید نمایش سریعی از چند متغیر برای اهداف اشکال‌زدایی داشته باشید، می‌توانید هر مقداری را با استفاده از توابع ‎[repr()](https://docs.python.org/3/library/functions.html#repr)‎ یا ‎[str()‎](https://docs.python.org/3/library/functions.html#repr) به رشته تبدیل کنید.

تابع ‎[str()‎](https://docs.python.org/3/library/stdtypes.html#str) برای بازگرداندن نمایشی از مقادیر طراحی شده است که برای انسان به نسبت خوانا باشد، در حالی که ‎[repr()‎](https://docs.python.org/3/library/functions.html#repr) برای ایجاد نمایشی طراحی شده است که توسط مفسر پایتون قابل خواندن باشد (یا اگر سینتاکس معادل وجود نداشته باشد، منجر به خطای ‎[SyntaxError](https://docs.python.org/3/library/exceptions.html#SyntaxError)‎ می‌شود). برای اشیایی که نمایشی خاص برای انسان ندارند، ‎[str()](https://docs.python.org/3/library/stdtypes.html#str)‎ همان مقدار ‎[repr()](https://docs.python.org/3/library/functions.html#repr)‎ را بازمی‌گرداند. بسیاری از مقادیر، مانند اعداد یا ساختارهایی مانند لیست‌ها و دیکشنری‌ها، با استفاده از هر دو تابع نمایش یکسانی دارند. رشته‌ها (strings) به طور خاص دو نمایش متمایز دارند.

برخی مثال‌ها:

``` python
>>> s = 'Hello, world.'
>>> str(s)
'Hello, world.'
>>> repr(s)
"'Hello, world.'"
>>> str(1/7)
'0.14285714285714285'
>>> x = 10 * 3.25
>>> y = 200 * 200
>>> s = 'The value of x is ' + repr(x) + ', and y is ' + repr(y) + '...'
>>> print(s)
The value of x is 32.5, and y is 40000...
>>> # The repr() of a string adds string quotes and backslashes:
>>> hello = 'hello, world\n'
>>> hellos = repr(hello)
>>> print(hellos)
'hello, world\n'
>>> # The argument to repr() may be any Python object:
>>> repr((x, y, ('spam', 'eggs')))
"(32.5, 40000, ('spam', 'eggs'))"
```

ماژول [string](https://docs.python.org/3/library/string.html#module-string) شامل کلاسی به نام [Template](https://docs.python.org/3/library/string.html#string.Template) است که روشی دیگر برای جایگزینی مقادیر در رشته‌ها ارائه می‌دهد. در این روش، از نگهدارنده‌هایی (placeholders) مانند ‎`$X`‎ استفاده می‌شود و این نگهدارنده‌ها با مقادیر موجود در یک دیکشنری جایگزین می‌شوند. با این حال، این روش کنترل بسیار کمتری روی فرمت‌بندی خروجی در مقایسه با سایر روش‌ها فراهم می‌کند.

https://docs.python.org/3/tutorial/inputoutput.html#formatted-string-literals
