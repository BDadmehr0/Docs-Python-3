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


## 4.2 عبارات for

عبارت [for](https://docs.python.org/3/reference/compound_stmts.html#for) در پایتون کمی با آنچه ممکن است در زبان‌هایی مانند C یا Pascal به آن عادت داشته باشید، متفاوت است. به جای اینکه همیشه بر روی یک پیشرفت حسابی از اعداد تکرار کند (مانند Pascal)، یا به کاربر امکان تعریف گام تکرار و شرط توقف را بدهد (مانند C)، عبارت **for** در پایتون بر روی آیتم‌های هر دنباله‌ای (مانند لیست یا رشته) به ترتیبی که در دنباله ظاهر می‌شوند، تکرار می‌کند. برای مثال: (بدون قصد بازی با کلمات).

``` python
>>> # Measure some strings:
>>> words = ['cat', 'window', 'defenestrate']
>>> for w in words:
...     print(w, len(w))
...
cat 3
window 6
defenestrate 12
```

کدی که یک مجموعه را هنگام تکرار روی همان مجموعه تغییر می‌دهد، ممکن است دشوار باشد که به درستی نوشته شود. به جای آن، معمولاً ساده‌تر است که روی یک کپی از مجموعه تکرار کنید یا یک مجموعه جدید ایجاد کنید:

``` python
# Create a sample collection
users = {'Hans': 'active', 'Éléonore': 'inactive', '景太郎': 'active'}

# Strategy:  Iterate over a copy
for user, status in users.copy().items():
    if status == 'inactive':
        del users[user]

# Strategy:  Create a new collection
active_users = {}
for user, status in users.items():
    if status == 'active':
        active_users[user] = status
```

## 4.3. تابع [()range](https://docs.python.org/3/library/stdtypes.html#range)

اگر نیاز دارید که بر روی دنباله‌ای از اعداد تکرار کنید، تابع داخلی [()range](https://docs.python.org/3/library/stdtypes.html#range) به کارتان می‌آید. این تابع پیشرفت‌های حسابی را تولید می‌کند:
``` python
>>> for i in range(5):
...     print(i)
...
0
1
2
3
4
```

نقطه انتهایی داده شده هرگز بخشی از دنباله تولید شده نیست؛ `range(10)` ده مقدار تولید می‌کند که شاخص‌های قانونی برای آیتم‌های یک دنباله به طول 10 هستند. این امکان وجود دارد که بازه از یک عدد دیگر شروع شود یا افزایش (حتی منفی؛ که گاهی "گام" نامیده می‌شود) دیگری را مشخص کنید:

``` python
>>> list(range(5, 10))
[5, 6, 7, 8, 9]
>>> list(range(0, 10, 3))
[0, 3, 6, 9]
>>> list(range(-10, -100, -30))
[-10, -40, -70]
```

برای تکرار بر روی شاخص‌های یک دنباله، می‌توانید [()range](https://docs.python.org/3/library/stdtypes.html#range) را با [()len](https://docs.python.org/3/library/functions.html#len) به این صورت ترکیب کنید:
``` python
>>> a = ['Mary', 'had', 'a', 'little', 'lamb']
>>> for i in range(len(a)):
...     print(i, a[i])
...
0 Mary
1 had
2 a
3 little
4 lamb
```

در بیشتر چنین مواردی، استفاده از تابع [()enumerate](https://docs.python.org/3/library/functions.html#enumerate) که در بخش **[تکنیک‌های حلقه‌زنی](https://docs.python.org/3/tutorial/datastructures.html#tut-loopidioms)** توضیح داده می‌شود، راحت‌تر است.

یک اتفاق عجیب رخ می‌دهد اگر فقط یک بازه را چاپ کنید:

```python
range(10)
range(0, 10)
```

در بسیاری از موارد، شیء بازگشتی از [()range](https://docs.python.org/3/library/stdtypes.html#range) مانند یک لیست رفتار می‌کند، اما در واقع این‌طور نیست. این یک شیء است که آیتم‌های متوالی دنباله مورد نظر را زمانی که روی آن تکرار می‌کنید برمی‌گرداند، اما لیست واقعی را نمی‌سازد، بنابراین در فضا صرفه‌جویی می‌کند.

ما به چنین شیئی می‌گوییم **[iterable](https://docs.python.org/3/glossary.html#term-iterable)** (قابل پیمایش)، یعنی مناسب به عنوان هدف برای توابع و ساختارهایی که انتظار دارند چیزی که می‌توانند از آن آیتم‌های متوالی را دریافت کنند تا زمانی که تمام شوند. ما قبلاً دیده‌ایم که دستور **[for](https://docs.python.org/3/reference/compound_stmts.html#for)** چنین ساختاری است، در حالی که مثالی از تابعی که یک iterable می‌گیرد، تابع [()sum](https://docs.python.org/3/library/functions.html#sum) است:

```python
sum(range(4))  # 0 + 1 + 2 + 3
6
```

بعداً توابع بیشتری خواهیم دید که iterableها را برمی‌گردانند و iterableها را به عنوان آرگومان‌ها می‌پذیرند. در فصل **[ساختارهای داده](https://docs.python.org/3/tutorial/datastructures.html#tut-structures)**، در مورد [()list](https://docs.python.org/3/library/stdtypes.html#list) به تفصیل بیشتری بحث خواهیم کرد.


https://docs.python.org/3/tutorial/controlflow.html#break-and-continue-statements
