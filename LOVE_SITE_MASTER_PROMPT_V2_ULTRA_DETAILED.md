# MASTER PROMPT — طراحی، پیاده‌سازی و تحویل سایت عاشقانه سه‌بعدی «Matin & Negar» با بازتولید دقیق استایل مرجع

> **نوع سند:** Master Implementation / Product Specification / Visual Design System / CMS Specification / AI Coding Agent Prompt  
> **هدف:** این فایل باید مستقیماً به یک AI Coding Agent، Agent توسعه‌دهنده، Cursor/Claude Code/Gemini/Codex یا تیم توسعه داده شود تا سایت را از صفر تا نسخه قابل استفاده پیاده‌سازی کند.  
> **منبع بصری اصلی:** تصویر مرجع آپلودشده در همین پروژه با ابعاد **1536×1024**.  
> **منبع محتوایی اولیه:** فایل `imagesoflovesite.zip` شامل **133 فایل تصویر JPG** از عکس‌های واقعی دو نفر.  
> **مخاطب سایت:** تعداد محدودی از افراد؛ سایت خصوصی و شخصی است.  
> **اولویت اصلی:** شباهت بصری بسیار بالا به تصویر مرجع، تجربه احساسی/سه‌بعدی، ویرایش‌پذیری بدون دانش برنامه‌نویسی، و جلوگیری از محتوای ساختگی.

---

## 0. دستور اجرای این سند

تو در این پروژه یک **Senior Full-Stack Engineer + UI/UX Designer + Motion/3D Developer + Media-CMS Architect + Computer-Vision/AI Engineer** هستی.

وظیفه تو این است که از روی تصویر مرجع و توضیحات این سند، یک وب‌سایت عاشقانه خصوصی و بسیار باکیفیت بسازی؛ به‌گونه‌ای که بازدیدکننده در نگاه اول **همان فضای بصری، ترکیب‌بندی، حس، عمق، نور، رنگ، کارت‌بندی و ساختار کلی تصویر مرجع** را ببیند، اما تمام تصاویر، خاطرات، نامه‌ها، مکان‌ها، موسیقی‌ها، فیلم‌ها و روایت داخل سایت متعلق به Matin و Negar باشد.

### قواعد غیرقابل مذاکره

1. تصویر مرجع **Visual Source of Truth** است. ساختار صفحه، هیرارشی بصری، نسبت فضای خالی و پر، حس عمق، گوشه‌های گرد، شفافیت، glow، نورپردازی، نوع حرکت و نحوه نمایش محتوا باید از تصویر مرجع الهام بگیرد و در خروجی واقعی بازسازی شود.
2. خود Screenshot نباید به‌عنوان یک عکس تمام‌صفحه یا پس‌زمینه سایت قرار داده شود تا سایت صرفاً تصویر را تقلید کند. باید **ساختار واقعی HTML/CSS/JS/3D** ساخته شود.
3. محتوای رابطه نباید hard-code شود. هر عنوان، متن، تاریخ، عکس، ویدیو، مکان، موسیقی، رنگ تأکیدی، ترتیب بخش‌ها و متن‌های Hero باید از CMS خوانده شود.
4. کاربر غیر برنامه‌نویس باید بتواند پس از تحویل سایت، محتوای عمده سایت را از پنل مدیریت تغییر دهد و برای تغییر متن یا عکس مجبور به دست‌کاری کد نباشد.
5. عکس‌های ZIP نباید به‌صورت کورکورانه و جداگانه نمایش داده شوند. سیستم باید **تشخیص دهد کدام عکس‌ها احتمالاً متعلق به یک اتفاق/جلسه/روز/خاطره واحد هستند** و آن‌ها را به‌صورت گروه یا Event پیشنهاد کند.
6. هیچ تاریخ، مکان، نام اتفاق، جمله، خاطره، احساس یا رویداد واقعی نباید بدون منبع از روی عکس «اختراع» شود. خروجی AI در هر جایی که ماهیت پیشنهادی دارد باید به‌وضوح در CMS به‌صورت `AI Suggested` علامت بخورد و برای انتشار نهایی نیاز به تأیید انسانی داشته باشد.
7. نباید فرض شود هر چند تصویر مشابه حتماً یک اتفاق واحد هستند؛ سیستم فقط باید **پیشنهاد گروه‌بندی** بدهد و امکان Merge / Split / Reorder / Rename را فراهم کند.
8. در صورت عدم اطمینان، به‌جای ساختن داستان، مقدار را `Unknown / نیازمند تأیید` قرار بده.
9. هیچ تصویر شخصی نباید بدون اجازه مدیر به سرویس بیرونی AI ارسال شود. پردازش AI باید provider-agnostic باشد و امکان اجرای محلی یا سرویس قابل‌تعویض داشته باشد.
10. تجربه دسکتاپ باید نزدیک به Screenshot باشد، اما سایت باید در موبایل نیز به‌صورت حرفه‌ای و غیر شکننده طراحی شود.
11. انیمیشن‌ها باید زیبا و نرم باشند، نه نمایشی و آزاردهنده. سایت نباید به یک «دموی افکت» تبدیل شود؛ محتوا همیشه مهم‌تر از افکت است.
12. همه چیز باید قابل نگهداری، تست، backup و توسعه باشد.

---

# 1. شناخت دقیق پروژه و دارایی‌های اولیه

## 1.1 تصویر مرجع

تصویر مرجع یک صفحه Landing / Home عاشقانه، سینمایی و لوکس است. نسبت کلی تصویر تقریباً 3:2 است و فضای طراحی از بالا تا پایین با لایه‌های مختلف عمق تشکیل شده است.

مشخصات فایل مرجع در زمان تهیه این سند:

- Resolution: `1536 × 1024`
- Mode: `RGBA`
- فضای غالب: تیره، بنفش/شرابی، صورتی، نور گرم
- حس کلی: Romantic / Dreamy / Premium / Cinematic / Personal / 3D Memory World

## 1.2 آرشیو عکس‌های واقعی

آرشیو اولیه `imagesoflovesite.zip` بررسی شده و شامل **133 فایل** است و تمام فایل‌ها JPG هستند.

در بررسی اولیه:

- تعداد کل تصاویر: `133`
- فرمت: `JPG` برای هر 133 فایل
- حالت رنگی: `RGB` برای هر 133 فایل
- EXIF قابل‌استفاده در فایل‌های بررسی‌شده: پیدا نشد؛ بنابراین metadata داخلی دوربین را نباید منبع حقیقت در نظر گرفت.
- تعداد قابل‌توجهی از فایل‌ها از نام‌گذاری‌هایی مانند `IMG_20260816_...` استفاده می‌کنند. این الگوی نام‌گذاری فقط می‌تواند به‌عنوان **سرنخ ضعیف زمانی/ترتیبی** استفاده شود، نه حقیقت قطعی.
- تصاویر زیادی نسبت ابعاد پرتره دارند و گروه دیگری landscape هستند؛ بنابراین سیستم باید crop/focal-point هوشمند و مستقل برای هر slot داشته باشد.

توزیع مهم ابعاد تصاویر:

| ابعاد | تعداد |
|---|---:|
| 1650×2200 | 57 |
| 1649×2200 | 24 |
| 2200×1650 | 24 |
| 960×1280 | 12 |
| 853×1280 | 8 |
| 1280×960 | 3 |
| 1280×853 | 2 |
| 1910×1910 | 1 |
| 1024×1024 | 1 |
| 1466×2200 | 1 |

### نتیجه مهم برای طراحی

عکس‌ها نباید صرفاً در `<img>` با `width:100%; height:auto` نمایش داده شوند. سیستم باید برای هر محل نمایش یک **Media Presentation Mode** داشته باشد:

- `cover`
- `contain`
- `smart-crop`
- `portrait-focus`
- `face-safe-crop`
- `polaroid`
- `full-bleed`
- `cinematic`
- `thumbnail`
- `timeline`
- `book-page`

### درباره شباهت تصاویر

در آرشیو تعداد زیادی عکس از یک موقعیت یا یک بازه کوتاه دیده می‌شود و چند جفت نیز از نظر محتوای تصویری بسیار نزدیک هستند. اما «شباهت ظاهری» به‌تنهایی برای تعیین Event کافی نیست.

بنابراین معماری باید دو مفهوم جدا داشته باشد:

- **Duplicate / Near Duplicate Detection:** برای حذف نمایش تکراری یا شناسایی عکس‌های بسیار مشابه.
- **Event Clustering:** برای تشخیص این‌که کدام مجموعه عکس‌ها احتمالاً متعلق به یک خاطره یا رویداد مشترک هستند.

این دو مسئله نباید با یک الگوریتم واحد و ساده حل شوند.

---

# 2. هدف نهایی محصول

هدف، ساخت یک **Digital Love Museum / 3D Relationship Memory Website** است؛ نه یک گالری عکس معمولی.

سایت باید حس یک جهان خاطره دیجیتال را ایجاد کند که عناصر زیر در آن به هم متصل هستند:

**Home → Our Story → Timeline → Memory Book → Photo Gallery → Places/Love Map → Letters → Videos → Music → Individual Memories → Fullscreen immersive media**

کاربر نباید احساس کند در یک داشبورد CRUD یا یک سایت وبلاگی است. حتی بخش‌های مدیریتی باید از نظر usability تمیز باشند، اما **صفحه عمومی باید تماماً تجربه‌محور، سینمایی و شخصی باشد.**

---

# 3. بازسازی دقیق تصویر مرجع — Visual Reverse Engineering

## 3.1 ساختار کلی صفحه

صفحه اصلی در تصویر مرجع از چند لایه اصلی تشکیل شده است:

1. پس‌زمینه تاریک و عمیق.
2. عناصر تزئینی شناور در Background.
3. Navigation Bar در بالای صفحه.
4. Hero Scene بزرگ و عمیق.
5. زیر Hero یک grid شش‌کارته با 3 ستون و 2 ردیف.
6. در پایین تصویر، ادامه روایت و امکان Scroll به بخش‌های عمیق‌تر سایت.

در نسخه نهایی، این ساختار باید **از نظر visual hierarchy حفظ شود**، ولی ارتفاع بخش‌ها برای نمایشگرهای مختلف responsive باشد.

---

## 3.2 پس‌زمینه

پس‌زمینه باید تقریباً مشکی خالص نباشد؛ بلکه یک فضای بسیار تیره با ته‌رنگ بنفش/شرابی داشته باشد.

ویژگی‌های پس‌زمینه:

- `deep plum / near-black` base
- چند radial gradient بسیار نرم
- نقاط نور کوچک و گرم
- ذرات/بوکه‌های صورتی، قرمز و نارنجی
- شکل‌های قلبی بسیار محو در عمق
- نورهای دوردست مانند fairy lights
- haze بسیار ظریف
- vignette در گوشه‌ها
- depth layers با opacityهای مختلف

پس‌زمینه نباید شلوغ باشد؛ عناصر تزئینی باید به‌صورت depth cue عمل کنند.

### قانون مهم

Decorative particles نباید بالای متن‌ها قرار گیرند و readability را خراب کنند.

---

# 4. Header / Navigation Bar

Header باید در همان فضای بصری تصویر مرجع باشد: مینیمال، تیره، شفاف، لوکس و floating.

## 4.1 سمت راست

در سمت راست Header یک profile capsule کوچک برای رابطه قرار دارد که شامل:

- Avatar دایره‌ای زوج
- نام رابطه، مثلاً `متین & نگار`
- یک خط تاریخ یا عبارت کوتاه

این قسمت باید قابل ویرایش باشد.

## 4.2 منوی اصلی

ترتیب منو در نسخه RTL از نظر تجربه باید مشابه Screenshot باشد و شامل گزینه‌های:

- خانه
- داستان ما
- خاطرات
- فیلم‌ها
- نامه‌ها
- نقشه عشق

ترتیب دقیق این آیتم‌ها باید از CMS قابل تغییر باشد.

هر آیتم:

- icon کوچک line-style
- عنوان فارسی
- hover glow
- transition نرم
- active state مشابه home در Screenshot

### Active Navigation

آیتم فعال یک pill شفاف/تیره دارد که زیر آن glow و خط نورانی صورتی دیده می‌شود.

---

## 4.3 Music Button

در گوشه بالایی صفحه، یک دکمه شناور موسیقی قرار بگیرد.

شکل:

- دایره/کپسول
- translucent
- border بسیار ظریف
- icon موسیقی
- هنگام پخش: موج صوتی یا حلقه بسیار ظریف
- هنگام pause: icon ثابت

با کلیک، Music Drawer باز شود.

---

# 5. Hero Section — مهم‌ترین بخش سایت

Hero باید بیشترین شباهت را به تصویر مرجع داشته باشد.

این قسمت نباید شبیه یک banner ساده باشد. باید **یک صحنه سه‌بعدی عاشقانه** باشد.

## 5.1 ترکیب صحنه

در سمت چپ/مرکز:

- یک Memory Book بزرگ و باز
- دو صفحه واقعی با texture کاغذ
- سایه ضخیم کتاب
- ضخامت جلد و صفحات
- چند گلبرگ پراکنده
- روی یکی از صفحات یک Polaroid / photo card قرار گیرد
- عکس واقعی Matin & Negar داخل آن قرار گیرد
- امکان تغییر عکس Hero از CMS

روی صفحه کتاب:

```text
Matin
♡
Negar
```

و زیر آن یک متن کوتاه دو یا سه خطی، مانند نمونه Screenshot، اما متن واقعی باید از CMS بیاید.

---

## 5.2 اسم زوج

نام‌ها باید با typography احساسی و دست‌نویس/serif نمایان شوند.

ترجیح visual:

- انگلیسی: فونت script / elegant serif
- فارسی: فونت دست‌نویس یا serif فارسی در صورت خوانایی
- glow بسیار ظریف
- shadow نرم

نباید نام‌ها بیش‌ازحد luminous شوند.

---

## 5.3 Polaroid Photo

عکس Hero باید داخل یک Polaroid/photograph frame باشد.

مشخصات:

- قاب سفید/گرم
- shadow
- rotation بسیار جزئی
- امکان rotate در hover
- هنگام load با animation از عمق وارد شود
- در Scroll کمی parallax داشته باشد
- در موبایل اندازه و rotation تطبیقی باشد

---

# 6. Hero سمت راست — Teddy / Couple Object / Emotional 3D Prop

در Screenshot در سمت راست Hero دو عروسک خرسی نشسته‌اند.

در سایت واقعی لازم نیست عروسک دقیقاً همان باشد؛ اما باید **همان نقش بصری** را حفظ کند:

- یک عنصر سه‌بعدی عاشقانه دو نفره
- در حالت نشسته/صمیمی
- رو به فضای اصلی
- نرم، plush، warm
- با نور rim light و shadow

سه مسیر قابل قبول:

1. مدل 3D واقعی و سبک‌شده با Three.js.
2. تصویر cutout با depth layers و pseudo-3D parallax.
3. مدل سه‌بعدی تولیدشده و بهینه‌شده، در صورتی که حجم و عملکرد مناسب بماند.

در صورت نبود مدل 3D مناسب، گزینه 2 بهتر از افزودن یک asset سه‌بعدی سنگین و بی‌کیفیت است.

---

# 7. Hero Statistics / Relationship Counter Card

در سمت راست‌تر Hero یک کارت شیشه‌ای/تیره وجود دارد.

کارت باید شامل:

- عنوانی مانند `یک سال کنار هم`
- شمارنده پویا
- روز
- ساعت
- دقیقه
- ثانیه
- یک جمله کوتاه احساسی
- دکمه/آیکون قلب

مثلاً در Screenshot داده‌ها چنین ساختاری دارند:

```text
365 روز
8760 ساعت
525600 دقیقه
31536000 ثانیه
```

اما این اعداد در نسخه واقعی نباید hard-code باشند.

از `relationship_start_at` محاسبه شوند و با timezone تنظیم‌شده سایت بروزرسانی شوند.

### نکته

برای جلوگیری از رفتار عجیب در سال‌های کبیسه، محاسبه باید بر اساس timestamp واقعی انجام شود، نه صرفاً ضرب روز در 24 ساعت.

---

# 8. Scroll Indicator

بین Hero و بخش بعدی یک دکمه کوچک شناور قرار گیرد.

ظاهر:

- شفاف
- border نیمه‌شفاف
- icon chevron/down
- glow ملایم
- pulse بسیار آرام

با کلیک، صفحه باید نرم به بخش بعدی scroll شود.

---

# 9. Home Grid — شش کارت اصلی

پس از Hero یک grid شش‌تکه وجود دارد.

ساختار دسکتاپ:

```text
┌────────────┬────────────┬────────────┐
│ داستان ما  │ خاطرات ما  │ نقشه عشق  │
├────────────┼────────────┼────────────┤
│ نامه‌ها    │ فیلم‌های ما│ متین به نگار│
└────────────┴────────────┴────────────┘
```

در Screenshot، کارت‌ها دارای:

- background تیره
- glass-like panel
- border صورتی بسیار ظریف
- radius نسبتاً زیاد
- shadow
- داخل کارت composition مستقل

این کارت‌ها نباید صرفاً یک کارت text-only باشند؛ هرکدام باید یک **mini-scene** باشند.

---

# 10. کارت «داستان ما»

عنوان:

`داستان ما`

زیرعنوان:

چیزی در سبک `از اولین روز تا امروز...`

درون کارت:

- timeline کوچک
- چند نقطه مهم
- عکس‌های مهم به‌صورت دایره‌ای یا floating
- line منحنی یا مسیر glowing
- heart markers
- تاریخ هر milestone

در Screenshot، timeline در نیمه پایینی کارت با تصاویر دایره‌ای و مسیر صورتی طراحی شده است.

در نسخه واقعی باید چند **مهم‌ترین لحظه رابطه** از CMS نمایش داده شود.

کلیک روی کارت → صفحه کامل Our Story.

---

# 11. کارت «خاطرات ما»

این کارت مانند یک Gallery Preview باشد:

- چند عکس سه‌بعدی شناور
- عکس مرکزی بزرگ‌تر
- عکس‌های کناری با perspective
- shadow و glow
- عمق Z واقعی یا شبیه‌سازی‌شده

روی hover:

- کارت‌های عکس کمی از هم جدا شوند
- عکس مرکزی بزرگ شود
- perspective بیشتر شود

دکمه:

`ورود به گالری`

---

# 12. کارت «نقشه عشق»

یک map preview بسیار stylized.

در Screenshot:

- دو نقطه دارای برچسب متین و نگار
- خط dotted/curved بین آن‌ها
- قلب‌های کوچک
- حس map/grid شبانه

نسخه واقعی باید یک preview از مکان‌های واقعی را نشان دهد.

### اطلاعات هر Place

هر مکان باید بتواند شامل موارد زیر باشد:

- title
- city
- country
- latitude
- longitude
- address_text اختیاری
- description
- date_first_visited اختیاری
- date_last_visited اختیاری
- favorite_reason
- cover_image
- gallery
- external_map_url اختیاری
- category
- color/accent

**هیچ مختصاتی از روی متن یا لینک به‌طور کورکورانه ساخته نشود.** اگر مکان یا مختصات مشخص نیست، مقدار unknown باقی بماند یا مدیر آن را وارد کند.

---

# 13. کارت «نامه‌ها برای تو»

این بخش در Screenshot با یک نامه/پاکت روی میز و گل رز طراحی شده است.

نسخه واقعی باید یک scene کوچک سینمایی داشته باشد:

- envelope
- paper
- heart seal
- rose/petal
- نور warm
- shadow

متن CTA مانند:

`خواندن نامه‌ها`

کلیک → صفحه Letters.

---

# 14. کارت «فیلم‌های ما»

در Screenshot یک صفحه نمایش و دو حلقه فیلم دیده می‌شود.

نسخه واقعی:

- video screen
- film reels یا cinematic decorative object
- thumbnail واقعی از ویدیو
- play button در مرکز
- progress line در صورت پخش

دکمه:

`مشاهده فیلم‌ها`

---

# 15. کارت «متین به نگار»

این کارت یک متن احساسی و دکمه دارد.

در Screenshot یک گل رز داخل cloche/glass dome نیز دیده می‌شود.

در نسخه واقعی:

- عنوان قابل ویرایش
- متن کوتاه نامه/پیام
- تصویر یا illustration مرتبط
- CTA مانند `دوستت دارم`

این بخش باید از CMS تغذیه شود و محدود به متن یک‌طرفه نباشد؛ امکان ساخت پیام‌های دوطرفه نیز وجود داشته باشد.

---

# 16. ادامه صفحه اصلی بعد از Grid

صفحه اصلی نباید بعد از شش کارت تمام شود.

بعد از Grid، بخش‌های immersive به‌صورت progressive disclosure ظاهر شوند:

1. Timeline Preview
2. Memory Book
3. Full Photo Journey
4. Love Map
5. Letters
6. Videos
7. Music
8. Closing Love Message

اما Navigation همچنان دسترسی مستقیم به هر بخش را فراهم کند.

---

# 17. Memory Book — قلب تجربۀ سایت

Memory Book باید حس ورق‌زدن یک آلبوم واقعی را ایجاد کند.

## 17.1 رفتار

- Book در مرکز viewport
- closed → open
- page flip
- shadow تغییر کند
- paper texture
- corner curl
- عکس‌ها روی صفحات قرار بگیرند
- متن کوتاه کنار تصاویر

هر Event می‌تواند یک spread داشته باشد.

ساختار هر spread:

```text
[Event title]
[date]

[1 تا چند تصویر]

[short narrative]

[location / song / quote / note]
```

### کنترل

- Next
- Previous
- page number
- keyboard arrows
- swipe روی mobile
- close/fullscreen

---

# 18. Event Clustering — حل مسئله 133 عکس بدون ورود دستی تک‌به‌تک

این بخش **یکی از مهم‌ترین نیازهای محصول** است.

کاربر نمی‌خواهد تک‌تک 133 عکس را توضیح دهد.

سیستم باید هنگام import، عکس‌ها را تحلیل کند و گروه‌های پیشنهادی بسازد.

## 18.1 Pipeline پیشنهادی

### Stage A — File Inventory

برای هر فایل ذخیره شود:

- original_filename
- normalized_filename
- extension
- file_size
- width
- height
- aspect_ratio
- sha256
- perceptual_hash
- optional image_embedding
- upload/import timestamp

### Stage B — Near Duplicate Detection

ابتدا هش رمزنگاری برای duplicate دقیق و سپس perceptual hash برای near duplicate استفاده شود.

مواردی که تقریباً یک عکس هستند باید به‌عنوان:

`duplicate_candidate`

برچسب بخورند.

### Stage C — Visual Embedding

برای Event Clustering از یک مدل embedding تصویری مناسب مانند CLIP/OpenCLIP/SigLIP یا جایگزین قابل‌تعویض استفاده شود.

Embedding نباید تنها معیار باشد.

### Stage D — Weak Temporal Signals

از موارد زیر فقط به‌عنوان weak signal استفاده شود:

- filename patterns
- timestamps داخل نام فایل در صورت قابل تشخیص بودن
- import order
- فایل‌های ایجادشده در یک batch

### Stage E — Visual/Temporal Grouping

مدل clustering پیشنهادی:

- HDBSCAN یا DBSCAN برای گروه‌بندی اولیه
- یا clustering سلسله‌مراتبی با threshold قابل تنظیم

امتیاز گروه می‌تواند ترکیبی باشد از:

```text
EventScore =
  visual_similarity_weight
+ temporal_proximity_weight
+ sequence_similarity_weight
+ duplicate_relationship_weight
```

وزن‌ها باید configuration باشند و در کد hard-code نشوند.

---

## 18.2 نتیجه clustering برای کاربر

در پنل مدیریت صفحه‌ای با عنوان:

`AI Photo Organization`

نمایش داده شود.

هر گروه:

- cover image پیشنهادی
- تعداد عکس
- confidence
- candidate title
- candidate date range
- عکس‌های داخل گروه

مثلاً:

```text
Group #07
12 photos
Confidence: 0.84
Suggested title: نیازمند تأیید
Suggested date: نیازمند تأیید
```

کاربر باید بتواند:

- تأیید گروه
- تغییر نام
- تغییر تاریخ
- Merge دو گروه
- Split گروه
- حذف عکس از گروه
- افزودن عکس به گروه
- تغییر Cover
- جابه‌جایی ترتیب عکس‌ها

را با drag & drop انجام دهد.

---

# 19. AI Captioning بدون Fabrication

AI می‌تواند برای هر Event پیشنهاد دهد:

- title
- short caption
- long description
- tags
- mood
- probable activity category
- alt text

اما فقط در صورتی که از تصویر/metadata قابل استنباط باشد.

مثال صحیح:

`دو نفر در فضای باز کنار یک میز نشسته‌اند.`

مثال ممنوع مگر اینکه کاربر/منبع بیرونی آن را تأیید کند:

`این عکس مربوط به اولین قرار شما در فلان رستوران در فلان روز است.`

مگر این‌که چنین اطلاعاتی واقعاً در داده‌های ورودی ثبت شده باشد.

### وضعیت‌های محتوایی

هر محتوای تولیدشده باید یک وضعیت داشته باشد:

- `human-authored`
- `ai-suggested`
- `ai-assisted-human-edited`
- `approved`
- `rejected`
- `unknown`

---

# 20. Timeline — داستان رابطه به شکل واقعی

Timeline یک بخش مستقل و بسیار مهم است.

Desktop:

- محور اصلی در مرکز یا با offset ظریف
- نقاط/heart markers
- دو طرف timeline به‌صورت alternating cards
- image card
- date
- title
- description
- location

Mobile:

- timeline عمودی
- content فقط در یک سمت
- تصویر قابل swipe

### هر Timeline Event

فیلدها:

- title
- date
- display_date
- description
- short_quote
- cover_image
- additional_images
- place
- related_letter
- related_video
- related_music
- importance: 1–5
- order
- visibility

### نمایش در Home

فقط 3 تا 5 milestone کلیدی در کارت Home نمایش داده شود.

---

# 21. Photo Gallery — گالری نباید یک Grid ساده باشد

Gallery باید تجربه‌محور و تعاملی باشد.

## 21.1 ساختار

Gallery بر اساس Event/Date Group شود، نه فقط یک مجموعه 133تایی بی‌ساختار.

مثلاً:

```text
2026 — یک روز خاص
      [photos]

2026 — یک عصر دیگر
      [photos]

... 
```

عنوان Event می‌تواند موقتاً ناشناس باشد تا کاربر اصلاح کند.

---

## 21.2 Animation

تصاویر نباید ناگهان ظاهر شوند.

با Scroll:

- fade-in
- translateY
- scale
- slight rotate
- depth movement

اما باید `prefers-reduced-motion` رعایت شود.

---

## 21.3 Gallery Modes

سیستم بتواند چند حالت نمایش داشته باشد:

1. Polaroid Wall
2. Cinematic Masonry
3. Timeline Gallery
4. 3D Carousel
5. Memory Book
6. Fullscreen story mode

حالت پیش‌فرض مشابه حس Screenshot باشد، اما در صفحه کامل Gallery می‌تواند immersiveتر شود.

---

# 22. 3D Photo Interaction

برای تصاویر مهم، از افکت‌هایی مثل:

- perspective tilt
- depth shadow
- layered frame
- floating card
- z-axis motion
- cursor parallax

استفاده شود.

در hover دسکتاپ:

```text
translateZ → کمی افزایش
rotateX/Y → بسیار محدود
shadow → عمیق‌تر
glow → بسیار ظریف
```

نباید تصویر آنقدر بچرخد که خوانایی/تمرکز را از بین ببرد.

---

# 23. Immersive Lightbox

با کلیک روی عکس، به‌جای یک modal ساده:

- backdrop dark
- تصویر با scale animation وارد شود
- metadata کنار یا زیر آن
- caption
- event
- date
- navigation arrows
- thumbnail strip
- swipe
- keyboard support

روی دسکتاپ امکان split view:

```text
[large image]   [story metadata]
```

روی موبایل:

```text
[image]
[caption]
[metadata]
```

---

# 24. Love Map — نقشه عشق

صفحه جداگانه باید تعادل بین نقشه واقعی و style عاشقانه را حفظ کند.

## 24.1 Map visual

- dark mode
- roads/terrain کم‌کنتراست
- pink glow
- heart pins
- dotted route
- active place pulse

استفاده از MapLibre/Leaflet/Mapbox/Google Maps فقط در صورتی مجاز است که privacy، API key و هزینه قابل کنترل باشد.

برای سایت خصوصی، انتخاب سبک ساده و lightweight ارجح است.

## 24.2 Place Story

کلیک روی Pin:

```text
[photo]
Place Name
Date
Why it matters
Short story
Related memories
```

---

# 25. Letters — سیستم نامه‌های دوطرفه

نامه‌ها باید یکی از احساسی‌ترین بخش‌های سایت باشند.

## 25.1 دو جهت نامه

هر نامه باید بتواند یکی از حالت‌های زیر باشد:

- Matin → Negar
- Negar → Matin
- Shared / Joint

---

## 25.2 ظاهر

پاکت → seal → opening animation → paper reveal.

Paper:

- off-white
- subtle texture
- handwriting-like typography
- realistic line spacing
- soft shadow

نامه باید قابل چاپ نیز باشد.

---

## 25.3 ویرایش

CMS باید editor داشته باشد برای:

- title
- sender
- receiver
- date
- body
- cover photo
- envelope color
- seal icon
- music association
- visibility

---

# 26. Video / Films

سیستم Video باید حداقل این نوع فایل را پشتیبانی کند:

- MP4/H.264
- WebM در صورت نیاز

فیلدها:

- title
- description
- date
- video file یا external URL
- poster image
- duration
- related event
- visibility
- order

ویژگی‌های player:

- play/pause
- seek
- volume
- fullscreen
- poster
- progress
- keyboard accessibility

### مهم

Autoplay صوت‌دار نباید به رفتار غیرقابل پیش‌بینی مرورگر وابسته باشد. صفحه باید gracefully با browser autoplay policies کار کند.

---

# 27. Music System

سیستم موسیقی باید global باشد و در چند صفحه ادامه پیدا کند.

## 27.1 Floating Mini Player

در Home:

- music icon
- current track title
- subtle equalizer
- play/pause

## 27.2 Music Drawer

لیست آهنگ‌ها:

```text
Track Cover
Track Title
Artist
Duration
Play
```

قابلیت:

- next
- previous
- shuffle اختیاری
- volume
- progress
- mute
- select as background track

## 27.3 آهنگ وابسته به خاطره

هر Event و Timeline Event می‌تواند یک آهنگ مرتبط داشته باشد.

با ورود به Event:

- کاربر مطلع شود آهنگ مرتبط وجود دارد
- پخش خودکار فقط در صورت فعال‌سازی مجاز کاربر

---

# 28. CMS — مهم‌تر از Backend زیبایی

Backend می‌تواند Django باشد.

پیشنهاد اصلی:

- **Django**
- Django ORM
- Django Admin به‌عنوان پایه
- یک **Custom Visual Content Manager** روی Admin برای usability
- HTMX برای تعاملات بدون پیچیدگی SPA
- Alpine.js برای state کوچک و تعاملات
- CSS سفارشی + utility classes در صورت نیاز
- Three.js برای 3Dهای واقعی
- Pillow برای image processing
- FFmpeg برای video metadata/poster در صورت امکان
- Celery/RQ یا command jobs برای پردازش‌های سنگین، در صورت نیاز

برای سایت کوچک، از معماری بیش‌ازحد پیچیده استفاده نشود.

---

# 29. ساختار CMS برای کاربر غیر فنی

پنل باید به زبان فارسی و RTL باشد.

Dashboard اصلی:

```text
┌───────────────────────────────────────┐
│ مدیریت سایت عاشقانه                  │
├───────────────────────────────────────┤
│ 🏠 نمای کلی                           │
│ 🖼 عکس‌ها و رسانه‌ها                  │
│ 🧠 سازمان‌دهی هوشمند عکس‌ها          │
│ ❤️ داستان ما / Timeline              │
│ 📖 Memory Book                        │
│ 📍 نقشه عشق                           │
│ ✉ نامه‌ها                             │
│ 🎬 فیلم‌ها                            │
│ 🎵 موسیقی                             │
│ 📝 متن‌ها                              │
│ 🎨 ظاهر سایت                          │
│ ⚙ تنظیمات                             │
└───────────────────────────────────────┘
```

---

# 30. Visual Editor برای صفحه Home

کاربر باید بتواند بدون کدنویسی بگوید:

- Hero photo = تصویر X
- Hero title = متن Y
- Hero subtitle = متن Z
- کارت 1 visible = yes/no
- کارت 2 title = ...
- کارت 3 = ...
- order = ...

بهتر است Home Section Editor شبیه یک form-builder ساده باشد.

### قابلیت Drag & Drop

برای بخش‌های زیر:

- Home cards
- Timeline events
- Gallery photos داخل هر event
- Letters
- Places
- Videos
- Music tracks

---

# 31. Media Library

Media Library باید شبیه یک DAM کوچک باشد.

هر asset:

```text
[thumbnail]
Filename
Type
Dimensions
Event
Tags
Status
```

فیلترها:

- Event
- date
- person/tag
- portrait/landscape
- duplicate candidate
- unassigned
- AI suggested
- approved

---

# 32. سیستم انتخاب «بهترین عکس»

برای هر Event، AI می‌تواند تعدادی عکس را برای cover پیشنهاد دهد.

رتبه‌بندی احتمالی باید از ترکیبی از:

- sharpness
- blur score
- face quality
- exposure
- aesthetic score
- duplicate penalty
- crop suitability

استفاده کند.

این رتبه‌بندی **فقط پیشنهاد** است.

کاربر باید بتواند یک عکس دیگر را به‌عنوان cover انتخاب کند.

---

# 33. Smart Crop / Face-Safe Crop

چون عکس‌ها هم پرتره و هم landscape هستند، سیستم باید نقطه کانونی عکس را حفظ کند.

فیلد:

```text
focal_x
focal_y
crop_mode
```

در CMS یک preview crop ارائه شود.

کاربر بتواند نقطه کانونی را با drag تغییر دهد.

---

# 34. جلوگیری از دست رفتن کیفیت عکس

Original باید حفظ شود.

بهتر است pipeline شامل:

```text
original
→ medium
→ thumbnail
→ webp/avif
```

باشد، ولی original هرگز حذف نشود.

برای نمایش وب:

- lazy loading
- responsive `srcset`
- decoding async
- preloading برای Hero

استفاده شود.

---

# 35. Privacy / Security

چون محتوای سایت شخصی است، این بخش حیاتی است.

حداقل نیاز:

- Authentication
- Admin authentication
- CSRF
- secure sessions
- upload validation
- file extension + MIME validation
- max upload size
- private media storage
- no directory listing
- no public indexing
- `robots.txt` مناسب
- meta `noindex, nofollow` در صورت private mode
- password protection برای سایت در صورت نیاز
- rate limiting برای login

### Recommendation

Media URLها نباید طوری باشند که فقط با حدس URL بتوان عکس خصوصی را دریافت کرد. در حالت Private Site، media endpoint با permission check داشته باشد.

---

# 36. Data Model پیشنهادی

مدل‌های اصلی:

### `SiteSettings`

```text
site_title
relationship_name
person_one_name
person_two_name
person_one_avatar
person_two_avatar
couple_avatar
relationship_start_at
timezone
intro_title
intro_text
footer_text
default_music_track
private_mode
```

### `NavigationItem`

```text
label
route
icon
order
visible
```

### `MediaAsset`

```text
id
original_file
optimized_file
thumbnail
filename
sha256
phash
width
height
aspect_ratio
focal_x
focal_y
embedding_status
ai_tags
caption
alt_text
is_duplicate_candidate
visibility
created_at
```

### `MemoryEvent`

```text
id
title
short_title
description
date_start
date_end
date_precision
cover_media
importance
location
music_track
order
status
ai_confidence
human_approved
```

### `MemoryEventMedia`

```text
event
media
order
caption
is_cover
```

### `TimelineEvent`

```text
title
date
description
cover_media
event
place
quote
order
visible
```

### `Place`

```text
name
city
country
lat
lng
address
story
cover_media
category
first_visit_date
is_favorite
```

### `Letter`

```text
title
sender
receiver
date
body
cover
seal
music
visibility
status
```

### `Video`

```text
title
description
video_file
external_url
poster
date
duration
event
order
visibility
```

### `MusicTrack`

```text
title
artist
audio_file
cover
duration
order
is_enabled
```

---

# 37. Home Configuration — محتوا نباید به Template گره بخورد

یک مدل یا JSON configuration مستقل برای Home داشته باش.

مثلاً:

```json
{
  "hero": {
    "enabled": true,
    "layout": "reference",
    "primary_media_id": 101,
    "secondary_media_id": 102
  },
  "cards": [
    {"type": "timeline_preview", "order": 1},
    {"type": "gallery_preview", "order": 2},
    {"type": "love_map_preview", "order": 3},
    {"type": "letters_preview", "order": 4},
    {"type": "videos_preview", "order": 5},
    {"type": "personal_message", "order": 6}
  ]
}
```

این JSON فقط نمونه معماری است. داده واقعی باید از DB خوانده شود.

---

# 38. Admin Preview

هر تغییر مهم در CMS باید امکان:

`Save Draft → Preview → Publish`

داشته باشد.

کاربر نباید بعد از هر تغییر مجبور باشد سایت عمومی را refresh کند تا بفهمد چه کرده است.

---

# 39. Versioning / Undo

برای متن‌های مهم و ترتیب Eventها، بهتر است version history وجود داشته باشد.

حداقل:

- last saved version
- published version
- draft version

و امکان بازگردانی نسخه قبلی برای محتوای مهم فراهم شود.

---

# 40. AI Photo Organization UI

هنگام ورود ZIP:

```text
Import 133 Photos
        ↓
Scanning
        ↓
Duplicate Analysis
        ↓
Visual Embedding
        ↓
Event Clustering
        ↓
Suggested Memory Groups
```

کاربر سپس گروه‌ها را می‌بیند.

برای هر گروه:

```text
┌─────────────────────────────────────┐
│ Group: #12                          │
│ 9 photos                            │
│ Confidence: 82%                     │
│                                     │
│ [photo][photo][photo][photo]        │
│ [photo][photo][photo][photo]        │
│                                     │
│ [Approve] [Split] [Merge] [Rename] │
└─────────────────────────────────────┘
```

---

# 41. اگر AI نتواند رویدادها را به‌طور مطمئن تشخیص دهد

سیستم حق ندارد برای رسیدن به ظاهری زیبا، واقعیت را جعل کند.

در این حالت:

```text
Event A
Event B
Event C
Needs confirmation
```

و UI از کاربر بخواهد بعداً عنوان/تاریخ را وارد کند.

این حالت کاملاً معتبر است و بهتر از fabricated story است.

---

# 42. مدیریت افراد داخل تصاویر

در نسخه پیشرفته می‌توان تشخیص چهره/تطبیق چهره را اضافه کرد، ولی به دلیل حساسیت حریم خصوصی باید optional باشد.

در صورت استفاده:

- فقط برای سازمان‌دهی داخلی
- بدون ارسال اجباری تصاویر به cloud
- امکان disable کامل
- هیچ برچسب هویتی از افراد واقعی نباید به‌صورت عمومی منتشر شود مگر اینکه مدیر آن را وارد و تأیید کند.

---

# 43. Visual Language / Design Tokens

از Screenshot به‌عنوان منبع اصلی رنگ استفاده شود و مقادیر در Theme Tokens نگه‌داری شوند.

یک palette اولیه پیشنهادی:

```css
--bg-0: #08060D;
--bg-1: #100A18;
--panel: rgba(28, 15, 31, 0.76);
--panel-strong: rgba(36, 18, 40, 0.88);
--pink: #D96A9D;
--pink-soft: #F4A8C7;
--pink-bright: #FFD5E7;
--violet: #7C4A79;
--text: #FFF7FB;
--text-muted: #D7BED0;
--border: rgba(255, 194, 223, 0.28);
--shadow: rgba(0, 0, 0, 0.48);
```

این‌ها **starting tokens** هستند و باید با Screenshot visual-tune شوند.

---

# 44. Glassmorphism

کارت‌ها و Header باید glass effect کنترل‌شده داشته باشند:

```css
background: rgba(...);
backdrop-filter: blur(...);
border: 1px solid rgba(...);
box-shadow: ...;
```

اما blur نباید آنقدر شدید باشد که performance روی موبایل افت کند.

---

# 45. Border Radius

گوشه‌های کارت‌ها در Screenshot مشخصاً rounded هستند.

از scale هماهنگ استفاده شود:

```text
small: 10–12px
medium: 14–18px
large: 20–28px
pill: 999px
```

مقادیر باید centralized باشند.

---

# 46. Typography

### Persian

اولویت:

1. Vazirmatn
2. IRANSansX
3. fallback system sans

### Latin / Names

ترجیح:

- Cormorant Garamond
- Cinzel
- یک script font سبک برای نام‌ها در صورت سازگاری

### قواعد

- Body text خوانا
- عنوان‌ها وزن medium/semibold
- Hero names احساسی‌تر
- letter text می‌تواند handwriting-like باشد

نباید برای کل سایت از یک script font استفاده شود.

---

# 47. Responsive Design

## Desktop 1440px+

ساختار نزدیک‌ترین حالت به Screenshot.

## Laptop 1024–1439px

Hero جمع‌وجورتر شود، ولی composition حفظ شود.

## Tablet 768–1023px

Hero stack نیمه‌عمودی.

## Mobile < 768px

ترتیب پیشنهادی:

```text
Header
Hero Book
Hero Photo
Couple 3D Object
Counter
Scroll
Cards → single column
Timeline → vertical
Gallery → adaptive
Map → full width
Letters
Videos
Music
Footer
```

روی موبایل نباید از 3-column grid اجباری استفاده شود.

---

# 48. Mobile Navigation

Header دسکتاپ در موبایل تبدیل به:

- compact logo/avatar
- music
- hamburger

شود.

منو با animation نرم و backdrop باز شود.

---

# 49. Accessibility

حداقل:

- keyboard navigation
- visible focus states
- alt text
- semantic buttons
- contrast مناسب
- reduced-motion mode
- controls دارای aria-label
- modal قابل بستن با Escape

---

# 50. Performance

این سایت تصویری است، بنابراین performance حیاتی است.

اجباری:

- image lazy loading
- responsive sizes
- AVIF/WebP برای delivery
- original retention
- preload Hero asset
- defer non-critical JS
- code splitting برای Three.js
- عدم بارگذاری همه 133 عکس در اولین request
- pagination/infinite loading در Gallery
- compress audio/video

### 3D Performance

هدف:

- 60fps در دسکتاپ مناسب
- graceful degradation روی موبایل ضعیف
- عدم استفاده از چندین WebGL canvas سنگین به‌طور همزمان

پیشنهاد:

یک canvas اصلی یا استفاده محدود و کنترل‌شده از 3D.

---

# 51. سه‌بعدی و Motion Architecture

Motion system باید یکپارچه باشد.

### دسته‌بندی Motion

`micro`

- 150–250ms

`standard`

- 300–500ms

`cinematic`

- 700–1200ms

### Easing

حرکات باید نرم و natural باشند؛ استفاده از spring-like transition در جاهایی که مناسب است.

### Scroll Reveal

هیچ بخش بزرگی نباید با animation بیش‌ازحد طولانی محو شود.

---

# 52. Floating Hearts / Particles

قلب‌ها باید:

- در عمق‌های مختلف باشند
- سرعت‌های مختلف داشته باشند
- opacity متغیر
- blur متفاوت
- برخی static و برخی animated

از randomization بی‌قاعده برای تغییر ناگهانی Layout استفاده نشود.

seed ثابت برای decorative layout بهتر است تا هر refresh صفحه کاملاً متفاوت و ناپایدار نباشد.

---

# 53. Parallax

حداقل سه depth layer:

```text
Background
Midground
Foreground
```

Hero objects بر اساس pointer و scroll چند پیکسل حرکت کنند.

این حرکت باید محدود و subtle باشد.

---

# 54. Cursor Interaction روی Desktop

یک cursor glow اختیاری:

- بسیار ظریف
- pink/purple radial
- سرعت دنبال کردن نرم

در `prefers-reduced-motion` خاموش شود.

---

# 55. Home Card Hover

Hover نباید صرفاً `transform: scale(1.02)` باشد.

پیشنهاد:

```text
Card → slightly forward
Inner image → depth shift
Border glow → increase
Decor elements → offset
```

---

# 56. Loading Experience

ابتدای سایت یک Preloader بسیار کوتاه و لوکس داشته باشد.

نمونه concept:

```text
♡
Matin & Negar
```

با progress غیرواقعی یا fake percentage طولانی ساخته نشود.

تا زمانی که Hero آماده نشده، background skeleton/ambient scene نمایش داده شود.

---

# 57. Closing Section

در انتهای سایت یک بخش بسیار مینیمال‌تر:

- یک جمله کوتاه
- قلب کوچک
- دو نام
- تاریخ آغاز رابطه
- شاید یک عکس منتخب

قرار گیرد.

این قسمت نباید شلوغ‌تر از Hero باشد.

---

# 58. مدیریت محتوا در سطح Section

هر بخش باید حداقل این گزینه‌ها را داشته باشد:

```text
enabled
order
title
subtitle
cover
background_variant
accent
animation_mode
visibility
```

---

# 59. Theme Editor

مدیر بتواند حداقل تغییر دهد:

- accent color
- background intensity
- card transparency
- corner radius preset
- typography preset
- animation intensity
- particles on/off
- 3D on/off
- music default

و preset ذخیره کند.

مثلاً:

```text
Romantic Night
Velvet Pink
Minimal Love
Cinematic Dark
```

ظاهر پیش‌فرض باید همچنان شبیه Screenshot باشد.

---

# 60. Content Seeding از آرشیو 133 عکس

در اولین نصب پروژه باید یک import workflow وجود داشته باشد.

### Command پیشنهادی

```bash
python manage.py import_love_media /path/to/imagesoflovesite.zip
```

دستور باید:

1. ZIP را validate کند.
2. همه فایل‌ها را استخراج کند.
3. checksum بگیرد.
4. duplicate دقیق را تشخیص دهد.
5. dimensions را ثبت کند.
6. thumbnail بسازد.
7. optimized copies بسازد.
8. perceptual hash بسازد.
9. embedding job را queue کند یا انجام دهد.
10. event clustering را اجرا کند.
11. پیشنهاد group ایجاد کند.
12. گزارش import بسازد.

---

# 61. Import Report

بعد از import، مدیر باید گزارشی ببیند:

```text
Imported: 133
Valid JPG: 133
Exact duplicates: X
Near duplicates: Y
Suggested groups: Z
Unassigned: N
AI analysis completed: ...
AI analysis pending: ...
```

مقادیر X/Y/Z/N باید واقعی محاسبه شوند؛ هرگز ثابت نوشته نشوند.

---

# 62. گزارش اولیه مورد انتظار از این آرشیو

این پروژه در زمان تهیه سند دارای 133 JPG است و هیچ EXIF معتبر قابل‌استفاده‌ای در بررسی اولیه پیدا نشده است.

بنابراین سیستم باید برای تعیین ترتیب/گروه‌بندی روی موارد زیر تکیه کند:

- visual similarity
- image embeddings
- filename pattern به‌عنوان weak signal
- import order
- duplicate hashes
- manual confirmation

و نباید بگوید «تاریخ واقعی عکس را داریم» مگر اینکه یک منبع معتبر در DB وارد شده باشد.

---

# 63. Seed Content — نباید داستان ساختگی ایجاد شود

برای بالا آمدن نسخه Demo می‌توان از placeholderهای محترمانه استفاده کرد:

```text
عنوان: یک خاطره برای یادآوری
تاریخ: نیازمند تأیید
شرح: برای این خاطره هنوز توضیحی ثبت نشده است.
```

اما نباید از روی ظاهر عکس، نام مکان خاص، تاریخ دقیق یا اتفاق دقیق ساخته شود.

---

# 64. Home Defaults

صفحه Home باید پس از نصب حتی با content ناقص نیز زیبا بماند.

برای مثال اگر هنوز Timeline فقط 2 event داشته باشد، کارت Timeline باید به‌صورت graceful همان دو event را نمایش دهد.

اگر هیچ نامه‌ای وجود ندارد، کارت Letters باید خالی و شکسته نباشد؛ بلکه یک CTA برای افزودن نامه نشان دهد.

---

# 65. Empty States

Empty stateها باید بخشی از design system باشند.

مثلاً:

```text
هنوز خاطره‌ای ثبت نشده ❤️
```

یا:

```text
اولین نامه‌تان را اضافه کنید.
```

---

# 66. Error States

خطاهای سیستم نباید exception خام Django را به کاربر نشان دهند.

صفحات:

- 404
- 403
- 500

باید همان visual language سایت را داشته باشند.

---

# 67. Storage Strategy

برای نسخه اولیه:

- SQLite قابل قبول است.

برای نسخه production یا رشد آینده:

- PostgreSQL

Media:

- local private media در ابتدا
- S3-compatible storage در آینده

معماری storage باید abstraction داشته باشد.

---

# 68. Deployment

محلی:

```bash
docker-compose up --build
```

همان command باید در README نوشته شود؛ از syntaxهای متفاوت مگر در صورت ضرورت پرهیز شود.

Production stack پیشنهادی:

```text
Nginx
  ↓
Gunicorn
  ↓
Django
  ↓
PostgreSQL / SQLite
  ↓
Private Media Storage
```

---

# 69. Backup

حداقل backup شامل:

- database
- original media
- music
- videos
- site configuration

باشد.

یک command برای backup تهیه شود.

---

# 70. Export

باید امکان export محتوا وجود داشته باشد:

```text
site-content.json
media manifest
```

تا اگر پروژه به host دیگری منتقل شد، محتوا از بین نرود.

---

# 71. Testing Requirements

## Backend

- model validation
- permissions
- media upload
- import ZIP
- duplicate detection
- event clustering
- save/publish
- private media

## Frontend

- responsive
- navigation
- modals
- keyboard
- gallery
- timeline
- music
- video
- map
- page transitions

## AI

- clustering reproducibility
- fallback when model unavailable
- no fabricated metadata
- confidence display

---

# 72. Browser Testing

حداقل:

- Chrome desktop
- Edge desktop
- Safari desktop/mobile در صورت دسترسی
- Chrome Android

---

# 73. Visual QA — مقایسه با Screenshot

پس از پیاده‌سازی Home باید screenshot گرفته و با تصویر مرجع مقایسه شود.

QA باید موارد زیر را بررسی کند:

### Header

- ارتفاع
- فاصله آیتم‌ها
- alignment RTL
- active pill
- music button

### Hero

- نسبـت book/photo/object
- whitespace
- typography
- counter placement
- depth

### Grid

- 3×2
- فاصله کارت‌ها
- radius
- border
- internal composition

### Background

- intensity
- particles
- lighting

---

# 74. ممنوعیت‌های مهم در طراحی

این خروجی نباید به یکی از موارد زیر تبدیل شود:

- سایت وردپرسی کلاسیک
- گالری عکس ساده
- template عمومی Love Website
- dashboard-like frontend
- صفحه‌ای با کارت‌های سفید معمولی
- صفحه‌ای که Screenshot را به‌عنوان background گذاشته باشد
- page full of random hearts بدون hierarchy
- افکت‌های 3D سنگین که موبایل را خراب کنند
- تولید داستان‌های خیالی توسط AI

---

# 75. اصل مهم در طراحی AI-assisted

AI باید **کاربر را از کارهای خسته‌کننده خلاص کند، نه این‌که به‌جای او خاطرات را جعل کند.**

پس:

```text
AI = Organize + Suggest + Assist
Human = Confirm + Correct + Publish
```

---

# 76. User Journey

### ورود به سایت

کاربر:

1. فضای تاریک را می‌بیند.
2. Hero به‌آرامی load می‌شود.
3. نام Matin & Negar ظاهر می‌شود.
4. تصویر واقعی زوج در Polaroid دیده می‌شود.
5. عناصر پس‌زمینه آرام حرکت می‌کنند.
6. شمارنده رابطه فعال است.
7. کاربر به grid می‌رسد.

### کلیک خاطرات

Home → Memory Gallery → Event → Immersive Lightbox / Book.

### کلیک داستان

Home → Timeline → Event Detail → Related photos/letter/place/music.

### کلیک نقشه

Home → Love Map → Place → Story + photos.

### کلیک نامه

Envelope → Open → Read.

### کلیک فیلم

Cinema scene → Play → Fullscreen.

### کلیک موسیقی

Music → choose track → continue across pages.

---

# 77. روابط بین داده‌ها

یک خاطره باید بتواند همزمان به:

```text
Memory Event
├── Photos
├── Timeline Event
├── Place
├── Letter
├── Video
└── Music
```

مرتبط باشد.

مثلاً کاربر با بازکردن یک Event بتواند همه چیز مربوط به آن را ببیند.

---

# 78. صفحه Event Detail

این صفحه مهم است.

ساختار:

```text
[large cinematic cover]

Event title
Date
Location

[story]

[photo sequence]

[related letter]
[related song]
[related video]
```

این صفحه باید حس یک فصل از کتاب خاطرات را ایجاد کند.

---

# 79. صفحه اختصاصی Photo Gallery

Header ساده‌تر از Home باشد.

Hero کوتاه:

```text
خاطرات ما
از لحظه‌هایی که هنوز زنده‌اند.
```

سپس Event sections.

برای هر Event:

- cover
- title
- date
- photo stack

---

# 80. Photo Stack Interaction

یک روش پیشنهادی:

```text
front photo
middle photo
back photo
```

در hover یا drag، عکس‌ها از هم جدا شوند.

با click، gallery باز شود.

---

# 81. Timeline Interaction

در timeline scroll، markerها به‌صورت progressive وارد شوند.

وقتی یک Event active شد:

- border روشن شود
- cover photo expand شود
- location/music icon روشن شود

---

# 82. Map Interaction

وقتی یک Place انتخاب شود:

- pin pulse
- route اگر وجود دارد highlight
- panel از کنار وارد شود
- photo با animation باز شود

---

# 83. Letter Interaction

هنگام hover پاکت کمی جلو بیاید.

هنگام click:

```text
envelope closed
→ seal break
→ flap open
→ paper pull
→ full letter
```

زمان انیمیشن کوتاه و قابل skip باشد.

---

# 84. Video Interaction

thumbnail در حالت idle با motion بسیار کم نمایش داده شود.

play button با hover:

- scale 1.05
- glow

هیچ autoplay video در نسخه اولیه لازم نیست.

---

# 85. Audio Continuity

اگر کاربر یک آهنگ را play کرد و به صفحه دیگری رفت، در صورت امکان همان track ادامه یابد.

این state می‌تواند با یک global player در layout اصلی نگهداری شود.

---

# 86. SEO / Privacy

چون سایت شخصی است:

پیش‌فرض:

```text
noindex
```

و در صورت private mode:

- password gate
- no social preview leakage در صورت امکان
- private media

---

# 87. Share Behavior

اگر مدیر خواست، امکان share یک Event با لینک امن وجود داشته باشد.

اما default سایت عمومی نباشد.

---

# 88. Admin Content Review Queue

AI-generated items باید در بخشی مانند:

`نیازمند بررسی`

جمع شوند.

برای هر مورد:

```text
AI suggestion
Evidence / reason
Confidence
Approve
Edit
Reject
```

---

# 89. Confidence Semantics

Confidence نباید به کاربر به‌عنوان «درصد حقیقت» فروخته شود.

مثلاً:

```text
High confidence — visual grouping strong
Medium confidence — manual check recommended
Low confidence — do not publish automatically
```

---

# 90. AI Provider Abstraction

ساختار backend:

```text
AIProvider
├── LocalVisionProvider
├── OpenAIProvider
├── GeminiProvider
├── AnthropicProvider
└── MockProvider
```

Provider نباید در business logic پراکنده باشد.

---

# 91. Offline-Friendly Development

تا حد ممکن توسعه محلی باید بدون نیاز دائم به اینترنت ممکن باشد.

حداقل:

- local media
- local DB
- local thumbnails
- optional local embedding

AI cloud باید optional باشد.

---

# 92. Model Fallback

اگر embedding model یا AI provider در دسترس نبود:

- سایت عمومی باید همچنان کار کند.
- gallery باید manual mode داشته باشد.
- clustering می‌تواند pending شود.
- error نباید Home را خراب کند.

---

# 93. Logging

برای کارهای AI و media logs لازم است:

```text
import_id
file_id
provider
model
started_at
finished_at
status
error
```

به‌خصوص برای اثبات این‌که چه چیزی AI generated و چه چیزی human edited است.

---

# 94. Reproducibility

نتیجه clustering باید تا حد امکان قابل تکرار باشد.

ثبت شود:

- model name
- model version
- threshold
- algorithm
- seed
- timestamp

---

# 95. عدم تغییر Original Assets

Original JPGها باید immutable بمانند.

اگر crop یا enhance انجام شد:

```text
original.jpg
processed_version.webp
```

و original حذف نشود.

---

# 96. Asset Naming

در سیستم داخلی ID مستقل وجود داشته باشد.

نام فایل اصلی حفظ شود، ولی URL عمومی نباید تنها بر اساس نام خام فایل باشد.

---

# 97. Duplicate Policy

Near duplicate نباید الزاماً حذف شود.

کاربر شاید بخواهد 2 عکس بسیار شبیه را هر دو نگه دارد چون یکی چشم‌انداز دیگری دارد.

پس:

```text
Duplicate detection ≠ automatic deletion
```

---

# 98. Gallery Sequencing

ترتیب نمایش Event Media باید configurable باشد.

AI می‌تواند ترتیب پیشنهادی بدهد، اما مدیر باید بتواند drag & drop کند.

---

# 99. Human Editing Priority

هر جا تضاد بین:

`AI suggestion` و `Human approved content`

وجود دارد، محتوای انسانی برنده است و AI نباید آن را override کند مگر با درخواست صریح.

---

# 100. Accessibility of Motion

در:

```css
@media (prefers-reduced-motion: reduce)
```

باید:

- parallax خاموش
- particle motion محدود
- page transitions کوتاه
- page flip به simple fade تبدیل شود

---

# 101. Audio Accessibility

- autoplay خاموش به‌صورت پیش‌فرض
- mute state واضح
- keyboard controls
- volume مستقل

---

# 102. Mobile 3D Fallback

اگر WebGL ضعیف بود:

- CSS 3D fallback
- static hero object
- no blank canvas

---

# 103. Visual Hierarchy Rules

در هر viewport فقط یک نقطه focal اصلی وجود داشته باشد.

Home:

`Couple / Book / Names`

Secondary:

`Counter + Navigation`

Tertiary:

`Six card scenes`

Particles باید hierarchy را نشکنند.

---

# 104. Design Density

Screenshot نسبتاً متراکم است ولی شلوغ نیست.

اصل:

```text
rich composition + controlled spacing
```

نه:

```text
many unrelated decorations
```

---

# 105. Realistic Lighting

نورها:

- warm key light around Hero
- pink rim light
- soft purple ambient
- localized glow روی hearts

نباید نور عمومی روی همه عناصر یکسان باشد.

---

# 106. Shadows

سه سطح shadow داشته باش:

```text
Soft
Medium
Cinematic
```

برای book و photo card از Cinematic استفاده شود.

---

# 107. Texture

Textureهای ظریف:

- paper grain
- subtle film grain
- glass blur

با opacity بسیار کم.

---

# 108. Avoid Over-Gloss

نباید همه چیز metallic یا neon شود.

فضای اصلی باید گرم، احساسی و luxurious باشد؛ نه cyberpunk.

---

# 109. Persian RTL Correctness

تمام این موارد باید تست شوند:

- punctuation
- numerals
- date rendering
- mixed Persian/English
- letters
- nav alignment
- card alignment
- map labels

نام‌های انگلیسی مانند `Matin` و `Negar` باید به‌صورت درست در وسط composition قرار گیرند.

---

# 110. Date Formatting

از تاریخ backend استاندارد استفاده شود و سپس display formatter داشته باشد.

قابلیت:

- Gregorian
- Persian/Jalali

مثلاً مدیر بتواند تاریخ را در پنل با Date Picker وارد کند و نحوه نمایش را انتخاب کند.

---

# 111. Relationship Counter

Widget باید قابلیت نمایش:

```text
Years
Months
Days
Hours
Minutes
Seconds
```

را داشته باشد.

نسخه Screenshot می‌تواند روز/ساعت/دقیقه/ثانیه نشان دهد.

---

# 112. Custom Couple Messages

مدیر باید بتواند چند Message بسازد:

```text
title
body
author
recipient
date
image
position
```

مثلاً:

`متین به نگار`

یا:

`نگار به متین`

یا:

`از طرف هردومون`

---

# 113. Love Map Route

در صورت وجود چند مکان، یک route نرم و stylized نمایش داده شود.

اما route نباید لزوماً مسیر رانندگی واقعی باشد.

می‌تواند صرفاً **visual relationship path** باشد.

اگر route واقعی است، منبع و روش محاسبه باید مشخص باشد.

---

# 114. Story Narrative

Narrative page می‌تواند چهار فاز داشته باشد:

```text
Beginning
Discoveries
Memories
Today
```

نام این فازها نیز configurable باشند.

---

# 115. Gallery Filtering

فیلترهای اختیاری:

- All
- Timeline
- Places
- Favorites
- Events
- By year

ولی UI نباید تبدیل به فیلتر پنل پیچیده شود.

---

# 116. Favorite Memories

مدیر می‌تواند favorite مشخص کند.

Favoriteها در Home و closing section استفاده شوند.

---

# 117. Featured Media

سه سطح:

```text
Hero featured
Section featured
Normal
```

AI می‌تواند پیشنهاد بدهد.

---

# 118. Asset Roles

هر تصویر می‌تواند چند نقش داشته باشد:

- Hero
- Cover
- Timeline
- Gallery
- Letter
- Place
- Decorative
- Personal message

یک تصویر نباید مجبور شود فقط یک نقش داشته باشد.

---

# 119. Content Relationships در UI

در زمان ویرایش Event:

```text
Related Photos
Related Place
Related Letter
Related Video
Related Song
Related Timeline Item
```

همه از یک صفحه قابل مدیریت باشند.

---

# 120. Draft / Published

هر entity محتوایی بهتر است visibility داشته باشد:

```text
Draft
Published
Hidden
Archived
```

---

# 121. Import Preview

قبل از نهایی‌شدن import، preview نشان داده شود:

```text
133 files found
133 images valid
...
Proceed?
```

---

# 122. No Destructive AI Actions

AI نباید:

- فایل را حذف کند
- فایل original را overwrite کند
- Event را permanently delete کند
- محتوای human-approved را overwrite کند

مگر با اقدام صریح مدیر.

---

# 123. Generated Contact Sheet

بعد از import، سیستم می‌تواند یک contact sheet برای مدیریت داخلی بسازد تا کاربر تمام 133 عکس را یک‌جا ببیند.

این feature مخصوصاً برای بررسی grouping مفید است.

---

# 124. Manual Event Creation

حتی بدون AI باید کاربر بتواند:

`New Memory Event`

بسازد و تصاویر را drag & drop کند.

---

# 125. Merge / Split UX

### Merge

کاربر Event A و B را انتخاب کند → Merge → preview → confirm.

### Split

داخل یک Event، عکس‌ها را انتخاب کند → Create New Event.

---

# 126. Bulk Actions

در Media Library:

- Select all
- Add tag
- Assign event
- Set favorite
- Mark hidden
- Move

---

# 127. Keyboard Shortcuts

در Gallery/Admin optional:

```text
← → next/previous
Esc close
Space play/pause
```

---

# 128. UX Copy

متن UI باید کوتاه، لطیف و انسانی باشد.

نمونه‌های مناسب:

```text
خاطرات ما
داستان ما
برای تو
لحظه‌هایی که هنوز زنده‌اند
یک قدم دیگر در این داستان
```

از جملات کلیشه‌ای بیش‌ازحد استفاده نشود.

---

# 129. Avoid Template-Copy Feeling

هرجا که Screenshot از یک asset تزئینی استفاده کرده است، نسخه واقعی باید **منطبق با هویت واقعی این زوج** شود.

مثلاً:

- اگر photo card وجود دارد → عکس واقعی زوج
- اگر memory cards وجود دارد → memory event واقعی
- اگر letter scene وجود دارد → نامه واقعی
- اگر map وجود دارد → مکان‌های واقعی ثبت‌شده
- اگر video موجود است → ویدیوی واقعی

---

# 130. Hero Photo Selection

در CMS دو تصویر مهم داشته باش:

```text
Hero Primary
Hero Secondary
```

اما Hero باید بیش از حد پر از عکس نشود.

---

# 131. Progressive Loading Strategy

در اولین viewport:

```text
load:
Hero background
Hero primary image
fonts
critical CSS
```

سپس:

```text
cards
ambient assets
3D scene
```

و بعد:

```text
below-fold images
videos
map
```

---

# 132. PWA / Installability

در صورت مناسب بودن، می‌توان PWA ساخت، اما این feature نباید به قیمت پیچیدگی غیرضروری اضافه شود.

---

# 133. Content Search در آینده

CMS و سایت عمومی باید schema طوری داشته باشد که بعداً بتوان Search اضافه کرد:

```text
search memories
search places
search letters
search dates
```

---

# 134. Internationalization

نسخه اول فارسی/RTL است، ولی مدل داده بهتر است language-ready باشد.

---

# 135. Theme-Level Animation Toggle

مدیر بتواند:

```text
Motion: Full
Motion: Soft
Motion: Minimal
Motion: Off
```

را انتخاب کند.

---

# 136. Developer Architecture

ساختار پیشنهادی پروژه:

```text
love_site/
├── manage.py
├── config/
│   ├── settings/
│   ├── urls.py
│   └── asgi.py
├── core/
├── memories/
├── media_library/
├── timeline/
├── places/
├── letters/
├── videos/
├── music/
├── ai_organizer/
├── cms/
├── templates/
├── static/
│   ├── css/
│   ├── js/
│   ├── textures/
│   └── models/
├── media/
├── tests/
└── README.md
```

اسم appها قابل تغییر است ولی separation of concerns باید حفظ شود.

---

# 137. Frontend Rule

برای Home ترجیحاً از templateهای server-rendered استفاده شود تا:

- SEO/initial load ساده باشد
- deployment ساده باشد
- مدیریت content راحت باشد
- dependency chain کاهش یابد

HTMX برای بخش‌های interactive در صورت نیاز.

---

# 138. Three.js Rule

Three.js فقط برای جاهایی استفاده شود که واقعاً 3D ارزش ایجاد می‌کند:

- Hero scene
- book depth
- selected gallery scenes

نباید هر card یک WebGL scene جدا داشته باشد.

---

# 139. 3D Scene Composition

اگر Three.js استفاده شد:

```text
Scene
Camera
Ambient Light
Key Light
Rim Light
Book/Object Meshes
Floating Particles
Photo Planes
```

مدل‌ها باید سبک باشند.

---

# 140. 3D Texture Safety

عکس‌های کاربر نباید بدون optimization مستقیماً به WebGL textureهای حجیم تبدیل شوند.

برای texture:

- resize
- compression
- mipmap/appropriate filtering

مدیریت شود.

---

# 141. Scroll-linked 3D

Scroll position باید فقط در یک animation loop مدیریت شود تا layout thrashing رخ ندهد.

---

# 142. Browser Fallback

اگر WebGL initialization fail شد:

```text
Use static layered Hero.
Do not show error.
```

---

# 143. CMS Route Structure

نمونه:

```text
/admin/
/admin/media/
/admin/media/ai-groups/
/admin/memories/
/admin/timeline/
/admin/places/
/admin/letters/
/admin/videos/
/admin/music/
/admin/theme/
/admin/home/
/admin/settings/
```

---

# 144. Public Route Structure

نمونه:

```text
/
/story/
/memories/
/memories/<slug>/
/gallery/
/map/
/letters/
/letters/<slug>/
/videos/
/music/
```

---

# 145. Slugs

Slugها باید مستقل از عنوان فارسی و برای URL پایدار باشند.

---

# 146. Admin Usability Details

کاربر غیر فنی باید با توضیحات فارسی روبه‌رو شود، نه field names خام انگلیسی.

مثلاً:

```text
«عکس اصلی Hero»
«عنوان خاطره»
«تاریخ خاطره»
«مکان خاطره»
```

---

# 147. Media Upload UX

Drag & Drop:

```text
فایل‌ها را اینجا رها کنید
```

بعد از upload:

- progress
- preview
- validation
- save

---

# 148. AI Action Buttons

روی Media Library:

```text
سازمان‌دهی خودکار
پیشنهاد عنوان
پیشنهاد ترتیب
تشخیص مشابه‌ها
```

هر action باید قابل لغو/بازبینی باشد.

---

# 149. Human Review of Clusters

اولین بار که 133 عکس import می‌شوند، سیستم نباید خودکار همه را منتشر کند.

باید:

```text
Imported → Needs Review
```

تا کاربر groupها را بررسی کند.

---

# 150. Data Provenance

برای هر generated text ثبت شود:

```text
source_type
source_asset_ids
model
provider
prompt_version
created_at
approved_by
approved_at
```

این کار برای جلوگیری از گم‌شدن منشأ محتوا مهم است.

---

# 151. Prompt Versioning

Promptهای AI داخلی نیز version داشته باشند.

---

# 152. No Hidden AI Behavior

AI نباید در background به‌طور دائمی متن سایت را تغییر دهد.

AI actions باید explicit یا queue-based باشند.

---

# 153. Final Home Visual Checklist

قبل از تحویل، Home باید این عناصر را داشته باشد:

```text
✓ dark romantic cinematic background
✓ RTL navigation
✓ music button
✓ couple profile
✓ large hero scene
✓ open memory book
✓ couple names
✓ real couple photo
✓ romantic 3D object / teddy-like couple prop
✓ relationship counter
✓ scroll indicator
✓ 6 major preview cards
✓ timeline preview
✓ gallery preview
✓ love map preview
✓ letters preview
✓ video preview
✓ personal message preview
```

---

# 154. Final CMS Checklist

```text
✓ edit hero
✓ edit texts
✓ upload images
✓ manage 133+ photos
✓ view AI groups
✓ merge/split groups
✓ assign photos to events
✓ edit event dates
✓ edit timeline
✓ manage places
✓ manage letters
✓ manage videos
✓ manage music
✓ reorder sections
✓ toggle visibility
✓ preview drafts
✓ publish
✓ backup/export
```

---

# 155. Final AI Checklist

```text
✓ duplicate detection
✓ near-duplicate detection
✓ visual embeddings
✓ event clustering
✓ confidence
✓ suggested title
✓ suggested caption
✓ suggested cover
✓ human approval
✓ no fabrication
✓ provider abstraction
✓ reproducibility logs
```

---

# 156. Final Visual Quality Bar

خروجی باید در سطحی باشد که اگر Screenshot مرجع کنار نسخه پیاده‌سازی‌شده قرار گرفت:

- Layout کلی فوراً قابل تشخیص باشد.
- Palette و lighting بسیار نزدیک باشد.
- Hero همان visual rhythm را داشته باشد.
- کارت‌ها همان حس glass/premium را بدهند.
- Motion و depth مشابه حس مرجع باشد.
- ولی تصاویر و داستان داخل سایت کاملاً متعلق به زوج باشند.

این پروژه نباید صرفاً «تقریباً شبیه» باشد؛ در بخش Home باید **reference-driven recreation** انجام شود.

---

# 157. Definition of Done

پروژه فقط وقتی Done است که:

1. Home از نظر ساختار، spacing، hierarchy و visual language با Screenshot مرجع هماهنگ باشد.
2. سایت با 133 عکس اولیه load و organize شود.
3. عکس‌ها گروه‌بندی پیشنهادی شوند و UI بررسی آن‌ها وجود داشته باشد.
4. کاربر بدون کدنویسی بتواند content اصلی را تغییر دهد.
5. Gallery، Timeline، Memory Book، Map، Letters، Videos و Music فعال باشند.
6. صفحات در موبایل سالم باشند.
7. motion reduction فعال باشد.
8. private media قابل دسترسی عمومی نباشد.
9. backup/export وجود داشته باشد.
10. README نصب و اجرا را توضیح دهد.
11. هیچ ادعای factual بدون source از داده‌های واقعی ساخته نشده باشد.
12. تست‌های حیاتی پاس شوند.

---

# 158. دستور نهایی به AI Coding Agent

قبل از شروع coding:

### مرحله 1 — Asset Audit

آرشیو عکس را کامل scan کن.

هیچ فایل را نادیده نگیر.

یک manifest تولید کن.

### مرحله 2 — Visual Reverse Engineering

Screenshot را به component-level decomposition تبدیل کن.

محدوده تقریبی هر بخش، alignment، رنگ، depth و hierarchy را ثبت کن.

### مرحله 3 — Architecture

Django + CMS + media pipeline + AI organizer + frontend architecture را طراحی کن.

### مرحله 4 — Media Ingestion

133 عکس را وارد media library کن.

### مرحله 5 — AI Organization

Duplicate / near duplicate / visual clustering را انجام بده.

### مرحله 6 — Human Review UI

گروه‌های پیشنهادی را در CMS نمایش بده.

### مرحله 7 — Home Recreation

Home را بر اساس Screenshot پیاده کن.

### مرحله 8 — Immersive Sections

Timeline، Memory Book، Gallery، Map، Letters، Videos و Music را پیاده کن.

### مرحله 9 — CMS

تمام contentهای اصلی را editable کن.

### مرحله 10 — QA

Desktop + mobile + accessibility + performance + privacy.

### مرحله 11 — Delivery

این موارد را تحویل بده:

```text
source code
.env.example
README.md
media import command
database schema/migrations
AI organizer
CMS
frontend
tests
Docker configuration
backup/export tools
```

---

# 159. گزارش‌دهی پس از اجرا

Agent پس از پیاده‌سازی نباید صرفاً بگوید «Done».

گزارش باید شامل این موارد باشد:

```text
Implementation status
Visual match status
Asset import status
AI clustering status
CMS status
Testing status
Performance status
Security status
Known limitations
Next manual review items
```

برای هر مورد اگر چیزی ناقص است، دقیقاً ذکر شود.

---

# 160. مهم‌ترین اصل پروژه

این پروژه قرار نیست فقط عکس‌ها را نشان دهد.

باید **خاطرات را به یک فضای سه‌بعدی، روایی، قابل لمس و قابل مدیریت تبدیل کند.**

اما این تجربه نباید حقیقت را قربانی زیبایی کند.

قاعده نهایی:

> **زیبایی از طراحی بیاید؛ حقیقت از داده‌های واقعی؛ هوش مصنوعی نقش دستیار را داشته باشد؛ و کنترل نهایی همیشه در اختیار انسان باشد.**

---

# Appendix A — خلاصه فنی آرشیو اولیه

آرشیو اولیه:

```text
Archive: imagesoflovesite.zip
Total members: 133
Image files: 133
Format: JPG
Color mode: RGB
EXIF found in initial inspection: 0
```

Distribution:

```text
1650×2200  → 57
1649×2200  → 24
2200×1650  → 24
960×1280   → 12
853×1280   → 8
1280×960   → 3
1280×853   → 2
1910×1910  → 1
1024×1024  → 1
1466×2200  → 1
```

### نکته درباره نام فایل‌ها

بخشی از تصاویر نام‌هایی مانند موارد زیر دارند:

```text
IMG_20260816_194333_325.jpg
IMG_20260816_200131_225.jpg
IMG_20260816_200955_130.jpg
```

وجود یک date-like pattern در filename مفید است، اما **به هیچ وجه نباید بدون تأیید انسانی به‌عنوان تاریخ واقعی عکس ثبت شود.**

---

# Appendix B — نمونه Content JSON برای توسعه

این فقط schema نمونه است و نباید محتوای واقعی را جعل کند:

```json
{
  "site": {
    "title": "Matin & Negar",
    "rtl": true,
    "private": true,
    "relationship_start_at": null
  },
  "hero": {
    "title": "Matin ♡ Negar",
    "subtitle": "",
    "primary_media": null,
    "secondary_media": null
  },
  "memories": [],
  "timeline": [],
  "places": [],
  "letters": [],
  "videos": [],
  "music": []
}
```

---

# Appendix C — نمونه UI Content برای Demo

برای پیش‌نمایش اولیه، این متن‌ها مجازند صرفاً به‌عنوان placeholder استفاده شوند:

```text
داستان ما
خاطره‌هایی که هنوز ادامه دارند...

خاطرات ما
لحظه‌هایی که ارزش دوباره دیدن دارند.

نقشه عشق
جاهایی که بخشی از داستان ما شدند.

نامه‌ها برای تو
حرف‌هایی که شاید بهتر است نوشته شوند.

فیلم‌های ما
لحظه‌هایی که می‌شود دوباره زندگی‌شان کرد.

متین به نگار
برای تو...
```

این placeholderها پس از ورود محتوای واقعی باید از CMS جایگزین شوند.

---

# Appendix D — Acceptance Test برای اولین نسخه

## A. Home

- [ ] reference composition قابل تشخیص است.
- [ ] Hero تصویر واقعی زوج را از Media Library می‌گیرد.
- [ ] Navigation RTL است.
- [ ] Music button فعال است.
- [ ] Counter داینامیک است.
- [ ] 6 card scene نمایش داده می‌شود.

## B. Media

- [ ] 133 تصویر import می‌شوند.
- [ ] originalها حفظ می‌شوند.
- [ ] optimized derivatives تولید می‌شوند.
- [ ] near duplicates مشخص می‌شوند.
- [ ] گروه‌بندی پیشنهادی ایجاد می‌شود.

## C. CMS

- [ ] مدیر بدون کدنویسی Hero را عوض می‌کند.
- [ ] متن‌ها را تغییر می‌دهد.
- [ ] تصاویر را reorder می‌کند.
- [ ] Event ایجاد/ویرایش می‌کند.
- [ ] Place ایجاد/ویرایش می‌کند.
- [ ] Letter ایجاد/ویرایش می‌کند.
- [ ] Music/Video مدیریت می‌کند.

## D. Experience

- [ ] Memory Book page flip دارد.
- [ ] Gallery immersive است.
- [ ] Timeline تعاملی است.
- [ ] Map قابل تعامل است.
- [ ] Letters animation دارد.
- [ ] Videos playable هستند.
- [ ] Music global player دارد.

## E. Safety

- [ ] private media access control دارد.
- [ ] noindex فعال است.
- [ ] AI fabricated metadata منتشر نمی‌کند.
- [ ] human approval workflow وجود دارد.

---

# Appendix E — Priority Matrix

### P0 — حیاتی

```text
Reference-like Home
Real photo integration
CMS editing
Media Library
Event clustering workflow
Timeline
Gallery
Letters
Music
Responsive
Privacy
```

### P1 — مهم

```text
3D Book
Love Map
Videos
AI captions
AI cover selection
Draft/Publish
Backup/Export
```

### P2 — تکمیلی

```text
Advanced WebGL
PWA
advanced face grouping
multilingual
shareable memories
```

---

# Final Instruction

**هر تصمیم فنی که می‌گیری باید در خدمت سه هدف باشد:**

`1) شباهت بصری بسیار بالا به تصویر مرجع`

`2) تجربه عاشقانه/سه‌بعدی و روایی با عکس‌های واقعی Matin و Negar`

`3) قابلیت مدیریت کامل محتوا توسط فرد غیر برنامه‌نویس`

در هیچ مرحله‌ای ظاهر را با استفاده از داده جعلی بهتر نکن.

در هیچ مرحله‌ای برای ساده‌کردن توسعه، CMS را حذف نکن.

در هیچ مرحله‌ای برای سریع‌تر شدن، تمام عکس‌ها را یک‌جا در صفحه اول load نکن.

در هیچ مرحله‌ای Screenshot را با `background-image` جایگزین UI واقعی نکن.

و در هیچ مرحله‌ای به دلیل مشابه‌بودن چند عکس، بدون تأیید انسانی آن‌ها را حذف یا داستان مشترک برایشان قطعی نکن.

**خروجی نهایی باید یک سایت عاشقانه واقعی، شخصی، لوکس، سینمایی، سه‌بعدی، قابل مدیریت و قابل توسعه باشد؛ نه یک mockup، نه یک gallery ساده و نه یک template عمومی.**


# ULTRA-DETAILED ADDENDUM — بخش اول: Visual Reverse Engineering و بازسازی سخت‌گیرانه تصویر مرجع

> **این Addendum به انتهای سند اضافه می‌شود و هیچ بخشی از متن قبلی را حذف، کوتاه یا بی‌اثر نمی‌کند.** این بخش برای آن نوشته شده است که یک AI Coding Agent نتواند از روی عبارت‌های کلی مانند «تم رمانتیک» یک طرح دلخواه تولید کند. باید Screenshot را مانند یک art director و front-end engineer به اجزای دقیق تبدیل کند.

---

# 161. Reference Fidelity Contract

این پروژه یک «الهام از تصویر» نیست؛ یک **reference-driven reconstruction** است.

در شروع کار Agent باید یک سند داخلی به نام `REFERENCE_AUDIT.md` بسازد و در آن موارد زیر را ثبت کند:

```text
reference viewport
canvas ratio
header bounding region
hero bounding region
book bounding region
right object bounding region
counter card bounding region
six-card grid bounding region
primary text anchors
major color families
shadow/glow language
background decorative layers
```

اگر Agent تصمیمی می‌گیرد که با Screenshot متفاوت است، باید علت فنی آن را ثبت کند؛ مثلاً:

```text
Difference: mobile layout
Reason: reference is desktop-only; mobile requires reflow
```

نه اینکه به‌سادگی طراحی را عوض کند.

---

# 162. Screenshot Geometry — مرجع 1536×1024

در Reference، کل صفحه یک composition واحد است. در implementation اولیه باید این نسبت‌ها حفظ شوند.

## 162.1 Outer canvas

- viewport reference: `1536 × 1024`
- outer visual padding: بسیار کم
- صفحه تقریباً تمام عرض را اشغال می‌کند.
- فاصله از لبه‌ها مخصوصاً در grid پایین بسیار کم است.

## 162.2 Header band

Header در ناحیه `y ≈ 0–90` قرار دارد.

جزئیات:

- حاشیه بالا زیاد نیست.
- header نباید با background به یک نوار خاکستری تبدیل شود.
- تمام navigation items در یک خط تقریباً افقی تراز هستند.
- profile capsule و music button در دو انتهای ترکیب قرار دارند.

## 162.3 Hero band

Hero تقریباً از `y ≈ 85` تا `y ≈ 470` امتداد دارد.

این ناحیه باید از نظر بصری بزرگ‌ترین scene پیش از card grid باشد.

## 162.4 Grid band

Grid از حدود `y ≈ 487` شروع می‌شود.

برای viewport reference:

```text
outer horizontal inset ≈ 7–10px
column gap             ≈ 10–16px
row gap                ≈ 8–14px
```

این‌ها initial calibration values هستند؛ در screenshot comparison باید تنظیم شوند.

---

# 163. Header Reverse Engineering — جزئیات بصری

Header باید floating و low-contrast باشد.

## 163.1 سمت راست: Couple Identity

تقریباً نزدیک لبه راست یک capsule دیده می‌شود که شامل:

1. تصویر دایره‌ای زوج
2. نام کوتاه زوج
3. metadata/date کوچک‌تر

است.

فاصله avatar از متن باید کم ولی خفه‌کننده نباشد.

Avatar:

- گرد
- border بسیار باریک
- background dark
- subtle glow

متن اصلی:

- سفید/شیری
- weight متوسط

متن دوم:

- muted
- کوچکتر

## 163.2 Navigation

Navigation بین profile و music control قرار دارد.

هر item شامل:

```text
icon
label
```

است.

فاصله icon تا label کم و هماهنگ باشد.

### Active item

Home در reference یک pill تیره‌تر دارد:

- rounded rectangle
- shadow/glow زیرین
- pink highlight کوچک در پایین

این active state باید بدون استفاده از border ضخیم ساخته شود.

---

# 164. Music Control در Header

Music control در سمت چپ header یک button شناور است.

Visual rules:

- دایره/کپسول
- dark translucent fill
- thin border
- music-note icon سفید/صورتی

هنگام hover:

- scale حداکثر چند درصد
- glow اندکی بیشتر

هنگام playing:

- pulse کوچک
- waveform بسیار ظریف

نباید به یک equalizer بزرگ تبدیل شود.

---

# 165. Hero Scene — Composition Map

Hero به سه ناحیه تصویری اصلی تقسیم می‌شود:

```text
LEFT/CENTER     → OPEN MEMORY BOOK
RIGHT-CENTER    → COUPLE / 3D OBJECT
RIGHT-FAR       → RELATIONSHIP COUNTER
```

و این سه ناحیه باید با background ambience به یک scene مشترک متصل باشند.

---

# 166. Hero Book — bounding-box target

در reference کتاب باز حدوداً از:

```text
x = 175–190
x2 = 840–855
y = 110–125
y2 = 455–465
```

است.

یعنی کتاب بسیار بزرگ است و بخش عمده Hero را می‌گیرد.

## 166.1 زاویه

کتاب کمی perspective دارد.

اسپاین مرکزی کمی پایین‌تر از بالاترین نقاط صفحات قرار می‌گیرد.

صفحات باید:

- کاملاً flat نباشند.
- کمی bend داشته باشند.
- inner shadow نزدیک spine داشته باشند.

## 166.2 صفحه چپ

صفحه چپ نقش typography/relationship declaration دارد.

Hierarchy:

```text
small top whitespace
→ Matin
→ heart
→ Negar
→ short paragraph
→ tiny decorative heart
```

## 166.3 صفحه راست

صفحه راست host عکس Polaroid است.

در screenshot، Polaroid کمی rotated و در مرکز/بخش بالایی صفحه قرار گرفته است.

---

# 167. Book Material

سطح کتاب باید حس:

- کاغذ قدیمی لوکس
- نرم
- matte
- کمی pink/lilac

داشته باشد.

Texture باید subtle باشد؛ texture خیلی واضح باعث می‌شود تصویر مصنوعی و noisy شود.

برای ساخت می‌توان از:

- procedural CSS noise بسیار کم
- image texture
- generated material

استفاده کرد.

---

# 168. Page Edge Detail

اگر book با HTML/CSS شبیه‌سازی می‌شود، لبه پایین و کنار صفحات باید با چند layer shadow/edge ساخته شود تا thickness دیده شود.

اگر Three.js استفاده شد:

- page mesh
- thickness geometry
- page material

ترجیح دارد.

هدف این نیست که یک کتاب واقعی شبیه‌سازی فیزیکی با صدها صفحه ساخته شود؛ هدف **optically convincing depth** است.

---

# 169. Polaroid — اندازه و زاویه

عکس داخل کتاب در یک قاب تقریباً مستطیلی با border روشن است.

قاب:

- روشن‌تر از صفحه کتاب
- white/cream
- shadow soft
- کمی rotate

خود عکس باید:

- aspect ratio خودش را حفظ کند.
- crop هوشمند داشته باشد.
- در صورت امکان یک composition مناسب برای couple داشته باشد.

---

# 170. Petals on the Book

چند گلبرگ باید روی/کنار کتاب وجود داشته باشد.

این گلبرگ‌ها:

- foreground accent هستند.
- opacity متوسط/پایین دارند.
- بعضی sharp و بعضی کمی blurred باشند.

تعدادشان کنترل‌شده باشد.

---

# 171. Right-side Couple Scene — لايه‌بندی دقیق

در reference دو عروسک/خرس کوچک با فرم گرد و نرم روی یک پایه دیده می‌شوند.

برای نسخه واقعی سایت اگر مدل 3D آماده در دسترس نباشد، می‌توان از یک object stylized یا image-based composition استفاده کرد؛ اما باید سه اصل رعایت شود:

1. سطح نشستن مشخص باشد.
2. contact shadow مشخص باشد.
3. object از background جدا شود.

---

# 172. Warm Lamp / Background Props

در اطراف Hero right side، نور و propهای گرمی وجود دارند.

این props نباید content واقعی باشند. می‌توانند:

- lantern
- warm lamp
- blurred decorative objects

باشند.

اما باید در background قرار بگیرند و با blur/opacity کنترل شوند.

---

# 173. Bokeh System

نقاط نورانی دوردست در screenshot مهم‌اند.

برای هر bokeh:

```text
radius
opacity
color-temperature family
blur
depth
x/y
```

تعریف شود.

Bokeh باید بیشتر در لایه‌های پشت Hero باشد.

---

# 174. Heart Particle System

قلب‌های بسیار دوردست باید بیشتر شبیه light particles باشند تا iconهای واضح.

قلب foreground می‌تواند واضح‌تر باشد، اما تعداد آن کم باشد.

---

# 175. Fairy-light System

در سمت چپ و اطراف Hero ردیف‌هایی از نقاط نور گرم به چشم می‌خورند.

این‌ها باید:

- منحنی/خطوط نرم
- نقاط نور کوچک
- blur کنترل‌شده

داشته باشند.

ممنوع:

- رشته چراغ‌های بسیار درخشان
- حرکت سریع

---

# 176. Hero Text Typography

نام‌های `Matin` و `Negar` در screenshot از body typography متفاوت‌اند و حس handwritten/script یا elegant display دارند.

بنابراین:

```text
Body font ≠ Couple name font
```

باید یک display font مناسب برای نام‌ها انتخاب شود.

فونت نهایی قابل تعویض از Theme/CSS token باشد.

---

# 177. Hero Copy Width

متن زیر نام‌ها باید عرض محدود داشته باشد و در چند خط کوتاه قرار گیرد.

نباید یک paragraph عریض باشد.

line-height کمی باز باشد تا روی texture کاغذ خوانا بماند.

---

# 178. Relationship Counter — visual placement

Counter باید روی layer بالاتر از background ولی کنار right object قرار بگیرد.

Counter نباید با object ترکیب شود.

فاصله منطقی میان:

```text
right object ↔ counter card
```

حفظ شود تا هر دو عنصر مستقل اما هم‌صحنه دیده شوند.

---

# 179. Counter Typography Hierarchy

ساختار:

```text
Title
↓
large number/primary unit
↓
secondary units
↓
heart CTA
```

نسبت title به numbers باید طوری باشد که numbers dominant باشند ولی card حالت statistics dashboard نگیرد.

---

# 180. Hero Bottom Boundary

پایان Hero در screenshot با یک مرز سخت مشخص نشده است.

در نتیجه:

- از border-top غلیظ روی grid استفاده نکن.
- به جای آن از dark fade / shadow / ambient overlap استفاده کن.

---

# 181. Scroll Indicator — دقیق

در مرکز نزدیک انتهای Hero یک دکمه کوچک گرد قرار دارد.

ظاهر:

- translucent
- rounded
- border thin
- down chevron
- tiny glow

می‌تواند با animation نرم نشان دهد که page قابل scroll است.

---

# 182. Six-card Grid — exact visual topology

Reference پایین صفحه **شش کارت بزرگ** دارد.

در viewport دسکتاپ:

```text
┌────────────┬────────────┬────────────┐
│ Story      │ Memories   │ Love Map   │
├────────────┼────────────┼────────────┤
│ Letters    │ Videos     │ Message    │
└────────────┴────────────┴────────────┘
```

اما چون سایت RTL است، mapping باید با slotهای صریح کنترل شود.

از سمت راست screenshot:

```text
Top-right    = Love Map
Top-center   = Memories
Top-left     = Story
Bottom-right = Personal Message
Bottom-center= Videos
Bottom-left  = Letters
```

این mapping نباید تصادفی شود.

---

# 183. Card Shell

همه کارت‌ها از یک shell مشترک بهره ببرند، اما **داخل هر کارت scene متفاوت باشد**.

Shell:

- dark translucent background
- thin luminous border
- rounded corners
- subtle shadow
- overflow hidden

---

# 184. Card Border

Border باید ظریف باشد و در قسمت‌های خاص کمی glow داشته باشد.

نباید:

- 2–3px ضخیم
- سفید روشن

باشد.

---

# 185. Card Internal Background

هر card می‌تواند background ambience مخصوص خود داشته باشد:

- Story → warm/pink path
- Memories → photo-focused purple
- Map → darker grid
- Letters → paper/rose ambience
- Videos → cinematic dark
- Personal Message → rose/lamp ambience

اما همه باید از palette جهانی تبعیت کنند.

---

# 186. Card Title Placement

عنوان در بخش بالایی card و تقریباً centered قرار دارد.

زیر آن subtitle کوچک قرار می‌گیرد.

در reference عنوان‌ها به‌صورت مستقیم داخل صحنه قرار گرفته‌اند، نه در یک header bar جداگانه.

---

# 187. Card CTA

CTAها کوچک، pill-shaped و در پایین card قرار می‌گیرند.

CTA نباید dominant‌تر از visual object باشد.

---

# 188. Card Hover Perspective

در desktop:

با حرکت mouse می‌توان tilt بسیار محدود داد:

```text
max rotateX ≈ 1–2deg
max rotateY ≈ 1–2deg
```

این فقط برای depth است.

---

# 189. Card Scene — Story

در Story card باید یک مسیر/خط timeline کوچک همراه با چند milestone دایره‌ای و عکس‌های گرد وجود داشته باشد.

این timeline miniature باید به timeline اصلی اشاره کند و فقط preview باشد.

---

# 190. Story Card Image Roles

حداقل:

- start image
- mid image
- end image

وجود داشته باشد، اگر داده کافی باشد.

اگر داده کافی نیست، تعداد کمتر شود؛ فضای خالی حفظ شود.

---

# 191. Card Scene — Memories

در Memories card، چند photo frame در عمق مختلف قرار بگیرد.

قاب‌ها باید تقریباً:

```text
back-left
back-right
front-center
```

باشند.

Front image باید واضح‌تر و بزرگ‌تر باشد.

---

# 192. Card Scene — Love Map

Map card نباید نقشه واقعی سنگین را داخل خود embed کند.

بهتر است:

```text
abstract route
+ two location nodes
+ central heart
+ distance label
```

باشد.

---

# 193. Card Scene — Letters

Letters card باید یک نامه/پاکت فیزیکی را تداعی کند.

Paper باید:

- matte
- warm
- slightly textured

باشد.

یک rose/flower accent در foreground کافی است.

---

# 194. Card Scene — Videos

Video card باید مانند mini cinema desk دیده شود.

عناصر:

- central screen
- two film reels or cinematic props
- play icon
- tiny control line

در screenshot screen مهم‌ترین object این card است.

---

# 195. Card Scene — Personal Message

Personal Message card باید حس خصوصی‌تر داشته باشد.

Visual anchor می‌تواند:

- glass flower dome
- illuminated rose
- message card

باشد.

متن نباید بیش از 4–6 خط در preview باشد.

---

# 196. Card Vertical Rhythm

داخل هر card به‌طور کلی:

```text
Top 15–20%    → title/subtitle
Middle 55–65% → main visual scene
Bottom 15–20% → CTA/meta
```

این ratio باید تقریباً ثابت بماند.

---

# 197. Card Decorative Layers

در هر card حداکثر 3–5 decorative cluster کافی است.

مثلاً:

```text
2 hearts
2 petals
1 bokeh
```

نه ده‌ها آبجکت.

---

# 198. Lower Continuation

بعد از 6 cards، صفحه می‌تواند یک message line احساسی داشته باشد تا Home ناگهان تمام نشود.

این بخش باید کوتاه باشد.

---

# 199. Visual Continuity Test

یک تست ساده:

صفحه را از فاصله دور یا با blur نگاه کن.

باید شبیه یک scene پیوسته باشد.

اگر مرز cardها باعث شود 6 مستطیل مستقل دیده شوند، background integration کافی نیست.

---

# 200. Color Family — baseline

Palette اولیه می‌تواند در محدوده:

```text
Near-black plum
Deep violet
Muted burgundy
Dusty rose
Soft pink
Warm cream
```

باشد.

از:

```text
pure black
pure white
electric magenta
neon purple
```

به‌صورت گسترده استفاده نکن.

---

# 201. Glow Hierarchy

سه سطح glow:

```text
G1 subtle ambient
G2 interactive accent
G3 focal highlight
```

G3 فقط برای عناصر بسیار مهم مانند heart/CTA/selected photo استفاده شود.

---

# 202. Material Hierarchy

چهار material اصلی:

```text
paper
photo
glass
soft fabric/object
```

هرکدام باید رفتار نور متفاوت داشته باشند.

---

# 203. Paper ≠ Glass

Book/letters:

- matte
- diffuse

Glass:

- translucent
- reflective edge

Photo:

- flatter
- sharp

این تفاوت باعث realism می‌شود.

---

# 204. Background Blur

Background elements دور باید blur بیشتری داشته باشند.

Foreground accents sharp‌تر.

این ساده‌ترین depth cue بدون physics سنگین است.

---

# 205. Lens-like Depth

از bloom/blur به‌اندازه استفاده کن؛ هدف cinematic است، نه overprocessed.

---

# 206. Avoid “AI image pasted into page” effect

اگر decorative object با تصویر آماده ساخته شد، باید:

- mask/cutout مناسب
- shadow
- scale
- perspective
- ambient integration

داشته باشد تا به صحنه متصل شود.

---

# 207. Composition Before Content

در reference recreation، اول geometry را درست کن، سپس متن و عکس را وارد کن.

نباید به دلیل طول متن واقعی، layout را از نو خراب کرد.

---

# 208. Content-safe constraints

برای هر slot، حداکثر طول محتوا define شود.

مثلاً:

```text
Hero title: 2 lines
Hero subtitle: 3 lines
Card title: 1–2 lines
Card subtitle: 1–2 lines
CTA: 1 short line
```

اگر محتوا طولانی بود، excerpt نمایش داده شود.

---

# 209. Focal Point Data

هر image asset می‌تواند:

```text
focal_x
focal_y
```

داشته باشد.

اگر null:

- auto focal detection
- center fallback

اجرا شود.

---

# 210. Reference Layout Tokens

این مقادیر به‌صورت token ذخیره شوند:

```text
--reference-hero-min-height
--reference-book-width
--reference-grid-gap
--reference-card-radius
--reference-header-height
--reference-content-max-width
```

این کار visual tuning را بسیار سریع‌تر می‌کند.


# ULTRA-DETAILED ADDENDUM — بخش دوم: Interaction، صفحه‌های داخلی، سه‌بعدی، Motion و تجربه کاربری

# 211. صفحه Gallery نباید صرفاً ادامه Home باشد

Gallery باید حس ورود به «اتاق عکس‌های واقعی» را ایجاد کند.

Hero صفحه Gallery می‌تواند یک stack از عکس‌های منتخب داشته باشد و بعد کاربر با scroll وارد مجموعه شود.

ساختار پیشنهادی:

```text
Gallery Hero
↓
Filter / Mode controls
↓
Featured Memory Stack
↓
Timeline / Memory groups
↓
Photos
↓
Fullscreen viewer
```

کنترل‌های Gallery باید کم و شیک باشند؛ از toolbar شلوغ اجتناب شود.

---

# 212. Gallery Mode Switcher

سه حالت اصلی:

```text
Cinematic
Timeline
Stacks
```

در UI بهتر است به جای متن طولانی، icon + label کوتاه استفاده شود.

حالت فعال با همان pink glow ملایم مشخص شود.

---

# 213. Cinematic Masonry

در این حالت:

- portraitها فضای عمودی بیشتری داشته باشند.
- landscapeها پهن‌تر باشند.
- فاصله‌ها یکنواخت ولی بیش‌ازحد زیاد نباشند.
- card background مستقل برای هر عکس استفاده نشود مگر برای caption.

هدف:

`gallery as flowing wall of memories`

---

# 214. Timeline Gallery

هر گروه عکس با:

```text
Date / unknown
Event title
small description
photo rail
```

نمایش داده شود.

اگر date وجود ندارد، event همچنان در ترتیب manual ظاهر شود.

---

# 215. Memory Stack Interaction

در Stack:

```text
front photo
+ 2–4 rear photos
```

هر click:

- top photo کنار برود.
- next photo جلو بیاید.
- stack کم‌کم reveal شود.

برای جلوگیری از حرکت‌های تصادفی، sequence deterministic باشد.

---

# 216. Photo Detail Panel

در lightbox یا side panel می‌توان:

```text
Memory
Date
Place
Caption
Favorite
```

را نمایش داد.

اما metadata فقط اگر approved باشد نمایش داده شود.

---

# 217. Fullscreen Viewer Keyboard Controls

Desktop:

```text
Esc → close
← → previous
→ → next
+ → zoom in
- → zoom out
Space → play/pause slideshow (optional)
```

---

# 218. Slideshow Mode

Slideshow باید optional باشد و user control داشته باشد.

فاصله بین عکس‌ها باید آرام و cinematic باشد.

موسیقی می‌تواند background soundtrack باشد.

---

# 219. Photo Transition Types

برای gallery از transitionهای زیر استفاده شود:

```text
fade
soft scale
slide
stack reveal
```

حداکثر یکی از این‌ها در هر mode غالب باشد.

همه را همزمان ترکیب نکن.

---

# 220. Story Page — visual chaptering

داستان رابطه بهتر است به chapter تقسیم شود:

```text
Chapter 01
Chapter 02
Chapter 03
...
```

اما اگر داده واقعی chapterها موجود نیست، نباید chapter جعلی تولید شود.

---

# 221. Story Chapter Card

هر chapter می‌تواند:

- cover photo
- title
- short note
- date

داشته باشد.

روی hover:

- image scale بسیار کم
- ambient glow

---

# 222. Story Reading Mode

برای متن‌های طولانی، یک reading mode با عرض محدود ایجاد شود.

حداکثر عرض متن:

`60–75ch`

تا خواندن راحت باشد.

---

# 223. Story Media Placement

در متن داستان، عکس‌ها باید گاهی:

- left aligned
- right aligned
- centered

باشند، اما placement از block schema بیاید.

---

# 224. Letter Viewer — تجربه باز شدن نامه

روی صفحه Letter list:

```text
envelope card
↓ click
seal glow
↓
envelope opens
↓
paper slides out
↓
letter unfolds
```

animation حدود 700–1200ms می‌تواند باشد و باید graceful باشد.

---

# 225. Letter Paper Animation

Paper نباید ناگهان ظاهر شود.

بهتر:

```text
translateY(15px)
opacity(0)
scale(0.98)
→ final
```

و سپس text fade-in.

---

# 226. Letter Typography

Letter body:

- line-height باز
- width محدود
- font serif/readable یا handwriting-like فقط اگر readability مناسب باشد.

---

# 227. Letter Sender Indicator

در بالای نامه:

```text
از طرف: متین
برای: نگار
```

یا برعکس.

این fieldها dynamic باشند.

---

# 228. Letter Optional Seal

Seal می‌تواند:

- heart
- initials
- simple monogram

باشد.

از emblem پیچیده و شلوغ اجتناب شود.

---

# 229. Video Gallery — cinematic room

صفحه ویدیوها بهتر است حس یک اتاق سینما بدهد.

اجزای اصلی:

```text
hero screen
video cards
film-strip motif
selected video viewer
```

پس‌زمینه تیره بماند.

---

# 230. Video Card

هر card:

- poster
- play icon
- title
- optional duration

داشته باشد.

Duration فقط در صورت وجود metadata معتبر نمایش داده شود.

---

# 231. Video Lightbox

وقتی video باز شد:

- screen centered
- controls native یا custom minimal
- close واضح

استفاده شود.

---

# 232. Music Page — immersive player

Music page باید علاوه بر global player یک visual scene داشته باشد:

- album art
- ambient light
- waveform/visualizer بسیار ملایم
- track list

اما visualizer باید کم‌حجم باشد.

---

# 233. Music Visualizer

اگر وجود داشت:

- particle/wave motion محدود
- low frequency update
- no giant bars

---

# 234. Persistent Player Bar

در پایین یا گوشه صفحه می‌توان mini player قرار داد.

این player باید:

- جمع‌وجور
- dismissible

باشد و مزاحم محتوا نشود.

---

# 235. Global Audio State

Stateهایی مانند:

```text
currentTrack
isPlaying
currentTime
volume
muted
queue
```

در یک module واحد نگهداری شوند.

---

# 236. Audio Error Handling

اگر فایل آهنگ load نشد:

```text
پخش این آهنگ ممکن نیست.
```

و گزینه انتخاب آهنگ دیگر.

موسیقی‌های دیگر همچنان usable باشند.

---

# 237. Love Map — Visual Interaction

در map page:

- نقاط با pulse کوچک
- مسیر با line glow
- hover روی نقطه → tooltip
- click → place panel

---

# 238. Map Route Animation

اگر route بین دو یا چند نقطه وجود دارد، می‌توان line را با stroke-dash animation ظاهر کرد.

اما animation فقط اولین بار یا هنگام focus اجرا شود.

---

# 239. Map Accessibility

هر location باید fallback list نیز داشته باشد.

پس اگر map library fail شد:

```text
Place list
```

نمایش داده شود.

---

# 240. Abstract Home Map

Home map preview می‌تواند کاملاً SVG/CSS باشد و از map library مستقل باشد.

هدف visual fidelity است، نه نقشه جغرافیایی کامل.

---

# 241. Timeline Scroll Mechanics

Timeline می‌تواند vertical باشد تا RTL/موبایل نیز ساده‌تر شود.

Desktop می‌تواند با zig-zag card placement جذاب‌تر شود.

---

# 242. Timeline Marker

هر marker:

- circular node
- heart/initial
- glow

داشته باشد.

Selected marker:

- larger
- brighter

---

# 243. Timeline Focus Mode

با click روی event:

- viewport به event scroll کند.
- card expand شود.
- supporting photos ظاهر شوند.

---

# 244. Timeline Progress

یک progress indicator ظریف می‌تواند نشان دهد کاربر کجای timeline است.

اما نباید به progress bar معمولی شبیه شود.

---

# 245. Page Background Parallax

هر صفحه می‌تواند یک ambient parallax background داشته باشد.

این movement باید در بازه بسیار کم باشد:

```text
translateX/Y ≈ 1–2%
```

---

# 246. Mouse Parallax

Desktop only:

```text
pointer position
→ normalized coordinates
→ tiny layer shifts
```

برای touch disable.

---

# 247. Cursor Effect

در desktop یک cursor glow بسیار ضعیف می‌توان داشت.

اما:

- نباید cursor واقعی را hide کند مگر replacement کامل باشد.
- روی mobile غیر فعال.

---

# 248. Cursor Magnetic Buttons

برای CTAهای اصلی می‌توان magnetic effect بسیار کم داشت.

اگر باعث کاهش performance یا accessibility شد، حذف شود.

---

# 249. Scroll-to-Section

CTAها باید واقعاً route/section صحیح را باز کنند.

هیچ button decorative بدون action نباشد، مگر صراحتاً decoration باشد.

---

# 250. State Preservation on Navigation

اگر user در Gallery filter خاصی بود و به detail رفت، با back تا حد امکان state حفظ شود.

---

# 251. Back Navigation

در صفحات داخلی یک back action ظریف وجود داشته باشد.

ترجیحاً با breadcrumb سنگین جایگزین نشود.

---

# 252. Modal Philosophy

Modalها باید:

- narrow in content
- dark
- rounded
- soft shadow

باشند.

از modalهای سفید استاندارد پرهیز شود.

---

# 253. Dialog Motion

Modal:

```text
overlay fade
content translateY(8px) + opacity
```

و reverse.

---

# 254. Focus Trap

در modal/lightbox focus trap و Escape support رعایت شود.

---

# 255. Scroll Lock

وقتی lightbox باز است:

body scroll lock شود و پس از close restore گردد.

---

# 256. 3D Book Page Turning — detail

برای page flip:

- perspective parent
- transform-origin near spine
- shadow layer
- backface-visibility

استفاده شود.

صفحه نباید از spine دور detach شود.

---

# 257. Book Shadow During Flip

shadow باید با زاویه صفحه تغییر کند.

مثلاً:

```text
flat page → soft shadow
rotating page → elongated shadow
edge-on → narrow dark line
```

---

# 258. Book Interaction Controls

روی Desktop می‌توان:

- left arrow
- right arrow
- page click zones

را داشت.

روی mobile swipe اولویت دارد.

---

# 259. Book Page Index

یک indicator مانند:

```text
03 / 12
```

می‌تواند پایین کتاب باشد، اما بسیار کوچک و subtle.

---

# 260. Book Cover

Cover اصلی می‌تواند عنوان رابطه یا monogram داشته باشد.

وقتی باز می‌شود، صفحه اول باید حس «شروع یک داستان» داشته باشد.

---

# 261. Memory Book Data Model

بهتر است Book و صفحاتش entity مستقل داشته باشند:

```text
MemoryBook
MemoryBookPage
```

هر page:

```text
type
order
title
body
media_ids
background_style
```

---

# 262. Memory Book Admin Builder

مدیر باید بتواند page بسازد با drag/drop:

```text
[+] Add Page
[Photo]
[Text]
[Quote]
[Letter]
[Video]
```

و preview turn-by-turn داشته باشد.

---

# 263. Page Template Gallery

در Admin:

```text
Photo page
Story page
Quote page
Letter page
Collage page
```

به‌صورت visual thumbnails نمایش داده شوند.

---

# 264. No-code Page Composition

کاربر غیر فنی باید با انتخاب template و drag media بتواند Book را تکمیل کند.

---

# 265. Media Multi-select

در photo picker امکان:

- search
- filter
- multi-select

وجود داشته باشد.

---

# 266. Photo Crop Presets for Book

Presets:

```text
Square frame
Portrait frame
Landscape frame
Polaroid
Full bleed
```

---

# 267. Image Orientation Awareness

اگر photo portrait است، Book page نباید آن را به landscape کش دهد.

---

# 268. 3D Photo Plane

در صورت Three.js:

photo plane باید:

- geometry ساده
- texture optimized
- anisotropic filtering فقط در حد لازم

داشته باشد.

---

# 269. 3D Performance Tier

می‌توان tier تعریف کرد:

```text
Tier 1 → full motion
Tier 2 → reduced motion
Tier 3 → static fallback
```

---

# 270. Device Memory Awareness

اگر browser اطلاعات memory/device hints دارد، می‌توان بر اساس آن quality را کم کرد.

اما feature detection نباید mandatory باشد.

---

# 271. WebGL Initialization

WebGL باید بعد از render اولیه DOM تا حد امکان initialize شود، نه اینکه مانع نمایش اولیه متن و navigation شود.

---

# 272. Three.js Scene Cleanup

در unmount/route change:

- geometry dispose
- materials dispose
- textures dispose
- renderer dispose

در صورت استفاده واقعی.

---

# 273. CSS-only fallback

اگر Three.js حذف شد یا fail شد، CSS scene باید structure را حفظ کند.

---

# 274. 3D Object Selection

برای right-side couple object می‌توان asset را از CMS تغییر داد، اما object category باید compatible باشد.

---

# 275. Hero Prop Library

مدیر پیشرفته می‌تواند بین چند prop انتخاب کند:

```text
couple plush
flower dome
lamp scene
photo sculpture
```

ولی default باید reference-like باشد.

---

# 276. Prop Position Controls

در CMS advanced:

```text
x
 y
scale
rotation
brightness
opacity
```

با محدودیت امن.

---

# 277. Prop Preset

بهتر است یک preset ذخیره شود:

`reference_hero_scene`

تا در تغییرات بعدی قابل restore باشد.

---

# 278. Ambient Scene Presets

```text
reference-night
soft-dream
warm-evening
romantic-violet
```

می‌توان تعریف کرد.

---

# 279. Home Scene Background Image

اگر برای background از image composite استفاده می‌شود، آن image باید از assetهای owned/generated باشد.

Reference Screenshot را directly به‌عنوان background نگذار.

---

# 280. CSS Layering

Hero background را ترجیحاً با pseudo-element/layers بساز تا content structure تمیز بماند.

---

# 281. Decorative SVG

خط timeline، قلب‌ها، map path و ornamentها ترجیحاً SVG باشند تا:

- crisp
- scalable

بمانند.

---

# 282. SVG Animation

SVG stroke animations برای:

- route
- heart line
- timeline

می‌توانند استفاده شوند.

---

# 283. SVG Accessibility

Decorative SVGها `aria-hidden=true`.

SVGهای interactive label داشته باشند.

---

# 284. Card Scene Parallax

Inside card فقط حداکثر 2–3 depth layers داشته باشد.

```text
background
mid objects
front focal media
```

---

# 285. Card Scene Enter Animation

وقتی card وارد viewport می‌شود، objects با stagger بسیار کم reveal شوند.

مثلاً:

```text
background → 0ms
mid → 60ms
front → 120ms
text → 180ms
```

---

# 286. Do not animate text independently too much

اگر title و subtitle بیش‌ازحد حرکت کنند، حس premium از بین می‌رود.

---

# 287. Heart Pulse

Heartهای interactive می‌توانند pulse داشته باشند.

Pulse باید subtle باشد:

```text
scale 1 → 1.04 → 1
```

نه scale بزرگ.

---

# 288. Petal Motion

Petals در scroll/idle می‌توانند 2–10px حرکت کنند.

سرعت کم و rotation آرام.

---

# 289. Ambient Bokeh Motion

Bokehها می‌توانند در بازه 10–30px طی چند ثانیه drift کنند.

---

# 290. Animation Randomness

randomness باید deterministic باشد تا screenshot regression خراب نشود.

---

# 291. Animation Disable Toggle

در CMS Theme:

```text
Animation intensity:
Off / Low / Medium / High
```

Default:

`Medium` یا نزدیک به reference.

---

# 292. Mobile Animation Intensity

Mobile default یک level کمتر از desktop باشد مگر device قدرتمند باشد.

---

# 293. Scroll-linked Effects Throttling

محاسبات scroll باید:

- requestAnimationFrame-based
- passive listeners

باشند.

---

# 294. No Layout Thrashing

برای parallax از transform استفاده کن، نه تغییر مکرر top/left.

---

# 295. GPU-friendly Properties

اولویت:

```text
transform
opacity
filter (limited)
```

از تغییر مکرر width/height/top/left در animation پرهیز شود.

---

# 296. Blur Cost

`filter: blur()` و `backdrop-filter` فقط روی تعداد محدود layerها.

---

# 297. Backdrop-filter fallback

اگر پشتیبانی نشد:

background opaque/translucent جایگزین شود.

---

# 298. Font Loading

فونت‌های لازم بهینه load شوند.

از ده‌ها font weight استفاده نکن.

---

# 299. Font Fallback

اگر font اختصاصی load نشد، layout نباید شکسته شود.

---

# 300. Final Interaction Principle

هیچ interactionی نباید فقط برای نمایش مهارت coding اضافه شود.

هر animation باید یکی از این‌ها را بهتر کند:

```text
orientation
emotion
depth
discovery
continuity
```

اگر هیچ‌کدام را بهتر نمی‌کند، حذف شود.


# ULTRA-DETAILED ADDENDUM — بخش سوم: Django CMS، مدیریت بدون کدنویسی، AI Organization، QA و دستور اجرای نهایی

# 301. CMS باید «ابزار ساخت سایت» باشد، نه فرم ثبت اطلاعات

هدف CMS این نیست که چند مدل Django را در Admin نشان دهد.

مدیر باید واقعاً بتواند سایت را مدیریت کند.

بنابراین interface باید سه لایه داشته باشد:

```text
Dashboard
Content Editors
Visual Builder
```

---

# 302. Dashboard — نمای کلی

صفحه Dashboard باید بدون ورود به چند submenu وضعیت را نشان دهد:

```text
عکس‌های سایت             133
خاطرات منتشرشده           X
خاطرات پیش‌نویس            Y
مکان‌ها                     Z
نامه‌ها                     N
ویدیوها                     M
آهنگ‌ها                     K
پیشنهادهای AI در انتظار    W
```

این اعداد باید از DB خوانده شوند.

---

# 303. Dashboard Quick Actions

دکمه‌های سریع:

```text
+ افزودن خاطره
+ افزودن نامه
+ افزودن مکان
+ افزودن ویدیو
+ افزودن آهنگ
بررسی پیشنهادهای AI
ویرایش صفحه اصلی
```

---

# 304. Admin Information Architecture

منوی اصلی CMS:

```text
خانه
├── ویرایش صفحه اصلی
├── پیش‌نمایش
└── نسخه‌ها

خاطرات
├── همه خاطرات
├── گروه‌های پیشنهادی AI
└── خاطرات منتشرشده

رسانه‌ها
├── کتابخانه عکس
├── گروه‌های مشابه
└── تصاویر بدون استفاده

داستان

Timeline

نقشه عشق

نامه‌ها

فیلم‌ها

موسیقی

پوسته و ظاهر

تنظیمات

پشتیبان‌گیری
```

---

# 305. CMS باید فارسی‌محور باشد

کاربر عادی نباید با عباراتی مثل:

```text
ForeignKey
JSONField
SlugField
UUID
```

در UI عمومی روبه‌رو شود.

این جزئیات فقط در Developer/Advanced Mode باشند.

---

# 306. Home Builder — مرحله اول

وقتی وارد Home Builder می‌شویم، ابتدا یک preview بزرگ از Home نمایش داده شود.

کنار یا زیر آن:

```text
ساختار صفحه

Hero
کارت 1
کارت 2
کارت 3
کارت 4
کارت 5
کارت 6
Footer Message
```

---

# 307. Section Selection

با click روی هر بخش، controls همان بخش ظاهر شود.

مثلاً Hero:

```text
عنوان
زیرعنوان
عکس اصلی
عکس جایگزین
نمایش شمارنده
نوع آبجکت سه‌بعدی
```

---

# 308. Live Preview

ترجیحاً editor و preview همزمان باشند.

تغییر title باید در همان صفحه در preview دیده شود.

---

# 309. Undo در Visual Editor

Ctrl/Cmd+Z در editor در حد منطقی پشتیبانی شود.

علاوه بر این:

`لغو آخرین تغییر`

وجود داشته باشد.

---

# 310. Save Draft Auto-save

برای تغییرات طولانی می‌توان autosave داشته باشی، ولی publish نباید خودکار شود.

---

# 311. Publish Guard

قبل از publish:

```text
آیا مطمئن هستید؟

تغییرات:
- عکس Hero
- عنوان کارت خاطرات
- 1 خاطره جدید
```

تأیید شود.

---

# 312. Home Card Editor

هر card باید fieldهای قابل ویرایش داشته باشد:

```text
title
subtitle
cta_label
cta_target
enabled
visual_variant
featured_media
secondary_media
```

---

# 313. Card visual variant باید کنترل‌شده باشد

User باید بتواند مثلاً:

```text
Memories → default / photo-heavy
```

انتخاب کند.

اما نباید به‌راحتی CSS آزاد وارد کند.

---

# 314. Drag Reorder

Drag & Drop باید با indicator واضح نشان دهد drop کجاست.

---

# 315. Accessibility for Drag & Drop

کنار drag handle:

```text
بالا بردن
پایین بردن
```

button نیز وجود داشته باشد.

---

# 316. Media Library — UX

Media Library باید شبیه photo manager مدرن باشد.

Layout:

```text
[search] [filter] [sort]

grid of thumbnails
```

با click:

side panel / modal detail

---

# 317. Media Detail Drawer

نمایش:

```text
Thumbnail large
Filename
Dimensions
File size
Hash
Used in
Tags
Focal point
Status
```

---

# 318. Image Assign UX

از داخل Memory Editor دکمه:

`افزودن عکس`

باید Media Picker را باز کند.

---

# 319. Media Picker

باید:

- grid
- search
- filter
- select multiple

داشته باشد.

---

# 320. Selected Media Tray

پایین picker:

```text
3 عکس انتخاب شده
[ادامه]
```

نمایش داده شود.

---

# 321. Reorder Selected Media

بعد از انتخاب، عکس‌ها در یک tray قابل reorder باشند.

---

# 322. Cover Selection

با یک heart/star یا button:

`قرار دادن به‌عنوان کاور`

---

# 323. Favorites vs Cover

این دو state جدا باشند.

```text
favorite = user preference
cover = presentation role
```

---

# 324. AI Grouping UI — نمای اصلی

صفحه AI Groups باید شامل:

```text
Suggested Group #01
9 images
Strong suggestion
```

و thumbnails باشد.

---

# 325. Group Confidence Visualization

به‌جای تنها عدد:

```text
قوی      ████████░░
```

استفاده شود، همراه متن.

---

# 326. Group Reason Chips

مثلاً:

```text
Visual similarity
Filename proximity
Sequence proximity
Near duplicate
```

با معادل فارسی در UI.

---

# 327. Group Action Bar

هر group:

```text
تأیید گروه
رد گروه
ادغام
تفکیک
انتخاب کاور
نام‌گذاری
```

---

# 328. Multi-group Review

مدیر بتواند چند گروه را انتخاب کند و:

`تأیید همه انتخاب‌شده‌ها`

انجام دهد.

---

# 329. Review Status

هر group:

```text
pending
approved
rejected
edited
```

---

# 330. AI Suggestion Lifecycle

```text
generated
↓
reviewed
↓
approved/rejected
↓
materialized as event (if approved)
↓
published manually
```

---

# 331. AI Suggestion باید از Memory Event جدا باشد

تا زمانی که approve نشده:

```text
AISuggestion ≠ MemoryEvent
```

این separation بسیار مهم است.

---

# 332. Materialization

با `Approve & Create Memory`:

AISuggestion به یک draft MemoryEvent تبدیل شود.

بعد مدیر:

- title
- date
- place
- story

را تکمیل کند.

---

# 333. AI Group Split UX

روی group:

`تفکیک گروه`

را بزن.

سپس یک interface دو ستونه:

```text
CURRENT GROUP     NEW GROUP
[photos]          [photos]
```

با drag بین دو ستون.

---

# 334. AI Group Merge UX

دو یا چند group select → merge preview.

سیستم duplicate را flag کند ولی هیچ عکس را auto-delete نکند.

---

# 335. Near Duplicate UI

یک صفحه ویژه:

```text
Near Duplicate Candidates

A [image]    B [image]
Similarity high

[Keep both] [Mark duplicate]
```

---

# 336. Exact Duplicate UI

برای exact duplicate:

```text
Byte-identical files detected
```

نمایش بده و به user اجازه تصمیم بده.

---

# 337. Asset Status Vocabulary

استاندارد واحد:

```text
Imported
Processed
In Use
Unused
Duplicate Candidate
Hidden
Archived
```

---

# 338. AI Confidence Is Not Truth

در همه جا اگر confidence نمایش داده شد، یک tooltip کوتاه داشته باشد:

> این عدد میزان اطمینان سیستم در پیشنهاد فعلی است و به معنی قطعی‌بودن واقعیت خاطره نیست.

---

# 339. AI Source Badge

روی suggestion badge:

```text
AI
Heuristic
Manual
EXIF
Filename
```

نمایش داده شود.

---

# 340. AI Model Cost Control

Settings:

```text
Enable semantic embeddings
Enable captioning
Enable visual tagging
```

هر کدام مستقل باشد.

---

# 341. Batch Processing

اگر provider امکان batch دارد، 133 تصویر را منطقی batch کن.

---

# 342. Cache Embeddings

Embedding یک فایل اگر hash unchanged است دوباره ساخته نشود.

---

# 343. Cache Key

حداقل:

```text
sha256 + model_name + model_version
```

---

# 344. Model Version Change

اگر model version عوض شد، embeddings قبلی invalidated یا versioned شوند.

---

# 345. Pipeline Run Registry

یک entity مانند:

`AIProcessingRun`

داشته باش.

fieldها:

```text
id
provider
model
config_json
started_at
finished_at
status
input_count
success_count
failure_count
```

---

# 346. Pipeline Run Detail

در admin بتوان log یک run را دید:

```text
Run #12
Status: Completed
133 assets
0 failures
17 groups suggested
```

فقط اگر واقعاً چنین runی اجرا شده باشد.

---

# 347. AI Processing Error Details

برای failure:

```text
asset
stage
error type
retry count
final status
```

---

# 348. Retry Policy

خطای transient:

```text
retry 1
retry 2
retry 3
```

بعد failed.

خطای invalid file نباید بی‌نهایت retry شود.

---

# 349. Cancel Job

Admin باید بتواند job سنگین را cancel کند.

---

# 350. Resume Job

پس از cancel یا failure:

`ادامه اجرا`

تا حد امکان از checkpoint قبلی ادامه دهد.

---

# 351. AI Cluster Reconciliation

وقتی clustering جدید اجرا می‌شود، سیستم باید بین clusterهای قبلی و جدید reconciliation انجام دهد یا لااقل هر run را version جدا نگه دارد.

---

# 352. Never silently replace reviewed groups

اگر یک group قبلاً human-approved شده است:

run جدید نباید آن را بدون explicit action تغییر دهد.

---

# 353. Manual Event Lock

روی Event می‌توان:

`قفل ویرایش خودکار`

داشت.

وقتی فعال شد، AI نباید metadata آن را auto-update کند.

---

# 354. AI Suggestions on Published Event

می‌توان suggestion جدید تولید کرد، ولی باید به‌صورت:

`Suggested update`

جدا بماند.

---

# 355. Content Diff for AI Suggestion

مثلاً:

```text
Current title:
غروب آرام

AI suggestion:
یک عصر آرام کنار دریا

[Keep current] [Use suggestion] [Edit]
```

---

# 356. Narrative Style Settings

اگر AI text generation enabled شد، style options:

```text
Simple
Warm
Poetic
Minimal
```

وجود داشته باشد.

اما output همیشه draft باشد.

---

# 357. Prompt Grounding

برای تولید text از context محدود استفاده شود:

```text
approved facts
manual notes
approved place
approved date
```

نه کل database.

---

# 358. Do not expose unrelated private content to AI

وقتی برای یک Memory summary تولید می‌شود، فقط asset/context همان Memory و داده‌های مجاز ارسال شود.

---

# 359. External AI Consent

اگر external provider فعال شد، یک confirmation:

> «ممکن است تصاویر انتخاب‌شده برای تحلیل به سرویس خارجی ارسال شوند.»

و setting در دسترس باشد.

---

# 360. Local-only Mode

در local-only:

- no external image upload
- no external caption calls

---

# 361. Sensitive Media Flag

مدیر بتواند asset را:

`حساس / فقط داخلی`

علامت بزند.

AI external باید این assetها را نادیده بگیرد مگر override explicit.

---

# 362. Media Watermark — optional

برای public preview در صورت نیاز می‌توان watermark ظریف داشت، ولی default نباید با زیبایی reference تداخل داشته باشد.

---

# 363. Photo Download Policy

در public lightbox:

- download button می‌تواند disabled باشد.
- original URL هرگز مستقیم لو نرود.

---

# 364. Screenshot Protection

کاربر نمی‌تواند از screenshot گرفتن به‌طور کامل منع شود؛ بنابراین به‌جای وعده امنیت مطلق، روی access control و URL protection تمرکز کن.

---

# 365. Admin Session Safety

بعد از inactivity طولانی:

logout یا re-authentication قابل تنظیم باشد.

---

# 366. Audit Log UI

مدیر بتواند تغییرات را با filter:

```text
Content
Media
AI
Theme
Auth
```

ببیند.

---

# 367. Audit Log Human-readable

به‌جای:

`PATCH /api/home/17`

نمایش:

`عکس اصلی Hero تغییر کرد.`

---

# 368. Backup Schedule

برای private site می‌توان backup روزانه/هفتگی configurable داشت.

---

# 369. Backup Verification

صرفاً backup گرفتن کافی نیست؛ حداقل periodically restore test انجام شود.

---

# 370. Disaster Recovery

Documentation باید بنویسد اگر database یا media از بین رفت چگونه restore شود.

---

# 371. Export Without Secrets

Export content نباید secret key یا API key را داخل خود داشته باشد.

---

# 372. Admin Media Re-encode

امکان regenerate derivatives در صورت تغییر algorithm.

---

# 373. Image Quality Profiles

مثلاً:

```text
web-fast
balanced
high-quality
```

اما default با توجه به performance انتخاب شود.

---

# 374. Preserve Original Quality

هیچ re-encode نباید original را overwrite کند.

---

# 375. WebP/AVIF Strategy

می‌توان derivative را به WebP/AVIF ساخت ولی JPG original حفظ شود.

---

# 376. Format Negotiation

در صورت امکان:

```text
AVIF → WebP → JPG
```

با fallback.

---

# 377. Picture Element

برای responsive image از `<picture>` و `srcset` استفاده کن هرجا مفید است.

---

# 378. Home Image Priority

فقط critical imagery اول load شود.

بقیه lazy.

---

# 379. Avoid Layout Shift

برای هر image container aspect-ratio از پیش مشخص شود.

---

# 380. CLS Protection

وجود image dimension attributes یا aspect ratio ضروری است.

---

# 381. LCP Awareness

Hero باید طوری ساخته شود که مهم‌ترین visual سریع render شود، ولی به قیمت load کردن فایل original چند مگابایتی نباشد.

---

# 382. CSS Background vs `<img>`

برای عکس‌های محتوایی بهتر است `<img>` باشد تا:

- accessibility
- responsive source
- lazy load

بهتر مدیریت شود.

Background image برای decorative scene acceptable است.

---

# 383. Image Semantics

اگر تصویر محتوای خاطره است، `<figure>` / caption مناسب در نظر بگیر.

---

# 384. Memory Card Accessibility

Entire card قابل focus باشد، ولی nested buttonهای بدون semantics نساز.

---

# 385. Keyboard Navigation Order

ترتیب focus باید با visual reading order همخوان باشد.

---

# 386. RTL Tab Order

صرفاً mirror کردن CSS نباید باعث tab order عجیب شود.

---

# 387. Screen Reader Text

برای icon-only buttonها aria-label:

```text
پخش موسیقی
بستن
عکس بعدی
عکس قبلی
```

---

# 388. Reduced Motion in CMS Preview

Editor باید بتواند preview کند که سایت با reduced motion چگونه دیده می‌شود.

---

# 389. Theme Safe Mode

اگر Theme custom باعث مشکل شد:

`بازگشت به پوسته مرجع`

وجود داشته باشد.

---

# 390. Reference Preset Immutable Snapshot

یک نسخه baseline از Reference Theme نگه دار که هر زمان بتوان به آن برگشت.

---

# 391. Design Tokens Export

Theme settings قابل export باشند.

---

# 392. Design Tokens Import

نسخه بعدی سایت بتواند یک theme JSON را import کند.

---

# 393. Version Compatibility

Theme schema version داشته باشد.

---

# 394. Future AI-generated Design Changes

اگر در آینده AI بخواهد theme را تغییر دهد، بهتر است فقط tokenهای مجاز را تغییر دهد، نه HTML/CSS آزاد.

---

# 395. Agent Editing Guardrails

یک AI Coding Agent آینده باید بتواند به راحتی تشخیص دهد که:

```text
content change
≠
layout change
```

و برای تغییر content نیاز نباشد template را edit کند.

---

# 396. CSS Class Naming

کلاس‌ها semantic و stable باشند.

مثلاً:

```text
home-hero
home-card--memories
memory-book__page
```

و نه:

```text
box17
pinkthing
new2
```

---

# 397. No Giant Single HTML File

Home نباید 3000 خط HTML در یک فایل باشد.

---

# 398. No Giant Single JS File

موتور music، gallery، 3D و CMS را در یک فایل هزاران خطی قرار نده.

---

# 399. CSS Token Governance

هر رنگ اصلی فقط یک یا چند token مرکزی داشته باشد.

---

# 400. Component Contract Tests

اگر component ورودی ناقص گرفت، graceful fallback داشته باشد.

---

# 401. Final Architecture Target

معماری مطلوب:

```text
                    ┌──────────────────┐
                    │  Public Website  │
                    └────────┬─────────┘
                             │
                    Django Views / API
                             │
              ┌──────────────┴──────────────┐
              │                             │
        Content/CMS                    Media Services
              │                             │
        PostgreSQL                     Files/Storage
              │                             │
              └──────────────┬──────────────┘
                             │
                    AI Organizer Layer
                             │
           ┌─────────────────┼─────────────────┐
           │                 │                 │
         Hashes          Embeddings        Optional AI
           │                 │                 │
           └─────────────────┴─────────────────┘
                             │
                       Human Review
```

---

# 402. Public / Admin Separation

Public frontend نباید implementation detailهای Admin را import کند.

Admin bundle جدا و در صورت امکان فقط در admin routes load شود.

---

# 403. API Surface حداقل نگه داشته شود

برای پروژه کوچک، API زیاد و پیچیده لازم نیست.

HTMX/Django views در بسیاری از موارد کافی‌اند.

---

# 404. Server-render first

Home باید بدون JavaScript سنگین حداقل skeleton محتوایی قابل render داشته باشد.

---

# 405. Progressive Enhancement

اگر JS fail شد:

- navigation کار کند.
- links کار کنند.
- photos قابل مشاهده باشند.
- content قابل خواندن باشد.

3D و fancy interactions optional enhancement باشند.

---

# 406. No JS dependency for basic content

Letter body یا title نباید فقط بعد از JS render شود اگر لازم نیست.

---

# 407. Navigation URL Stability

URLهای اصلی stable باشند.

---

# 408. Slug Editing Safety

تغییر slug باید redirect یا alias قبلی را نگه دارد تا link شکسته نشود.

---

# 409. Draft Preview Token

Preview draft با token/session امن انجام شود.

---

# 410. Admin Preview Must Use Same Renderer

Preview و Public باید تا حد امکان از همان rendering code استفاده کنند تا اختلاف ایجاد نشود.

---

# 411. Final QA — User-facing checklist

در browser واقعی:

```text
open home
check header
check music
check hero
check book
check image
check counter
scroll
check six cards
open every card
open gallery
open timeline
open map
open letter
open video
switch music
resize viewport
```

---

# 412. Final QA — Admin checklist

```text
login
change hero image
change hero title
reorder card
create memory
assign 3 images
merge groups
split group
approve suggestion
publish draft
unpublish content
restore previous version
export backup
```

---

# 413. Final QA — AI checklist

```text
run inventory
run hash detection
run near duplicate
run embeddings
run clustering
review groups
rerun
verify reviewed content unchanged
inspect provider/model log
```

---

# 414. Final QA — Privacy checklist

```text
unauthenticated media request
unauthenticated draft page
robots indexing
direct original URL
AI external upload setting
admin route protection
```

---

# 415. Final QA — Responsive checklist

At:

```text
1536×1024
1440×900
1280×800
1024×768
768×1024
430×932
390×844
```

بررسی شود:

- overflow
- clipping
- broken text
- broken book
- card collision
- navigation collision

---

# 416. Final QA — Visual checklist per screenshot

### Header

```text
□ right identity capsule
□ central nav
□ left music button
□ correct vertical spacing
□ active home capsule
```

### Hero

```text
□ large open book
□ central spine
□ page depth
□ actual couple photo
□ Polaroid
□ petals
□ right couple object
□ counter card
□ warm background prop
```

### Grid

```text
□ exact 3×2 topology
□ thin borders
□ rounded cards
□ correct visual order
□ six scene-specific compositions
```

---

# 417. Reference Card Order Acceptance

Desktop visual order must remain:

```text
TOP:
[ Story ] [ Memories ] [ Love Map ]

BOTTOM:
[ Letters ] [ Videos ] [ Personal Message ]
```

توجه: در RTL باید placement دیداری با slot mapping کنترل شود تا این ترتیب دقیقاً با reference یکی باشد.

---

# 418. Card-to-page Mapping

```text
Story card       → /story/
Memories card    → /memories/
Love Map card    → /map/
Letters card     → /letters/
Videos card      → /videos/
Message card     → /story/message/ یا route مناسب
```

route نهایی قابل تنظیم است، اما action باید واقعی باشد.

---

# 419. No Dead Buttons

در نسخه نهایی هیچ CTA با click بدون نتیجه نداشته باش.

اگر section هنوز ساخته نشده، button نباید public شود.

---

# 420. Final Content Freeze Before Delivery

قبل از delivery:

- sample placeholders را پیدا کن.
- demo text را پیدا کن.
- fake data را پیدا کن.
- test files را پیدا کن.

و هیچ موردی بدون آگاهی مدیر در public باقی نماند.

---

# 421. Search for Hardcoded Reference Placeholder Text

Agent باید در codebase search کند برای textهایی مانند:

```text
داستان ما
خاطرات ما
365 روز
8760 ساعت
```

و تعیین کند کدام مورد:

- static UI label
- placeholder
- dynamic content

است.

اعداد واقعی counter نباید hard-code بمانند.

---

# 422. Hardcoded Position Audit

بررسی کن که CSS برای reference geometry بیش‌ازحد brittle نباشد.

مثلاً صدها absolute coordinate غیرقابل responsive ممنوع.

---

# 423. Allowed Absolute Positioning

در Hero scene برای decorative objects و book positioning، absolute positioning قابل قبول است.

اما باید component-scoped و responsive باشد.

---

# 424. Container Query / Clamp

برای responsive tuning استفاده از:

- clamp
- min/max
- container query

در صورت نیاز توصیه می‌شود.

---

# 425. Screenshot scaling

Reference را به عنوان composition ratio استفاده کن، نه اینکه یک `transform: scale()` کل سایت را بر اساس 1536px بسازد.

---

# 426. Anti-pattern: Entire App Scale

ممنوع:

```css
body {
  transform: scale(...)
}
```

یا مشابه آن برای تقلید Screenshot.

---

# 427. Anti-pattern: giant canvas screenshot reconstruction

ممنوع:

- giant canvas واحد
- clickable image hotspots

به‌جای DOM واقعی.

---

# 428. Semantic Content Must Remain Searchable in DOM

Title و body باید text واقعی باشند، نه text baked into image.

---

# 429. Text in 3D scene

اگر عنوان داخل Hero روی HTML overlay باشد، باید با Scene هماهنگ شود ولی selectable/readable بماند.

---

# 430. Reference-like without brittle pixel copy

بهترین روش:

```text
semantic HTML
+ CSS geometry
+ SVG decorative vectors
+ limited 3D
+ real media
+ data-driven content
```

---

# 431. Final Build Order — دقیق‌تر

Agent باید:

```text
PHASE 0
read reference + this file

PHASE 1
scan archive

PHASE 2
create Django project

PHASE 3
create models/migrations

PHASE 4
create media pipeline

PHASE 5
create AI organizer

PHASE 6
create CMS

PHASE 7
build reference Home

PHASE 8
build immersive pages

PHASE 9
integrate real content

PHASE 10
visual QA

PHASE 11
security QA

PHASE 12
performance QA

PHASE 13
document + package
```

---

# 432. Phase 0 — Mandatory Reading

قبل از coding:

1. کل این فایل را بخوان.
2. Screenshot را inspect کن.
3. ZIP را inspect کن.
4. dependency choices را مستند کن.

---

# 433. Phase 1 — Asset Audit Evidence

فایل‌های خروجی:

```text
reports/asset_manifest.json
reports/asset_dimensions.csv
reports/contact_sheet.jpg
reports/duplicate_report.json
```

---

# 434. Phase 2 — Architecture Evidence

فایل:

`ARCHITECTURE.md`

باید تصمیمات را ثبت کند.

---

# 435. Phase 3 — Data Evidence

migration files + seed/import command.

---

# 436. Phase 4 — Media Evidence

مطمئن شو original و derivative جدا هستند.

---

# 437. Phase 5 — AI Evidence

حداقل:

```text
AI run log
cluster result
review state
```

---

# 438. Phase 6 — CMS Evidence

یک راهنمای تصویری/متنی کوتاه برای عملیات مهم.

---

# 439. Phase 7 — Home Evidence

Screenshot output از `1536×1024`.

---

# 440. Phase 8 — Page Evidence

Screenshot هر صفحه اصلی در حداقل یک viewport.

---

# 441. Phase 9 — Real Content Evidence

نشان بده که assetهای واقعی archive در UI استفاده شده‌اند، نه فقط placeholders.

---

# 442. Phase 10 — Visual QA Evidence

یک report مانند:

```text
Header: aligned
Hero: tuned
Book: tuned
Counter: tuned
Grid: tuned
```

اما فقط پس از مقایسه واقعی.

---

# 443. Phase 11 — Security Evidence

نتایج تست دسترسی private media.

---

# 444. Phase 12 — Performance Evidence

حداقل:

```text
Home asset weight
JS size
number of requests
largest images
3D status
```

---

# 445. Phase 13 — Delivery Bundle

تحویل:

```text
love-site/
├── source
├── docs
├── tests
├── scripts
├── reports
├── .env.example
├── README.md
└── deployment files
```

---

# 446. Final Agent Report — قالب دقیق

Agent باید در پایان این template را پر کند:

```text
PROJECT: Matin & Negar Love Site

Reference:
1536×1024 screenshot

Backend:
Django + PostgreSQL

Archive:
133 images discovered

Import:
[real result]

Duplicates:
[real result]

AI Clusters:
[real result]

Human Review:
[real result]

Home:
Implemented / Partial / Blocked

CMS:
Implemented / Partial / Blocked

Memory Book:
Implemented / Partial / Blocked

Gallery:
Implemented / Partial / Blocked

Timeline:
Implemented / Partial / Blocked

Map:
Implemented / Partial / Blocked

Letters:
Implemented / Partial / Blocked

Videos:
Implemented / Partial / Blocked

Music:
Implemented / Partial / Blocked

Privacy:
[real result]

Performance:
[real result]

Tests:
[real result]

Visual QA:
[real result]

Known limitations:
[explicit]
```

---

# 447. Final Non-fabrication Reporting Rule

اگر یک metric یا feature اندازه‌گیری نشده است، بنویس:

`Not measured`

اگر feature اجرا نشده است، بنویس:

`Not run`

اگر failure وجود دارد، بنویس:

`Failed`

هرگز آن را با:

`Done`

جایگزین نکن.

---

# 448. Final “Looks Good” Prohibition

عبارت‌هایی مانند:

`به نظر خوب می‌رسد`

برای visual QA کافی نیست.

باید evidence وجود داشته باشد:

- screenshot
- inspection
- issue list
- corrected screenshot

---

# 449. Final “Similar Enough” Prohibition

«مشابه است» قابل قبول نیست مگر مشخص شود چه چیزی مقایسه شده است.

مثلاً:

```text
Book position
Counter position
Grid topology
Card density
```

باید explicit بررسی شوند.

---

# 450. Final Strictness Rule

**هرجا این سند یک جزئیات مشخص داده است، Agent حق ندارد آن را با یک abstraction مبهم جایگزین کند.**

مثلاً:

```text
“6 cards”
```

نباید به:

`some cards`

تبدیل شود.

```text
“open book”
```

نباید به:

`book-themed banner`

تبدیل شود.

```text
“editable without coding”
```

نباید به:

`edit database manually`

تبدیل شود.

```text
“AI grouping with human review”
```

نباید به:

`manual upload of every photo`

تبدیل شود.

---

# 451. Final Creative Freedom Boundary

Creative freedom فقط در جاهایی مجاز است که reference specification چیزی را مشخص نکرده است.

مثلاً:

- نوع دقیق مدل 3D داخلی
- library انتخابی برای icon
- ORM abstraction جزئی
- اسم internal service

اما در مواردی مانند:

- composition
- card topology
- visual hierarchy
- CMS editability
- AI review

creative freedom محدود است.

---

# 452. Final Design Principle

**عکس واقعی باید ستاره سایت باشد؛ UI باید قاب آن باشد، نه رقیب آن.**

---

# 453. Final Experience Principle

**حرکت باید خاطره را reveal کند، نه اینکه خودش تبدیل به موضوع اصلی شود.**

---

# 454. Final CMS Principle

**تغییر دادن سایت باید برای صاحب سایت مثل ویرایش یک آلبوم باشد، نه مثل برنامه‌نویسی یک وب‌سایت.**

---

# 455. Final AI Principle

**AI باید زمان سازمان‌دهی 133 تصویر را کم کند، نه اینکه حقیقت رابطه را به جای انسان تعریف کند.**

---

# 456. Final Engineering Principle

**Django برای داده و مدیریت، CSS/HTML برای layout، JS/HTMX برای interaction، Three.js برای depth واقعی، و image pipeline برای media؛ هر تکنولوژی فقط برای مسئله‌ای که واقعاً حل می‌کند.**

---

# 457. Final Visual Principle

**اگر صفحه زیبایی خود را مدیون افکت باشد ولی بدون افکت شبیه Screenshot نباشد، composition کافی دقیق نیست.**

---

# 458. Final Private-Site Principle

این سایت برای تعداد محدودی از افراد است؛ بنابراین:

```text
privacy
simplicity
maintainability
personalization
```

از scale عمومی مهم‌تر هستند.

---

# 459. Final Product Identity

نام محصول می‌تواند:

```text
Matin & Negar
Our Story
Love Archive
Our Memories
```

باشد و از CMS قابل تغییر باشد.

---

# 460. Final Delivery Standard

نسخه‌ای قابل تحویل است که:

```text
واقعی است
قابل اجرا است
قابل مدیریت است
قابل بازگشت است
قابل توسعه است
قابل تست است
خصوصی است
و از نظر بصری به Reference وفادار است
```

---

# 461. FINAL MASTER COMMAND TO THE AI CODING AGENT

> **این پروژه را به‌عنوان یک محصول واقعی و یک reference-driven digital memory experience پیاده‌سازی کن. پیش از نوشتن کد، Screenshot 1536×1024 را دقیقاً بررسی و decomposition کن و archive `imagesoflovesite.zip` را واقعاً scan کن. تمام 133 تصویر را discover، manifest، hash و optimize کن. duplicate و near-duplicate را با روش‌های جدا تحلیل کن و event clustering را با چند signal انجام بده؛ تعداد eventها را از قبل فرض نکن. نتیجه را به‌صورت AI Suggestions بساز و برای هر پیشنهاد confidence، source و reason داشته باش. هیچ تاریخ، مکان، داستان، احساس یا واقعیت شخصی را از روی حدس به‌عنوان fact تولید نکن. human approval برای تبدیل suggestion به content منتشرشده الزامی است. Backend اصلی Django باشد و PostgreSQL برای persistence استفاده شود. CMS سفارشی و فارسی/RTL باشد و فردی که هیچ دانش برنامه‌نویسی ندارد بتواند Hero، عکس‌ها، متن‌ها، کارت‌ها، Timeline، Memory Book، Gallery، Map، Letters، Videos و Music را تغییر دهد. Home Builder باید live preview، drag/drop، draft/preview/publish و version/undo داشته باشد. Home public باید از نظر geometry و visual hierarchy به Screenshot بسیار نزدیک باشد: Header بالایی با identity در راست، navigation مرکزی و music control در چپ؛ Hero با open book بزرگ در چپ/مرکز، Polaroid photo واقعی داخل کتاب، متن Matin/Negar روی صفحه، couple object سه‌بعدی در راست، counter glass روی scene، scroll indicator در مرز Hero؛ و پایین Hero یک grid دقیقاً سه‌ستونه و دو ردیفه با شش miniature scene شامل Story، Memories، Love Map، Letters، Videos و Personal Message. رنگ‌ها باید dark plum/violet/rose با warm highlights باشند؛ glassmorphism، soft glow، depth، shadows، petals، hearts و bokeh باید subtle باشند. Three.js فقط برای depth واقعی و قابل‌دفاع استفاده شود؛ متن‌های اصلی HTML باقی بمانند. تمام media واقعی باید responsive، crop-safe و private باشند. 133 فایل original هرگز overwrite یا خودکار حذف نشوند. external AI upload به‌صورت پیش‌فرض خاموش باشد. قبل از completion، browser screenshots واقعی در viewportهای مشخص تهیه کن، reference comparison انجام بده، issueها را اصلاح کن و فقط چیزهایی را که واقعاً اجرا و بررسی کرده‌ای به‌عنوان completed گزارش کن. اگر چیزی اجرا نشده، explicitly بگو not run/blocked/failed. **هرگز mockup را با implementation، placeholder را با content واقعی، confidence را با truth، یا حدس را با fact اشتباه نگیر.**

---

# 462. LAST WORD

**این پروژه باید در نهایت حس یک خاطره زنده را منتقل کند: کاربر وارد صفحه شود، تصویرهای واقعی خودش را ببیند، بتواند آنها را ورق بزند، داستان را دنبال کند، روی نقشه حرکت کند، نامه را باز کند، فیلم را تماشا کند و موسیقی را انتخاب کند؛ و صاحب سایت بدون نوشتن حتی یک خط کد بتواند همه این خاطرات را در آینده تغییر، مرتب، تکمیل یا دوباره روایت کند. در عین حال، ظاهر Home باید از همان composition مرجع شروع شود و در تمام مراحل توسعه، reference به‌عنوان خط‌کش بصری حفظ شود.**
