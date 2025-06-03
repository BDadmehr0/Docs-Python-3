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

در اینجا ترجمه فارسی بخش "Formatted String Literals" (رشته‌های قالب‌بندی‌شده یا f-strings) را می‌خوانید:

### ۷.۱.۱. رشته‌های قالب‌بندی‌شده (Formatted String Literals)

[رشته‌های قالب‌بندی‌شده](https://docs.python.org/3/reference/lexical_analysis.html#f-strings) (که به‌اختصار به آن‌ها f-string گفته می‌شود) به شما اجازه می‌دهند مقدار عبارات پایتون را درون یک رشته وارد کنید. این کار با پیشوند `f` یا `F` پیش از رشته و نوشتن عبارت‌ها در داخل `{expression}` انجام می‌شود.

می‌توانید پس از عبارت، یک مشخص‌کننده قالب (format specifier) اختیاری قرار دهید. این ویژگی امکان کنترل بیشتر بر نحوه نمایش مقدار را فراهم می‌کند. مثلاً مثال زیر عدد π را تا سه رقم اعشار گرد می‌کند:

```python
>>> import math
>>> print(f'The value of pi is approximately {math.pi:.3f}.')
The value of pi is approximately 3.142.
```

اگر عددی بعد از `:` قرار دهید، آن فیلد حداقل به اندازه تعداد مشخص‌شده کاراکتر خواهد بود. این قابلیت برای مرتب کردن ستون‌ها کاربرد دارد:

```python
>>> table = {'Sjoerd': 4127, 'Jack': 4098, 'Dcab': 7678}
>>> for name, phone in table.items():
...     print(f'{name:10} ==> {phone:10d}')
...
Sjoerd     ==>       4127
Jack       ==>       4098
Dcab       ==>       7678
```

می‌توانید از اصلاح‌کننده‌های دیگری نیز استفاده کنید تا مقدار پیش از قالب‌بندی به نوعی دیگر تبدیل شود. برای مثال:

* `!a` تابع [ascii()](https://docs.python.org/3/library/functions.html#ascii) را اعمال می‌کند،
* `!s` تابع [str()](https://docs.python.org/3/library/stdtypes.html#str) را اعمال می‌کند،
* `!r` تابع [repr()](https://docs.python.org/3/library/functions.html#repr) را اعمال می‌کند:

```python
>>> animals = 'eels'
>>> print(f'My hovercraft is full of {animals}.')
My hovercraft is full of eels.
>>> print(f'My hovercraft is full of {animals!r}.')
My hovercraft is full of 'eels'.
```

مشخص‌کننده `=` نیز وجود دارد که عبارت، علامت مساوی، و مقدار ارزیابی‌شده را چاپ می‌کند:

```python
>>> bugs = 'roaches'
>>> count = 13
>>> area = 'living room'
>>> print(f'Debugging {bugs=} {count=} {area=}')
Debugging bugs='roaches' count=13 area='living room'
```

برای اطلاعات بیشتر درباره [عبارت‌های خودمستند](https://docs.python.org/3/whatsnew/3.8.html#bpo-36817-whatsnew) (self-documenting expressions)، به بخش مربوطه مراجعه کنید. همچنین برای راهنمای کامل مشخص‌کننده‌های قالب، به [راهنمای مختصر زبان قالب‌بندی](https://docs.python.org/3/library/string.html#formatspec) (Format Specification Mini-Language) مراجعه کنید.

