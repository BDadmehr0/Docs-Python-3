# 5. ساختارهای داده

این فصل برخی از چیزهایی که قبلاً یاد گرفته‌اید را با جزئیات بیشتری توضیح می‌دهد و همچنین موارد جدیدی را نیز اضافه می‌کند.

## 5.1. اطلاعات بیشتر در مورد لیست‌ها 

نوع داده لیست تعدادی متدهای بیشتری دارد. در اینجا تمام متدهای مربوط به اشیاء لیست آمده است:

**list.append(x)**  

یک آیتم را به انتهای لیست اضافه می‌کند. معادل است با `a[len(a):] = [x]`.

**list.extend(iterable)**  

لیست را با افزودن تمام آیتم‌های قابل پیمایش (iterable) گسترش می‌دهد. معادل است با `a[len(a):] = iterable`.

**list.insert(i, x)**  

یک آیتم را در موقعیت مشخص‌شده قرار می‌دهد. اولین آرگومان اندیس عنصری است که قبل از آن باید درج شود، بنابراین `a.insert(0, x)` آیتم را در ابتدای لیست درج می‌کند و `a.insert(len(a), x)` معادل با `a.append(x)` است.

**list.remove(x)**  

اولین آیتمی که مقدار آن برابر با x باشد را از لیست حذف می‌کند. اگر چنین آیتمی وجود نداشته باشد، خطای [ValueError](https://docs.python.org/3/library/exceptions.html#ValueError) ایجاد می‌شود.

**list.pop([i])**  

آیتم موجود در موقعیت مشخص‌شده را از لیست حذف کرده و آن را برمی‌گرداند. اگر اندیسی مشخص نشود، `a.pop()` آخرین آیتم لیست را حذف کرده و برمی‌گرداند. اگر لیست خالی باشد یا اندیس خارج از محدوده باشد، خطای [IndexError](https://docs.python.org/3/library/exceptions.html#IndexError) رخ می‌دهد.

**list.clear()**  

همه آیتم‌های لیست را حذف می‌کند. معادل با `del a[:]`.

**list.index(x[, start[, end]])**  

اندیس اولین آیتمی که مقدار آن برابر با x باشد را بازمی‌گرداند. اگر چنین آیتمی وجود نداشته باشد، خطای [ValueError](https://docs.python.org/3/library/exceptions.html#ValueError) رخ می‌دهد.

آرگومان‌های اختیاری `start` و `end` مشابه با نحو برش (slice notation) تفسیر می‌شوند و برای محدود کردن جستجو به زیرمجموعه‌ای از لیست استفاده می‌شوند. اندیس بازگشتی نسبت به ابتدای دنباله کامل محاسبه می‌شود و نه آرگومان `start`.

**list.count(x)**  

تعداد دفعاتی که x در لیست ظاهر شده را بازمی‌گرداند.

**list.sort(*, key=None, reverse=False)**  

آیتم‌های لیست را به صورت محلی مرتب می‌کند (آرگومان‌ها می‌توانند برای سفارشی‌سازی مرتب‌سازی استفاده شوند، برای توضیح آن‌ها به تابع [sorted()](https://docs.python.org/3/library/functions.html#sorted) مراجعه کنید).

**list.reverse()**  

عناصر لیست را به صورت محلی معکوس می‌کند.

**list.copy()**  

یک نسخه سطحی (shallow copy) از لیست را بازمی‌گرداند. معادل با `a[:]`.

مثالی که از اکثر متدهای لیست استفاده می کند:
``` python
>>> fruits = ['orange', 'apple', 'pear', 'banana', 'kiwi', 'apple', 'banana']
>>> fruits.count('apple')
2
>>> fruits.count('tangerine')
0
>>> fruits.index('banana')
3
>>> fruits.index('banana', 4)  # Find next banana starting at position 4
6
>>> fruits.reverse()
>>> fruits
['banana', 'apple', 'kiwi', 'banana', 'pear', 'apple', 'orange']
>>> fruits.append('grape')
>>> fruits
['banana', 'apple', 'kiwi', 'banana', 'pear', 'apple', 'orange', 'grape']
>>> fruits.sort()
>>> fruits
['apple', 'apple', 'banana', 'banana', 'grape', 'kiwi', 'orange', 'pear']
>>> fruits.pop()
'pear'
```

ممکن است متوجه شده باشید که متدهایی مانند `insert`، `remove` یا `sort` که فقط لیست را تغییر می‌دهند، هیچ مقدار بازگشتی چاپ نمی‌کنند – این متدها مقدار پیش‌فرض `None` را بازمی‌گردانند. [1^] این یک اصل طراحی برای تمام ساختارهای داده قابل تغییر (mutable) در پایتون است.

چیز دیگری که ممکن است متوجه شوید این است که همه داده‌ها قابل مرتب‌سازی یا مقایسه نیستند. به عنوان مثال، `[None, 'hello', 10]` قابل مرتب‌سازی نیست، زیرا اعداد صحیح قابل مقایسه با رشته‌ها نیستند و `None` نیز با دیگر نوع‌ها قابل مقایسه نیست. همچنین، برخی از نوع‌ها رابطه ترتیبی تعریف‌شده‌ای ندارند. به عنوان مثال، مقایسه `3+4j < 5+7j` معتبر نیست.

### 5.1.1. استفاده از لیست‌ها به‌عنوان پشته‌ها

متدهای لیست استفاده از لیست به عنوان یک پشته (stack) را بسیار آسان می‌کنند، جایی که آخرین عنصر اضافه شده اولین عنصری است که بازیابی می‌شود ("آخرین ورودی، اولین خروجی"). برای اضافه کردن یک آیتم به بالای پشته از `append()` استفاده کنید. برای بازیابی یک آیتم از بالای پشته، از `pop()` بدون مشخص کردن اندیس استفاده کنید. برای مثال:

``` python
>>> stack = [3, 4, 5]
>>> stack.append(6)
>>> stack.append(7)
>>> stack
[3, 4, 5, 6, 7]
>>> stack.pop()
7
>>> stack
[3, 4, 5, 6]
>>> stack.pop()
6
>>> stack.pop()
5
>>> stack
[3, 4]
```

### 5.1.2. استفاده از لیست‌ها به‌عنوان صف‌ها

همچنین می‌توان از لیست به عنوان یک صف (queue) استفاده کرد، جایی که اولین عنصر اضافه شده، اولین عنصری است که بازیابی می‌شود ("اولین ورودی، اولین خروجی"). با این حال، لیست‌ها برای این منظور کارآمد نیستند. در حالی که افزودن و حذف عناصر از انتهای لیست سریع است، انجام عملیات درج یا حذف از ابتدای لیست کند است (زیرا تمام عناصر دیگر باید به اندازه یک واحد جابه‌جا شوند).

برای پیاده‌سازی یک صف، از [collections.deque](https://docs.python.org/3/library/collections.html#collections.deque) استفاده کنید که برای افزودن و حذف سریع از هر دو طرف طراحی شده است. به عنوان مثال:

``` python
>>> from collections import deque
>>> queue = deque(["Eric", "John", "Michael"])
>>> queue.append("Terry")           # Terry arrives
>>> queue.append("Graham")          # Graham arrives
>>> queue.popleft()                 # The first to arrive now leaves
'Eric'
>>> queue.popleft()                 # The second to arrive now leaves
'John'
>>> queue                           # Remaining queue in order of arrival
deque(['Michael', 'Terry', 'Graham'])
```

### 5.1.3. درک لیست‌ها

تعبیرهای لیستی (List comprehensions) روشی مختصر برای ایجاد لیست‌ها ارائه می‌دهند. کاربردهای رایج آن‌ها شامل ایجاد لیست‌های جدید است که در آن هر عنصر نتیجه عملیاتی است که بر روی هر عضو از یک دنباله یا قابل پیمایش (iterable) دیگر اعمال شده است، یا ایجاد زیرمجموعه‌ای از عناصری که شرایط خاصی را برآورده می‌کنند.

به عنوان مثال، فرض کنید می‌خواهیم لیستی از مربعات اعداد ایجاد کنیم، مانند:

``` python
>>> squares = []
>>> for x in range(10):
...     squares.append(x**2)
...
>>> squares
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

توجه داشته باشید که این کد یک متغیر به نام `x` ایجاد می‌کند (یا آن را بازنویسی می‌کند) که پس از اتمام حلقه هنوز وجود دارد. می‌توانیم لیست مربعات را بدون هیچ گونه اثر جانبی محاسبه کنیم با استفاده از:

``` python
squares = list(map(lambda x: x**2, range(10)))
```

یا به طور معادل:

``` python
squares = [x**2 for x in range(10)]
```

که این روش مختصرتر و خواناتر است.

یک تعبیر لیستی (list comprehension) شامل براکت‌هایی است که یک عبارت را در خود دارند و پس از آن یک جمله `for`، و سپس صفر یا چند جمله `for` یا `if` قرار می‌گیرد. نتیجه یک لیست جدید خواهد بود که از ارزیابی عبارت در زمینه جملات `for` و `if` که پس از آن آمده‌اند، به دست می‌آید. به عنوان مثال، این تعبیر لیستی (listcomp) عناصری از دو لیست را ترکیب می‌کند اگر آن‌ها برابر نباشند:

``` python
>>> [(x, y) for x in [1,2,3] for y in [3,1,4] if x != y]
[(1, 3), (1, 4), (2, 3), (2, 1), (2, 4), (3, 1), (3, 4)]
```

و معادل با:

``` python
>>> combs = []
>>> for x in [1,2,3]:
...     for y in [3,1,4]:
...         if x != y:
...             combs.append((x, y))
...
>>> combs
[(1, 3), (1, 4), (2, 3), (2, 1), (2, 4), (3, 1), (3, 4)]
```

به ترتیب جملات [for](https://docs.python.org/3/reference/compound_stmts.html#for) و [if](https://docs.python.org/3/reference/compound_stmts.html#if) در هر دو کد توجه کنید که یکسان است.

اگر عبارت یک زوج مرتب (tuple) باشد (به عنوان مثال، `(x, y)` در مثال قبلی)، باید در پرانتز قرار گیرد.

``` python
>>> vec = [-4, -2, 0, 2, 4]
>>> # create a new list with the values doubled
>>> [x*2 for x in vec]
[-8, -4, 0, 4, 8]
>>> # filter the list to exclude negative numbers
>>> [x for x in vec if x >= 0]
[0, 2, 4]
>>> # apply a function to all the elements
>>> [abs(x) for x in vec]
[4, 2, 0, 2, 4]
>>> # call a method on each element
>>> freshfruit = ['  banana', '  loganberry ', 'passion fruit  ']
>>> [weapon.strip() for weapon in freshfruit]
['banana', 'loganberry', 'passion fruit']
>>> # create a list of 2-tuples like (number, square)
>>> [(x, x**2) for x in range(6)]
[(0, 0), (1, 1), (2, 4), (3, 9), (4, 16), (5, 25)]
>>> # the tuple must be parenthesized, otherwise an error is raised
>>> [x, x**2 for x in range(6)]
  File "<stdin>", line 1
    [x, x**2 for x in range(6)]
     ^^^^^^^
SyntaxError: did you forget parentheses around the comprehension target?
>>> # flatten a list using a listcomp with two 'for'
>>> vec = [[1,2,3], [4,5,6], [7,8,9]]
>>> [num for elem in vec for num in elem]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

تعبیرهای لیستی می‌توانند شامل عبارات پیچیده و توابع تو در تو باشند:

``` python
>>> from math import pi
>>> [str(round(pi, i)) for i in range(1, 6)]
['3.1', '3.14', '3.142', '3.1416', '3.14159']
```

### 5.1.4. درک لیست‌های تو در تو

عبارت اولیه در یک تعبیر لیستی می‌تواند هر عبارت دلخواهی باشد، از جمله یک تعبیر لیستی دیگر.

به مثال زیر از یک ماتریس ۳ در ۴ توجه کنید که به عنوان یک لیست از ۳ لیست با طول ۴ پیاده‌سازی شده است:

``` python
>>> matrix = [
...     [1, 2, 3, 4],
...     [5, 6, 7, 8],
...     [9, 10, 11, 12],
... ]
```

تعبیر لیستی زیر ردیف‌ها و ستون‌ها را جابجا (ترانهاده) می‌کند:

``` python
>>> [[row[i] for row in matrix] for i in range(4)]
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
```

همان‌طور که در بخش قبلی مشاهده کردیم، تعبیر لیستی درونی در زمینه جملۀ [for](https://docs.python.org/3/reference/compound_stmts.html#for) که پس از آن آمده است، ارزیابی می‌شود، بنابراین این مثال معادل با:

``` python
>>> transposed = []
>>> for i in range(4):
...     transposed.append([row[i] for row in matrix])
...
transposed
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
```

که به نوبه خود، معادل با:

``` python
>>> transposed = []
>>> for i in range(4):
...    # the following 3 lines implement the nested listcomp
...     transposed_row = []
...     for row in matrix:
...         transposed_row.append(row[i])
...     transposed.append(transposed_row)
...
>>> transposed
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
```

در دنیای واقعی، باید به جای استفاده از عبارات کنترلی پیچیده، از توابع داخلی استفاده کنید. تابع [zip()](https://docs.python.org/3/library/functions.html#zip) برای این مورد بسیار مناسب است:

``` python
>>> list(zip(*matrix))
[(1, 5, 9), (2, 6, 10), (3, 7, 11), (4, 8, 12)]
```

برای جزئیات بیشتر در مورد ستاره (*) در این خط، به بخش "[Unpacking Argument Lists](https://docs.python.org/3/tutorial/controlflow.html#tut-unpacking-arguments)" مراجعه کنید.

