# 4. ابزارهای بیشتر برای کنترل جریان 

بر عبارت [while](https://docs.python.org/3/reference/compound_stmts.html#while) که به تازگی معرفی شد، پایتون از چند عبارت دیگر نیز استفاده می‌کند که در این فصل با آن‌ها روبه‌رو خواهیم شد.

## 4.1. عبارات if

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


## 4.2. عبارات for

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


## 4.4. عبارات break و continue

دستور ‌[break](https://docs.python.org/3/reference/simple_stmts.html#break) از درونی‌ترین حلقه‌ی ‌[for](https://docs.python.org/3/reference/compound_stmts.html#for) یا ‌[while](https://docs.python.org/3/reference/compound_stmts.html#while) خارج می‌شود:

``` python
>>> for n in range(2, 10):
...     for x in range(2, n):
...         if n % x == 0:
...             print(f"{n} equals {x} * {n//x}")
...             break
...
4 equals 2 * 2
6 equals 2 * 3
8 equals 2 * 4
9 equals 3 * 3
```

دستور ‌[continue](https://docs.python.org/3/reference/simple_stmts.html#continue) با تکرار بعدی حلقه ادامه می‌دهد:

``` python
>>> for num in range(2, 10):
...     if num % 2 == 0:
...         print(f"Found an even number {num}")
...         continue
...     print(f"Found an odd number {num}")
...
Found an even number 2
Found an odd number 3
Found an even number 4
Found an odd number 5
Found an even number 6
Found an odd number 7
Found an even number 8
Found an odd number 9
```

## 4.5. عبارات else در حلقه‌ها

در یک حلقه ‌`for` یا ‌`while`، دستور ‌`break` ممکن است با یک بخش ‌`else` همراه شود. اگر حلقه بدون اجرای ‌`break` به پایان برسد، بخش ‌`else` اجرا می‌شود.

در حلقه ‌[for](https://docs.python.org/3/reference/compound_stmts.html#for)، بخش ‌`else` بعد از اتمام آخرین تکرار حلقه اجرا می‌شود، یعنی در صورتی که هیچ ‌`break` رخ نداده باشد.

در حلقه ‌[while](https://docs.python.org/3/reference/compound_stmts.html#while)، این بخش بعد از اینکه شرط حلقه نادرست شد، اجرا می‌شود.

در هر نوع حلقه‌ای، بخش ‌`else` در صورتی اجرا نمی‌شود که حلقه با ‌[break](https://docs.python.org/3/reference/simple_stmts.html#break) متوقف شده باشد. به طور طبیعی، سایر روش‌های خاتمه دادن زودهنگام حلقه مانند استفاده از ‌[return](https://docs.python.org/3/reference/simple_stmts.html#return) یا رخ دادن یک استثنا (exception)، باعث می‌شود که بخش ‌[else](https://docs.python.org/3/reference/compound_stmts.html#else) نیز اجرا نشود.

این موضوع در مثال زیر با یک حلقه ‌`for` که به دنبال اعداد اول می‌گردد، نشان داده شده است:

``` python
>>> for n in range(2, 10):
...     for x in range(2, n):
...         if n % x == 0:
...             print(n, 'equals', x, '*', n//x)
...             break
...     else:
...         # loop fell through without finding a factor
...         print(n, 'is a prime number')
...
2 is a prime number
3 is a prime number
4 equals 2 * 2
5 is a prime number
6 equals 2 * 3
7 is a prime number
8 equals 2 * 4
9 equals 3 * 3
```

ترجمه:

(بله، این کد درست است. دقت کنید: بخش ‌`else` مربوط به حلقه ‌`for` است، نه دستور ‌`if`.)

یکی از روش‌های فکر کردن به بخش ‌`else` این است که آن را در کنار دستور ‌`if` درون حلقه تصور کنید. زمانی که حلقه اجرا می‌شود، توالی‌ای مانند ‌`if/if/if/else` را اجرا می‌کند. دستور ‌`if` درون حلقه قرار دارد و چندین بار با آن برخورد می‌شود. اگر شرط ‌`if` در هر زمانی درست باشد، دستور ‌`break` اجرا می‌شود. اگر شرط هیچ‌گاه درست نباشد، بخش ‌`else` خارج از حلقه اجرا می‌شود.

هنگامی که از بخش ‌`else` در کنار یک حلقه استفاده می‌شود، این بخش بیشتر به بخش ‌`else` در دستور ‌[try](https://docs.python.org/3/reference/compound_stmts.html#try) شباهت دارد تا به بخش ‌`else` در دستور ‌`if`: بخش ‌`else` در یک دستور ‌`try` زمانی اجرا می‌شود که هیچ استثنایی رخ ندهد و بخش ‌`else` در یک حلقه زمانی اجرا می‌شود که هیچ ‌`break` اتفاق نیفتد. برای اطلاعات بیشتر در مورد دستور ‌`try` و استثناها، به بخش "[مدیریت استثناها](https://docs.python.org/3/tutorial/errors.html#tut-handling)" مراجعه کنید.


## 4.6. عبارات pass

دستور `pass` هیچ کاری انجام نمی‌دهد. از آن می‌توان زمانی استفاده کرد که از نظر دستوری به یک دستور نیاز است، اما برنامه به هیچ اقدامی نیاز ندارد. برای مثال:

``` python
>>> while True:
...     pass  # Busy-wait for keyboard interrupt (Ctrl+C)
...
```

این معمولاً برای ایجاد کلاس‌های حداقلی استفاده می‌شود:

``` python
>>> class MyEmptyClass:
...    pass
...
```

محل دیگری که می‌توان از [pass](https://docs.python.org/3/reference/simple_stmts.html#pass) استفاده کرد، به‌عنوان جایگزینی موقت برای بدنه‌ی یک تابع یا شرط است، زمانی که در حال کار روی کد جدید هستید و می‌خواهید به فکر در سطحی انتزاعی‌تر ادامه دهید. دستور `pass` به‌صورت بی‌صدا نادیده گرفته می‌شود.


``` python
>>> def initlog(*args):
...     pass   # Remember to implement this!
...
```

## 4.7. عبارات match
ترجمه:

یک دستور ‌[match](https://docs.python.org/3/reference/compound_stmts.html#match) یک عبارت را می‌گیرد و مقدار آن را با الگوهای متوالی که به‌صورت یک یا چند بلوک ‌`case` داده شده‌اند، مقایسه می‌کند. این از نظر ظاهری شبیه به دستور ‌`switch` در زبان‌هایی مانند C، جاوا یا جاوااسکریپت (و بسیاری دیگر از زبان‌ها) است، اما بیشتر به تطابق الگو (pattern matching) در زبان‌هایی مانند Rust یا Haskell شباهت دارد. تنها اولین الگویی که مطابقت داشته باشد، اجرا می‌شود و همچنین می‌تواند اجزا (عناصر یک دنباله یا ویژگی‌های یک شیء) را از مقدار به متغیرها استخراج کند.

ساده‌ترین شکل آن، یک مقدار موضوعی را با یک یا چند مقدار ثابت مقایسه می‌کند:

``` python
def http_error(status):
    match status:
        case 400:
            return "Bad request"
        case 404:
            return "Not found"
        case 418:
            return "I'm a teapot"
        case _:
            return "Something's wrong with the internet"
```

به بلوک آخر توجه کنید: نام متغیر `_` به‌عنوان یک کاراکتر wildcard عمل می‌کند و هرگز در مطابقت شکست نمی‌خورد. اگر هیچ کدام از حالات مطابقت نداشته باشد، هیچ‌کدام از شاخه‌ها اجرا نمی‌شود.

شما می‌توانید چندین مقدار ثابت را در یک الگوی واحد با استفاده از `|` (عملگر "یا") ترکیب کنید:

``` python
case 401 | 403 | 404:
    return "Not allowed"
```

الگوها می‌توانند شبیه انتساب‌های unpacking به نظر برسند و می‌توانند برای متصل کردن متغیرها استفاده شوند:

``` python
# point is an (x, y) tuple
match point:
    case (0, 0):
        print("Origin")
    case (0, y):
        print(f"Y={y}")
    case (x, 0):
        print(f"X={x}")
    case (x, y):
        print(f"X={x}, Y={y}")
    case _:
        raise ValueError("Not a point")
```

آن را با دقت مطالعه کنید! الگوی اول دارای دو مقدار ثابت است و می‌توان آن را به‌عنوان گسترشی از الگوی ثابت نشان‌داده‌شده در بالا در نظر گرفت. اما دو الگوی بعدی یک مقدار ثابت و یک متغیر را ترکیب می‌کنند، و متغیر مقداری را از موضوع (`point`) متصل می‌کند. الگوی چهارم دو مقدار را ضبط می‌کند که از نظر مفهومی مشابه انتساب `unpacking (x, y) = point` است.

اگر از کلاس‌ها برای ساختاردهی داده‌های خود استفاده می‌کنید، می‌توانید از نام کلاس به‌همراه یک لیست آرگومان شبیه به یک سازنده استفاده کنید، اما با قابلیت ضبط ویژگی‌ها در متغیرها:

``` python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

def where_is(point):
    match point:
        case Point(x=0, y=0):
            print("Origin")
        case Point(x=0, y=y):
            print(f"Y={y}")
        case Point(x=x, y=0):
            print(f"X={x}")
        case Point():
            print("Somewhere else")
        case _:
            print("Not a point")
```

می‌توانید از پارامترهای موقعیتی با برخی از کلاس‌های داخلی که برای ویژگی‌های خود ترتیبی ارائه می‌دهند (مثلاً `dataclass`‌ها) استفاده کنید. همچنین می‌توانید با تنظیم ویژگی ویژه‌ی `__match_args__` در کلاس‌های خود، موقعیت خاصی برای ویژگی‌ها در الگوها تعریف کنید. اگر این ویژگی به ("x"، "y") تنظیم شود، الگوهای زیر همگی معادل خواهند بود (و همگی ویژگی ‍`y` را به متغیر `var` متصل می‌کنند):


``` python
Point(1, var)
Point(1, y=var)
Point(x=1, y=var)
Point(y=var, x=1)
```

یک روش پیشنهادی برای خواندن الگوها این است که به آنها به‌عنوان شکلی گسترده از آنچه در سمت چپ یک انتساب قرار می‌دهید نگاه کنید، تا بفهمید کدام متغیرها به چه چیزی اختصاص داده می‌شوند. تنها نام‌های مستقل (مانند `var` در مثال بالا) توسط دستور ‌`match` مقداردهی می‌شوند. نام‌های نقطه‌گذاری‌شده (مانند `foo.bar`)، نام ویژگی‌ها (مانند `x=` و `y=` در مثال بالا) یا نام کلاس‌ها (که با “(…)” کنار آنها مانند `Point` در مثال بالا شناخته می‌شوند) هرگز مقداردهی نمی‌شوند.

الگوها می‌توانند به‌صورت دلخواه تودرتو باشند. برای مثال، اگر یک لیست کوتاه از نقاط (Points) داشته باشیم که ویژگی `__match_args__` به آن اضافه شده باشد، می‌توانیم به این صورت آن را مطابقت دهیم:

``` python
class Point:
    __match_args__ = ('x', 'y')
    def __init__(self, x, y):
        self.x = x
        self.y = y

match points:
    case []:
        print("No points")
    case [Point(0, 0)]:
        print("The origin")
    case [Point(x, y)]:
        print(f"Single point {x}, {y}")
    case [Point(0, y1), Point(0, y2)]:
        print(f"Two on the Y axis at {y1}, {y2}")
    case _:
        print("Something else")
```

ما می‌توانیم یک بخش ‌`if` به یک الگو اضافه کنیم که به‌عنوان "محافظ" (guard) شناخته می‌شود. اگر محافظ نادرست باشد، ‌`match` به بررسی بلوک ‌`case` بعدی ادامه می‌دهد. توجه داشته باشید که مقداردهی (capture) متغیرها قبل از ارزیابی محافظ انجام می‌شود.

``` python
match point:
    case Point(x, y) if x == y:
        print(f"Y=X at {x}")
    case Point(x, y):
        print(f"Not on the diagonal")
```

چند ویژگی کلیدی دیگر این دستور:

- مانند انتساب‌های unpacking، الگوهای ‌`tuple` و ‌`list` دقیقاً معنای یکسانی دارند و عملاً با دنباله‌های دلخواه مطابقت می‌یابند. یک استثنای مهم این است که آنها با ‌`iterator`‌ها یا رشته‌ها مطابقت ندارند.
  
- الگوهای دنباله‌ای از unpacking گسترده پشتیبانی می‌کنند: `[x, y, *rest]` و `(x, y, *rest)` شبیه به انتساب‌های unpacking عمل می‌کنند. نامی که بعد از `*` می‌آید می‌تواند `_` باشد، بنابراین `(x, y, *_)` با دنباله‌ای از حداقل دو آیتم مطابقت می‌یابد بدون اینکه آیتم‌های باقی‌مانده را به متغیری متصل کند.

- الگوهای نگاشت: `{"bandwidth": b, "latency": l}` مقادیر "bandwidth" و "latency" را از یک دیکشنری استخراج می‌کند. برخلاف الگوهای دنباله‌ای، کلیدهای اضافی نادیده گرفته می‌شوند. یک unpacking مانند `**rest` نیز پشتیبانی می‌شود (اما `**_` اضافی است، بنابراین مجاز نیست).

- الگوهای فرعی را می‌توان با استفاده از کلیدواژه `as` استخراج کرد:
  
  ```python
  case (Point(x1, y1), Point(x2, y2) as p2): ...
  ```

  این کد عنصر دوم ورودی را به‌عنوان `p2` ضبط می‌کند (مشروط بر اینکه ورودی یک دنباله از دو نقطه باشد).

- بیشتر مقادیر ثابت با برابری مقایسه می‌شوند، اما ‌`True`، ‌`False` و ‌`None` با هویت مقایسه می‌شوند.

- الگوها می‌توانند از ثابت‌های نام‌گذاری‌شده استفاده کنند. این ثابت‌ها باید به‌صورت نام‌های نقطه‌گذاری‌شده (dotted names) باشند تا به‌عنوان متغیرهای capture تفسیر نشوند:

  ```python
  from enum import Enum
  class Color(Enum):
      RED = 'red'
      GREEN = 'green'
      BLUE = 'blue'

  color = Color(input("Enter your choice of 'red', 'blue' or 'green': "))

  match color:
      case Color.RED:
          print("I see red!")
      case Color.GREEN:
          print("Grass is green")
      case Color.BLUE:
          print("I'm feeling the blues :(")
  ```

برای توضیحات دقیق‌تر و مثال‌های بیشتر، می‌توانید به [PEP 636](https://peps.python.org/pep-0636/) مراجعه کنید که به‌صورت یک آموزش نوشته شده است.


https://docs.python.org/3/tutorial/controlflow.html#defining-functions
