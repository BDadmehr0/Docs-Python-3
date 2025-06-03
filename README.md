# [آموزش پایتون](https://docs.python.org/3/tutorial/index.html)

پایتون یک زبان برنامه‌نویسی آسان برای یادگیری و قدرتمند است. این زبان دارای ساختارهای داده‌ای سطح بالا و کارآمد و رویکردی ساده اما مؤثر به برنامه‌نویسی شیءگرا است. نگارش زیبا و تایپ دینامیک پایتون، به همراه ماهیت تفسیرشده‌اش، آن را به زبانی ایده‌آل برای نوشتن اسکریپت و توسعه سریع برنامه‌ها در بسیاری از زمینه‌ها و بر روی اکثر پلتفرم‌ها تبدیل می‌کند.

مفسر پایتون و کتابخانه استاندارد گسترده آن به صورت رایگان به‌صورت کد منبع یا باینری برای تمام پلتفرم‌های اصلی از وب‌سایت پایتون به نشانی [https://www.python.org/](https://www.python.org/) در دسترس هستند و می‌توانند به‌راحتی توزیع شوند. همین وب‌سایت همچنین شامل توزیع‌ها و ارجاعاتی به بسیاری از ماژول‌ها، برنامه‌ها و ابزارهای رایگان شخص ثالث پایتون و مستندات اضافی است.

مفسر پایتون به‌راحتی با توابع و نوع‌های داده جدیدی که به زبان C یا C++ (یا دیگر زبان‌های قابل فراخوانی از C) پیاده‌سازی شده‌اند، قابل گسترش است. پایتون همچنین به‌عنوان یک زبان گسترش‌دهنده برای برنامه‌های قابل سفارشی‌سازی مناسب است.

این آموزش به‌طور غیررسمی خواننده را با مفاهیم و ویژگی‌های اصلی زبان و سیستم پایتون آشنا می‌کند. داشتن یک مفسر پایتون برای تجربه عملی مفید است، اما تمام مثال‌ها خودکفا هستند، بنابراین می‌توان این آموزش را به‌صورت آفلاین نیز مطالعه کرد.

برای توصیف اشیاء و ماژول‌های استاندارد، به «[کتابخانه استاندارد پایتون](https://docs.python.org/3/library/index.html#library-index)» مراجعه کنید. «[مرجع زبان پایتون](https://docs.python.org/3/reference/index.html#reference-index)» تعریف رسمی‌تری از زبان ارائه می‌دهد. برای نوشتن افزونه‌ها به زبان C یا C++، «[گسترش و جاسازی مفسر پایتون](https://docs.python.org/3/extending/index.html#extending-index)» و «[مرجع API پایتون/C](https://docs.python.org/3/c-api/index.html#c-api-index)» را مطالعه کنید. همچنین چندین کتاب وجود دارد که به‌طور عمیق به پایتون پرداخته‌اند.

این آموزش تلاش نمی‌کند که جامع باشد و هر ویژگی خاص یا حتی هر ویژگی رایج را پوشش دهد. در عوض، بسیاری از ویژگی‌های بارز پایتون را معرفی می‌کند و ایده خوبی از طعم و سبک این زبان به شما می‌دهد. پس از مطالعه این آموزش، شما قادر خواهید بود ماژول‌ها و برنامه‌های پایتون را بخوانید و بنویسید و آماده خواهید بود تا درباره ماژول‌های مختلف کتابخانه پایتون که در «[کتابخانه استاندارد پایتون](https://docs.python.org/3/library/index.html#library-index)» توصیف شده‌اند، بیشتر یاد بگیرید.

[فهرست واژه‌ها](https://docs.python.org/3/glossary.html#glossary) نیز ارزش مرور کردن دارد.

# فهرست مطالب

1. **[تحریک اشتیاق](https://github.com/BDadmehr0/Docs-Python-3/blob/main/1/appetite.md)**
1. **[استفاده از مفسر پایتون](https://github.com/BDadmehr0/Docs-Python-3/blob/main/2/interpreter.md)**
   - 2.1 **[فراخوانی مفسر](https://github.com/BDadmehr0/Docs-Python-3/blob/main/2/interpreter.md#21-%D9%81%D8%B1%D8%A7%D8%AE%D9%88%D8%A7%D9%86%DB%8C-%D9%85%D9%81%D8%B3%D8%B1)**
     - 2.1.1 **[انتقال آرگومان‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/2/interpreter.md#211-%D8%A7%D9%86%D8%AA%D9%82%D8%A7%D9%84-%D8%A2%D8%B1%DA%AF%D9%88%D9%85%D8%A7%D9%86%D9%87%D8%A7)**
     - 2.1.2 **[حالت تعاملی](https://github.com/BDadmehr0/Docs-Python-3/blob/main/2/interpreter.md#212-%D8%AD%D8%A7%D9%84%D8%AA-%D8%AA%D8%B9%D8%A7%D9%85%D9%84%DB%8C)**
   - 2.2 **[مترجم و محیط آن](https://github.com/BDadmehr0/Docs-Python-3/blob/main/2/interpreter.md#22-%D9%85%D8%AA%D8%B1%D8%AC%D9%85-%D9%88-%D9%85%D8%AD%DB%8C%D8%B7-%D8%A2%D9%86)**
     - 2.2.1 **[کدگذاری کد منبع](https://github.com/BDadmehr0/Docs-Python-3/blob/main/2/interpreter.md#22-%D9%85%D8%AA%D8%B1%D8%AC%D9%85-%D9%88-%D9%85%D8%AD%DB%8C%D8%B7-%D8%A2%D9%86)**
1. **[آشنایی غیررسمی با پایتون](https://github.com/BDadmehr0/Docs-Python-3/blob/main/3%2Fintroduction.md)**
   - 3.1 **[استفاده از پایتون به‌عنوان یک ماشین حساب](https://github.com/BDadmehr0/Docs-Python-3/blob/main/3/introduction.md#31-%D8%A7%D8%B3%D8%AA%D9%81%D8%A7%D8%AF%D9%87-%D8%A7%D8%B2-%D9%BE%D8%A7%DB%8C%D8%AA%D9%88%D9%86-%D8%A8%D9%87-%D8%B9%D9%86%D9%88%D8%A7%D9%86-%D9%85%D8%A7%D8%B4%DB%8C%D9%86-%D8%AD%D8%B3%D8%A7%D8%A8)**
     - 3.1.1 **[اعداد](https://github.com/BDadmehr0/Docs-Python-3/blob/main/3/introduction.md#311-%D8%A7%D8%B9%D8%AF%D8%A7%D8%AF)**
     - 3.1.2 **[متن](https://github.com/BDadmehr0/Docs-Python-3/blob/main/3/introduction.md#312-%D9%85%D8%AA%D9%86)**
     - 3.1.3 **[لیست‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/3/introduction.md#313-%D9%84%DB%8C%D8%B3%D8%AA%D9%87%D8%A7)**
   - 3.2 **[اولین قدم‌ها به‌سوی برنامه‌نویسی](https://github.com/BDadmehr0/Docs-Python-3/blob/main/3/introduction.md#32-%D8%A7%D9%88%D9%84%DB%8C%D9%86-%D9%82%D8%AF%D9%85%D9%87%D8%A7-%D8%A8%D9%87%D8%B3%D9%88%DB%8C-%D8%A8%D8%B1%D9%86%D8%A7%D9%85%D9%87%D9%86%D9%88%DB%8C%D8%B3%DB%8C)**
1. **[ابزارهای بیشتر برای کنترل جریان](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md)**
   - 4.1 **[عبارات if](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#41-%D8%B9%D8%A8%D8%A7%D8%B1%D8%A7%D8%AA-if)**
   - 4.2 **[عبارات for](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#42-%D8%B9%D8%A8%D8%A7%D8%B1%D8%A7%D8%AA-for)**
   - 4.3 **[تابع range()](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#43-%D8%AA%D8%A7%D8%A8%D8%B9-range)**
   - 4.4 **[عبارات break و continue](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#44-%D8%B9%D8%A8%D8%A7%D8%B1%D8%A7%D8%AA-break-%D9%88-continue)**
   - 4.5 **[عبارات else در حلقه‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#45-%D8%B9%D8%A8%D8%A7%D8%B1%D8%A7%D8%AA-else-%D8%AF%D8%B1-%D8%AD%D9%84%D9%82%D9%87%D9%87%D8%A7)**
   - 4.6 **[عبارات pass](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#46-%D8%B9%D8%A8%D8%A7%D8%B1%D8%A7%D8%AA-pass)**
   - 4.7 **[عبارات match](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#47-%D8%B9%D8%A8%D8%A7%D8%B1%D8%A7%D8%AA-match)**
   - 4.8 **[تعریف توابع](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#48-%D8%AA%D8%B9%D8%B1%DB%8C%D9%81-%D8%AA%D9%88%D8%A7%D8%A8%D8%B9)**
   - 4.9 **[اطلاعات بیشتر در مورد تعریف توابع](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#49-%D8%A7%D8%B7%D9%84%D8%A7%D8%B9%D8%A7%D8%AA-%D8%A8%DB%8C%D8%B4%D8%AA%D8%B1-%D8%AF%D8%B1-%D9%85%D9%88%D8%B1%D8%AF-%D8%AA%D8%B9%D8%B1%DB%8C%D9%81-%D8%AA%D9%88%D8%A7%D8%A8%D8%B9)**
     - 4.9.1 **[مقادیر پیش‌فرض آرگومان‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#491-%D9%85%D9%82%D8%A7%D8%AF%DB%8C%D8%B1-%D9%BE%DB%8C%D8%B4%D9%81%D8%B1%D8%B6-%D8%A2%D8%B1%DA%AF%D9%88%D9%85%D8%A7%D9%86%D9%87%D8%A7)**
     - 4.9.2 **[آرگومان‌های کلیدی](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#492-%D8%A2%D8%B1%DA%AF%D9%88%D9%85%D8%A7%D9%86%D9%87%D8%A7%DB%8C-%DA%A9%D9%84%DB%8C%D8%AF%DB%8C)**
     - 4.9.3 **[پارامترهای خاص](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#493-%D9%BE%D8%A7%D8%B1%D8%A7%D9%85%D8%AA%D8%B1%D9%87%D8%A7%DB%8C-%D8%AE%D8%A7%D8%B5)**
       - 4.9.3.1 **[آرگومان‌های موقعیتی یا کلیدی](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#4931-%D8%A2%D8%B1%DA%AF%D9%88%D9%85%D8%A7%D9%86%D9%87%D8%A7%DB%8C-%D9%85%D9%88%D9%82%D8%B9%DB%8C%D8%AA%DB%8C-%DB%8C%D8%A7-%DA%A9%D9%84%DB%8C%D8%AF%DB%8C)**
       - 4.9.3.2 **[پارامترهای فقط موقعیتی](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#4932-%D9%BE%D8%A7%D8%B1%D8%A7%D9%85%D8%AA%D8%B1%D9%87%D8%A7%DB%8C-%D9%81%D9%82%D8%B7-%D9%85%D9%88%D9%82%D8%B9%DB%8C%D8%AA%DB%8C)**
       - 4.9.3.3 **[آرگومان‌های فقط کلیدی](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#4933-%D8%A2%D8%B1%DA%AF%D9%88%D9%85%D8%A7%D9%86%D9%87%D8%A7%DB%8C-%D9%81%D9%82%D8%B7-%DA%A9%D9%84%DB%8C%D8%AF%DB%8C)**
       - 4.9.3.4 **[مثال‌های تابع](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#4934-%D9%85%D8%AB%D8%A7%D9%84%D9%87%D8%A7%DB%8C-%D8%AA%D8%A7%D8%A8%D8%B9)**
       - 4.9.3.5 **[خلاصه](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#4935-%D8%AE%D9%84%D8%A7%D8%B5%D9%87)**
     - 4.9.4 **[لیست‌های آرگومان دلخواه](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#494-%D9%84%DB%8C%D8%B3%D8%AA%D9%87%D8%A7%DB%8C-%D8%A2%D8%B1%DA%AF%D9%88%D9%85%D8%A7%D9%86-%D8%AF%D9%84%D8%AE%D9%88%D8%A7%D9%87)**
     - 4.9.5 **[پک کردن لیست‌های آرگومان](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#495-%D9%BE%DA%A9-%DA%A9%D8%B1%D8%AF%D9%86-%D9%84%DB%8C%D8%B3%D8%AA%D9%87%D8%A7%DB%8C-%D8%A2%D8%B1%DA%AF%D9%88%D9%85%D8%A7%D9%86)**
     - 4.9.6 **[عبارات لامبدا](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#496-%D8%B9%D8%A8%D8%A7%D8%B1%D8%A7%D8%AA-%D9%84%D8%A7%D9%85%D8%A8%D8%AF%D8%A7)**
     - 4.9.7 **[رشته‌های مستندات](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#497-%D8%B1%D8%B4%D8%AA%D9%87%D9%87%D8%A7%DB%8C-%D9%85%D8%B3%D8%AA%D9%86%D8%AF%D8%A7%D8%AA)**
     - 4.9.8 **[حاشیه‌نویسی توابع](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#498-%D8%AD%D8%A7%D8%B4%DB%8C%D9%87%D9%86%D9%88%DB%8C%D8%B3%DB%8C-%D8%AA%D9%88%D8%A7%D8%A8%D8%B9)**
   - 4.10 **[بینابین (Intermezzo): سبک کدنویسی](https://github.com/BDadmehr0/Docs-Python-3/blob/main/4/controlflow.md#410-%D8%A8%DB%8C%D9%86%D8%A7%D8%A8%DB%8C%D9%86-intermezzo-%D8%B3%D8%A8%DA%A9-%DA%A9%D8%AF%D9%86%D9%88%DB%8C%D8%B3%DB%8C)**
1. **[ساختارهای داده](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md)**
   - 5.1 **[اطلاعات بیشتر در مورد لیست‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#51-%D8%A7%D8%B7%D9%84%D8%A7%D8%B9%D8%A7%D8%AA-%D8%A8%DB%8C%D8%B4%D8%AA%D8%B1-%D8%AF%D8%B1-%D9%85%D9%88%D8%B1%D8%AF-%D9%84%DB%8C%D8%B3%D8%AA%D9%87%D8%A7)**
     - 5.1.1 **[استفاده از لیست‌ها به‌عنوان پشته‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#511-%D8%A7%D8%B3%D8%AA%D9%81%D8%A7%D8%AF%D9%87-%D8%A7%D8%B2-%D9%84%DB%8C%D8%B3%D8%AA%D9%87%D8%A7-%D8%A8%D9%87%D8%B9%D9%86%D9%88%D8%A7%D9%86-%D9%BE%D8%B4%D8%AA%D9%87%D9%87%D8%A7)**
     - 5.1.2 **[استفاده از لیست‌ها به‌عنوان صف‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#512-%D8%A7%D8%B3%D8%AA%D9%81%D8%A7%D8%AF%D9%87-%D8%A7%D8%B2-%D9%84%DB%8C%D8%B3%D8%AA%D9%87%D8%A7-%D8%A8%D9%87%D8%B9%D9%86%D9%88%D8%A7%D9%86-%D8%B5%D9%81%D9%87%D8%A7)**
     - 5.1.3 **[درک لیست‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#513-%D8%AF%D8%B1%DA%A9-%D9%84%DB%8C%D8%B3%D8%AA%D9%87%D8%A7)**
     - 5.1.4 **[درک لیست‌های تو در تو](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#514-%D8%AF%D8%B1%DA%A9-%D9%84%DB%8C%D8%B3%D8%AA%D9%87%D8%A7%DB%8C-%D8%AA%D9%88-%D8%AF%D8%B1-%D8%AA%D9%88)**
   - 5.2 **[عبارت del](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#52-%D8%B9%D8%A8%D8%A7%D8%B1%D8%AA-del)**
   - 5.3 **[تاپل‌ها و دنباله‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#53-%D8%AA%D8%A7%D9%BE%D9%84%D9%87%D8%A7-%D9%88-%D8%AF%D9%86%D8%A8%D8%A7%D9%84%D9%87%D9%87%D8%A7)**
   - 5.4 **[مجموعه‌ها (Sets)](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#54-%D9%85%D8%AC%D9%85%D9%88%D8%B9%D9%87%D9%87%D8%A7-sets)**
   - 5.5 **[دیکشنری‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#55-%D8%AF%DB%8C%DA%A9%D8%B4%D9%86%D8%B1%DB%8C%D9%87%D8%A7)**
   - 5.6 **[تکنیک‌های حلقه‌زنی](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#56-%D8%AA%DA%A9%D9%86%DB%8C%DA%A9%D9%87%D8%A7%DB%8C-%D8%AD%D9%84%D9%82%D9%87%D8%B2%D9%86%DB%8C)**
   - 5.7 **[اطلاعات بیشتر در مورد شرایط](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#57-%D8%A7%D8%B7%D9%84%D8%A7%D8%B9%D8%A7%D8%AA-%D8%A8%DB%8C%D8%B4%D8%AA%D8%B1-%D8%AF%D8%B1-%D9%85%D9%88%D8%B1%D8%AF-%D8%B4%D8%B1%D8%A7%DB%8C%D8%B7)**
   - 5.8 **[مقایسه دنباله‌ها و سایر انواع](https://github.com/BDadmehr0/Docs-Python-3/blob/main/5/datastructures.md#58-%D9%85%D9%82%D8%A7%DB%8C%D8%B3%D9%87-%D8%AF%D9%86%D8%A8%D8%A7%D9%84%D9%87%D9%87%D8%A7-%D9%88-%D8%B3%D8%A7%DB%8C%D8%B1-%D8%A7%D9%86%D9%88%D8%A7%D8%B9)**
1. **[ماژول‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#6-%D9%85%D8%A7%DA%98%D9%88%D9%84%D9%87%D8%A7)**
   - 6.1 **[اطلاعات بیشتر در مورد ماژول‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#61-%D8%A7%D8%B7%D9%84%D8%A7%D8%B9%D8%A7%D8%AA-%D8%A8%DB%8C%D8%B4%D8%AA%D8%B1-%D8%AF%D8%B1-%D9%85%D9%88%D8%B1%D8%AF-%D9%85%D8%A7%DA%98%D9%88%D9%84%D9%87%D8%A7)**
     - 6.1.1 **[اجرای ماژول‌ها به‌عنوان اسکریپت](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#611-%D8%A7%D8%AC%D8%B1%D8%A7%DB%8C-%D9%85%D8%A7%DA%98%D9%88%D9%84%D9%87%D8%A7-%D8%A8%D9%87%D8%B9%D9%86%D9%88%D8%A7%D9%86-%D8%A7%D8%B3%DA%A9%D8%B1%DB%8C%D9%BE%D8%AA)**
     - 6.1.2 **[مسیر جستجوی ماژول](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#612-%D9%85%D8%B3%DB%8C%D8%B1-%D8%AC%D8%B3%D8%AA%D8%AC%D9%88%DB%8C-%D9%85%D8%A7%DA%98%D9%88%D9%84)**
     - 6.1.3 **[فایل‌های پایتون «کامپایل‌شده»](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#613-%D9%81%D8%A7%DB%8C%D9%84%D9%87%D8%A7%DB%8C-%D9%BE%D8%A7%DB%8C%D8%AA%D9%88%D9%86-%DA%A9%D8%A7%D9%85%D9%BE%D8%A7%DB%8C%D9%84%D8%B4%D8%AF%D9%87)**
   - 6.2 **[ماژول‌های استاندارد](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#62-%D9%85%D8%A7%DA%98%D9%88%D9%84%D9%87%D8%A7%DB%8C-%D8%A7%D8%B3%D8%AA%D8%A7%D9%86%D8%AF%D8%A7%D8%B1%D8%AF)**
   - 6.3 **[تابع dir()](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#62-%D9%85%D8%A7%DA%98%D9%88%D9%84%D9%87%D8%A7%DB%8C-%D8%A7%D8%B3%D8%AA%D8%A7%D9%86%D8%AF%D8%A7%D8%B1%D8%AF)**
   - 6.4 **[بسته‌ها](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#64-%D8%A8%D8%B3%D8%AA%D9%87%D9%87%D8%A7)**
     - 6.4.1 **[وارد کردن * از یک بسته](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#641-%D9%88%D8%A7%D8%B1%D8%AF-%DA%A9%D8%B1%D8%AF%D9%86--%D8%A7%D8%B2-%DB%8C%DA%A9-%D8%A8%D8%B3%D8%AA%D9%87)**
     - 6.4.2 **[ارجاعات درون بسته‌ای](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#642-%D8%A7%D8%B1%D8%AC%D8%A7%D8%B9%D8%A7%D8%AA-%D8%AF%D8%B1%D9%88%D9%86-%D8%A8%D8%B3%D8%AA%D9%87%D8%A7%DB%8C)**
     - 6.4.3 **[بسته‌ها در دایرکتوری‌های متعدد](https://github.com/BDadmehr0/Docs-Python-3/blob/main/6/modules.md#643-%D8%A8%D8%B3%D8%AA%D9%87%D9%87%D8%A7-%D8%AF%D8%B1-%D8%AF%D8%A7%DB%8C%D8%B1%DA%A9%D8%AA%D9%88%D8%B1%DB%8C%D9%87%D8%A7%DB%8C-%D9%85%D8%AA%D8%B9%D8%AF%D8%AF)**
1. **ورودی و خروجی**
   - 7.1 **فرمت‌بندی خروجی پیشرفته‌تر**
     - 7.1.1 **رشته‌های فرمت‌شده**
     - 7.1.2 **روش format() رشته**
     - 7.1.3 **فرمت‌بندی دستی رشته**
     - 7.1.4 **فرمت‌بندی قدیمی رشته**
   - 7.2 **خواندن و نوشتن فایل‌ها**
     - 7.2.1 **روش‌های اشیاء فایل**
     - 7.2.2 **ذخیره‌سازی داده‌های ساختارمند با json**
1. **خطاها و استثناها**
   - 8.1 **خطاهای سینتکسی**
   - 8.2 **استثناها**
   - 8.3 **مدیریت استثناها**
   - 8.4 **برافراشتن استثناها**
   - 8.5 **زنجیره‌سازی استثناها**
   - 8.6 **استثناهای تعریف‌شده توسط کاربر**
   - 8.7 **تعریف اقدامات تمیزکاری**
   - 8.8 **اقدامات تمیزکاری پیش‌تعریف‌شده**
   - 8.9 **برافراشتن و مدیریت چندین استثنای نامربوط**
   - 8.10 **غنی‌سازی استثناها با یادداشت‌ها**
1. **کلاس‌ها**
   - 9.1 **یک کلمه در مورد نام‌ها و اشیاء**
   - 9.2 **دامنه‌ها و فضای نام‌های پایتون**
     - 9.2.1 **مثال دامنه‌ها و فضای نام‌ها**
   - 9.3 **نگاهی اولیه به کلاس‌ها**
     - 9.3.1 **سینتکس تعریف کلاس**
     - 9.3.2 **اشیاء کلاس**
     - 9.3.3 **اشیاء نمونه**
     - 9.3.4 **اشیاء متد**
     - 9.3.5 **متغیرهای کلاس و نمونه**
   - 9.4 **نکات تصادفی**
   - 9.5 **وراثت**
     - 9.5.1 **وراثت چندگانه**
   - 9.6 **متغیرهای خصوصی**
   - 9.7 **مسائل و نکات**
   - 9.8 **تکرارکننده‌ها**
   - 9.9 **ژنراتورها**
   - 9.10 **عبارات ژنراتور**
1. **گشت و گذار کوتاه در کتابخانه استاندارد**
   - 10.1 **رابط سیستم‌عامل**
   - 10.2 **فیلترهای نام فایل**
   - 10.3 **آرگومان‌های خط فرمان**
   - 10.4 **هدایت خروجی خطا و خاتمه برنامه**
   - 10.5 **تشخیص الگوی رشته**
   - 10.6 **ریاضیات**
   - 10.7 **دسترسی به اینترنت**
   - 10.8 **تاریخ و زمان**
   - 10.9 **فشرده‌سازی داده‌ها**
   - 10.10 **اندازه‌گیری عملکرد**
   - 10.11 **کنترل کیفیت**
   - 10.12 **باتری‌ها شامل شده است**
1. **گشت و گذار کوتاه در کتابخانه استاندارد - قسمت دوم**
   - 11.1 **فرمت‌بندی خروجی**
   - 11.2 **الگوگذاری**
   - 11.3 **کار با چیدمان‌های داده‌های باینری**
   - 11.4 **چند نخی**
   - 11.5 **ثبت رویداد**
   - 11.6 **ارجاعات ضعیف**
   - 11.7 **ابزارهای کار با لیست‌ها**
   - 11.8 **حساب‌داری اعشاری با نقطه شناور**
1. **محیط‌ها و بسته‌های مجازی**
   - 12.1 **معرفی**
   - 12.2 **ایجاد محیط‌های مجازی**
   - 12.3 **مدیریت بسته‌ها با pip**
1. **حالا چه؟**
1. **ویرایش ورودی تعاملی و جانشینی تاریخچه**
   - 14.1 **تکمیل تب و ویرایش تاریخچه**
   - 14.2 **جایگزین‌هایی برای مفسر تعاملی**
1. **حساب‌داری با نقطه شناور: مسائل و محدودیت‌ها**
   - 15.1 **خطای نمایش**
1. **ضمیمه**
   - 16.1 **حالت تعاملی**
     - 16.1.1 **مدیریت خطا**
     - 16.1.2 **اسکریپت‌های اجرایی پایتون**
     - 16.1.3 **فایل راه‌اندازی تعاملی**
     - 16.1.4 **ماژول‌های سفارشی‌سازی**
