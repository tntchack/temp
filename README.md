# myQazvin
<div dir="rtl">

## معرفی

اپ قزوین من، اپ مدیریت شهری قزوین، پروژه حاضر شامل وب سرویس و وب پنل های اپ قزوین من می باشد.
به وسیله جنگو پیاده سازی شده و شامل ۵ اپلیکیشن مجزا در جنگو است:
news, map, exhibition, account, api
هر اپلیکیشن کار کرد خاص خود را دارد و مدل ها و url ها نیز جداگانه در هر اپلیکیشن تعریف شده
### news
اطلاعات مربوط به بخش اخبار اپ موبایل بوسیله این اپلیکیشن مدیریت میشود شامل  
وب پنل های تحریریه خبر شامل دو پنل با دو سطح دسترسی متفاوت برای مدیر تحریریه و (news moderator) و نویسنده خبر (news author)
شامل مدل های NewsCategory, ReportedNews,News

### map
اپلیکیشن نقشه که اطلاعات مربوط به بخش اطلاعات شهری اپ موبایل  بوسیله این اپلیکیشن مدیریت می شود
شامل مدل های LocationProfile, LocationCategory, Location

### exhibition
اپلیکیشن نمایشگاه که اطلاعات مربوط به بخش نمایشگاه در اپ موبایل بوسیله این اپلیکیشن مدیریت می شود
شامل وب پنل های نمایشگاه دار (exhibition manager) و پیمانکار (contractor) با دو سطح دسترسی متفاوت
و شامل مدل های Exhibition, Booth, 

### account
اپلیکیشن حساب کاربری که اطلاعات مربوط به کاربران، پروفایل های کاربران و سطوح دسترسی آنها بوسیله این اپلیکیشن مدیریت می شود.
شامل view های login, login-redirect, logout, logout-then-login
شامل مدل های Profile, OrganizationProfile, NewsProfile, PersonProfile, PaymentReceipt, Notification
</div>
