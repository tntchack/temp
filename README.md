# myQazvin
<div dir="rtl">

## معرفی

اپ قزوین من، اپ مدیریت شهری قزوین، پروژه حاضر شامل وب سرویس و وب پنل های اپ قزوین من می باشد.
به وسیله جنگو پیاده سازی شده و شامل ۵ اپلیکیشن مجزا در جنگو است:
news, map, exhibition, account, api
هر اپلیکیشن کار کرد خاص خود را دارد و مدل ها و url ها نیز جداگانه در هر اپلیکیشن تعریف شده

## واژگان

اپلیکشین : اپلیکیشین های موجو در یک پروژه جنگو

اپ موبایل : اپلیکشن موبایلی که web server ما با آن سرویس دهی می کند

نمایشگاه دار : کاربری که از طریق  وب پنل امکان تعریف نمایشگاه جدید، ویرایش اطلاعات نمایشگا، ایجاد پیمانکار جدید و انتساب پیمانکار به نمایشگاه را دارد

پیمانکار : کاربری که از طریق وب پنل امکان تعریف غرفه های جدید برای یک نمایشگاه و ویرایش اطلاعات غرفه ها را دارد

مدیر تحریریه : کاربری که از طریق وب پنل امکان نوشتن - انتشار - بایگانی اخبار، ایجاد نویسنده جدید، ایجاد مدیر تحریریه جدید و حذف نویسنده را دارد.

نویسنده خبر: کابری که از طریق وب پل امکان نوشتن اخبار را دارد.

کابر اپ : کاربری است که در حال استفاده از اپ موبایل است.

ادمین : ادمین سایت که به administrator جنگو دسترسی دارد

## پیش نیاز ها

در این پروژه از این کتاب خانه ها استفاده شده است:

celery 4.3.0

django 1.11.20

django-jalali 2.4.6

django-taggit 1.1.0

djangorestframework 3.9.3

djangorestframework-simplejwt 4.3.0

jdatetime 3.2.0

mysqlclient 1.4.2

Pillow 6.0.0

sorl-thumbnail 12.5.0

## اپلیکیشن ها

پروژه شمال ۵ اپلیکیشن مجزا است که توضیاحات هرکدام به شرح زیر است:

### news
اطلاعات مربوط به بخش اخبار اپ موبایل بوسیله این اپلیکیشن مدیریت میشود

شامل وب پنل های تحریریه خبر شامل دو پنل با دو سطح دسترسی متفاوت برای مدیر تحریریه (news moderator) و نویسنده خبر (news author)

شامل مدل های NewsCategory, ReportedNews,News

### map
اپلیکیشن نقشه که اطلاعات مربوط به بخش اطلاعات شهری اپ موبایل  بوسیله این اپلیکیشن مدیریت می شود

شامل مدل های LocationProfile, LocationCategory, Location

### exhibition
اپلیکیشن نمایشگاه که اطلاعات مربوط به بخش نمایشگاه در اپ موبایل بوسیله این اپلیکیشن مدیریت می شود

شامل وب پنل های نمایشگاه دار (exhibition manager) و پیمانکار (contractor) با دو سطح دسترسی متفاوت

شامل مدل های Exhibition, Booth,

### account
اپلیکیشن حساب کاربری که اطلاعات مربوط به کاربران، پروفایل های کاربر، سطوح دسترسی، رسید های خرید و تراکنش های مالی، اعلان ها در آنها بوسیله این اپلیکیشن مدیریت می شود.

شامل view های login, login-redirect, logout, logout-then-login

شامل مدل های Profile, OrganizationProfile, NewsProfile, PersonProfile, PaymentReceipt, Notification

### api

شامل تمام api های پیاده سازی شده برای ارتباط با اپ موبایل

## پروفایل های کاربری

به منظور مدیریت دسترسی ها و ذخیره اطلاعات اضافه برای کاربران د از تعدادی مدل کمکی استفاده میشود که نکات زیر را در استفاده از آنها باید در نظر گرفت: 

### Profile

همه کاربران به منظور کنترل دسترسی به پنل ها و سایر دسترسی ها باید یک پروفایل از نوع Profile داشته باشند
اگر کاربری بدون این پروفایل موجود باشد احتمال بروز خطای سمت سرور هنگام استفاده از وب پنل ها وجود دارد، این مدل 

این مدل شامل یک فیلد panelTypes از نوع رشته است که دسترسی به پنل های مختلف از طریق این فیلد کنترل می شود،

چنان چه این فیلد شامل رشته news باشد کاربر به پنل های اخبار دسترسی دارد،

چنان چه شامل رشته exhibition باشد کاربر به پنل های نمایشگاه دسترسی دارد.

### OrganizationProfile

از این مدل برای ذخیره سازی اطلاعات کاربرانی که هویت سازامانی دارند استفاده می شود.مانند نمایشگاه داران، پیمانکاران و سازمان هایی که پنل اخبار دارند.

### NewsProfile

از این مدل برای نگهداری اطلاعات کابرانی که به پنل اخبار دسترسی دارند و همچنین کنترل دسترسی های نویسنده خبر و مدیر تحریریه استفاده می شود.

### PersonProfile

از این مدل برای نگهداری اطلاعات کاربران اپ موبایل استفاده می شود، هر کاربر اپ موبایل حتما یک پروفایل از این نوع دارد.

## مدل ها

در ادامه مدل های هر اپلیکیشن به صورت جداگانه آورده می شود
</div>

### news

#### NewsCategory
