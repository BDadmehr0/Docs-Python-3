# 4 ابزارهای بیشتر برای کنترل جریان 

بر عبارت [while](https://docs.python.org/3/reference/compound_stmts.html#while) که به تازگی معرفی شد، پایتون از چند عبارت دیگر نیز استفاده می‌کند که در این فصل با آن‌ها روبه‌رو خواهیم شد.

## 4.1 عبارات if

شاید شناخته‌شده‌ترین نوع عبارت، عبارت if باشد. برای مثال:

``` python
>>> x = int(input("Please enter an integer: "))
Please enter an integer: 42
>>> if x < 0:
...     x = 0
...     print('Negative changed to zero')
>>> elif x == 0:
...     print('Zero')
>>> elif x == 1:
...     print('Single')
>>> else:
...     print('More')
...
More
```

ممکن است هیچ یا چندین بخش [elif](https://docs.python.org/3/reference/compound_stmts.html#elif) وجود داشته باشد و بخش [else](https://docs.python.org/3/reference/compound_stmts.html#else) نیز اختیاری است. کلمه کلیدی «**elif**» کوتاه‌شده‌ی «**else if**» است و برای جلوگیری از تورفتگی بیش از حد مفید است. دنباله‌ای از **if** … **elif** … **elif** … جایگزینی برای عبارات `switch` یا `case` در زبان‌های دیگر است.

اگر در حال مقایسه‌ی یک مقدار با چند ثابت هستید یا در حال بررسی نوع‌ها یا ویژگی‌های خاصی هستید، ممکن است عبارت **match** نیز برای شما مفید باشد. برای جزئیات بیشتر به [عبارات match](https://docs.python.org/3/tutorial/controlflow.html#tut-match) مراجعه کنید.

