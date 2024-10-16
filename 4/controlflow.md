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

