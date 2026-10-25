# داشبورد پروژه‌ها — نسخه‌ی GitHub Pages (۸٫۹٫۰)

این پوشه فقط **صفحه‌ی داشبورد** است. همه‌ی داده‌ها (پروژه‌ها، کاربران، وظایف، نامه‌ها، فایل‌ها) همچنان داخل **Google Sheets و Google Drive** شما می‌مانند و سرور همان **Google Apps Script** قبلی است؛ پس با بارگذاری در GitHub هیچ داده‌ای جابه‌جا یا پاک نمی‌شود.

## فایل‌ها
| فایل | کار |
|---|---|
| `index.html` | خود برنامه |
| `config.js` | آدرس سرور (Apps Script). اگر آدرس عوض شد فقط این فایل را ویرایش کنید |
| `manifest.webmanifest`، `icon-192.png`، `icon-512.png` | نصب روی صفحه‌ی اصلی iPad/گوشی |
| `.nojekyll` | (اختیاری) جلوگیری از پردازش Jekyll |

## مراحل (همه از مرورگر iPad)
1. در github.com وارد شوید ← **New repository** ← نام مثلاً `dashboard` ← **Private یا Public** (هر دو کار می‌کند؛ برای Pages در حساب رایگان، مخزن Public لازم است) ← **Create**.
2. **Add file ← Upload files** و این فایل‌ها را انتخاب کنید: `index.html`، `config.js`، `manifest.webmanifest`، `icon-192.png`، `icon-512.png` (و `README.md`). سپس **Commit changes**.
   - اگر ZIP را دارید: ابتدا در برنامه‌ی Files با لمس طولانی «Uncompress» کنید.
3. **Settings ← Pages ← Build and deployment**: Source را روی **Deploy from a branch** بگذارید، Branch = `main` و پوشه‌ی `/ (root)` ← **Save**.
4. حدود یک تا دو دقیقه بعد آدرس `https://نام‌کاربری.github.io/dashboard/` فعال می‌شود.
5. با همان نام کاربری و رمز قبلی وارد شوید. (ورود دوباره لازم است چون آدرس تازه است؛ داده‌ها سر جایشان هستند.)

## شرط‌های سمت Google (فقط یک‌بار بررسی کنید)
- در Apps Script: **Deploy ← Manage deployments ← ✏️ Edit** روی همان استقرار قبلی ← Version = **New version** ← Deploy. (آدرس `/exec` عوض نمی‌شود.)
- تنظیم Web app: **Execute as = Me** و **Who has access = Anyone**.
- فایل `Code.gs` را **در GitHub نگذارید**؛ در آن شناسه‌ی شیت‌ها و `PASSWORD_SALT` هست. آن فقط داخل Apps Script بماند.

## جلوگیری از هر گونه از دست رفتن اطلاعات
- پیش از هر به‌روزرسانی: در Google Sheets **File ← Make a copy** (یک نسخه‌ی پشتیبان).
- هرگز در Apps Script مقدار `PASSWORD_SALT` را عوض نکنید (همه‌ی رمزها باطل می‌شود).
- به‌روزرسانی برنامه = جایگزین کردن `index.html` در GitHub (Upload ← Replace). به شیت‌ها دست نمی‌زند.
- اگر آدرس Apps Script عوض شد، فقط `config.js` را ویرایش کنید.

## عیب‌یابی
- «Failed to fetch» یا خطای شبکه: دسترسی Web app باید «Anyone» باشد و باید یک **New version** Deploy شده باشد.
- صفحه‌ی سفید: آدرس را با `/` پایان بدهید و صفحه را با نگه‌داشتن دکمه‌ی بروزرسانی Safari تازه کنید.
- نصب روی iPad: Safari ← دکمه‌ی Share ← **Add to Home Screen**.
