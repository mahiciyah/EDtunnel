<div align="center">

<img src="https://cloudflare-ipfs.com/ipfs/bafybeigd6i5aavwpr6wvnwuyayklq3omonggta4x2q7kpmgafj357nkcky" alt="edgetunnel" width="180">

# ⚡ EDtunnel

### تانل رایگان و سریع روی زیرساخت Cloudflare — بدون نیاز به سرور اختصاصی

<p>
  <img src="https://img.shields.io/badge/Cloudflare-Workers%20%7C%20Pages-f38020?style=for-the-badge&logo=cloudflare&logoColor=white">
  <img src="https://img.shields.io/badge/Protocol-VLESS-8A2BE2?style=for-the-badge">
  <img src="https://img.shields.io/badge/License-Open%20Source-brightgreen?style=for-the-badge">
</p>

<p>
  <a href="https://github.com/zizifn/edgetunnel"><img src="https://img.shields.io/badge/📦_Original_Repo-GitHub-181717?style=flat-square&logo=github"></a>
  <a href="https://t.me/edtunnel"><img src="https://img.shields.io/badge/💬_Telegram-Join_Channel-26A5E4?style=flat-square&logo=telegram&logoColor=white"></a>
</p>

</div>

---

## 🎯 EDtunnel چیه؟

فرض کن می‌تونی بدون خرید سرور، بدون هزینه، و فقط با یه حساب رایگان Cloudflare، تانل شخصی خودتو بسازی. دقیقاً همین کار رو **EDtunnel** برات انجام می‌ده 😎

این پروژه بر پایه پروتکل **VLESS** ساخته شده و روی سرویس‌های **Cloudflare Workers** و **Cloudflare Pages** اجرا می‌شه. یعنی سریع، رایگان، و در دسترس همه.

> 🔧 نسخه توسعه‌یافته از پروژه [edgetunnel](https://github.com/zizifn/edgetunnel)

---

## 📚 فهرست مطالب

- [🌿 شاخه‌های پروژه](#-شاخه‌های-پروژه)
- [☁️ دیپلوی روی Cloudflare Pages](#️-دیپلوی-روی-cloudflare-pages)
- [⚙️ دیپلوی روی Cloudflare Workers](#️-دیپلوی-روی-cloudflare-workers)
- [😴 برای تنبل‌ها](#-برای-تنبل‌ها)
- [🆔 تنظیم UUID](#-تنظیم-uuid)
- [🔗 لینک اشتراک](#-لینک-اشتراک-vless)
- [🌍 بهترین آی‌پی Cloudflare](#-بهترین-آی‌پی-cloudflare)
- [🔌 پشتیبانی چند پورت](#-پشتیبانی-چند-پورت)
- [🛰 تنظیم proxyIP](#-تنظیم-proxyip)
- [🖥 نحوه استفاده](#-نحوه-استفاده)

---

## 🌿 شاخه‌های پروژه

<div align="center">

| شاخه | کاربرد |
|:---:|:---|
| 🟢 `main` | شاخه اصلی و پایدار پروژه |
| 🔵 `pages` | نسخه ویژه دیپلوی روی Cloudflare Pages |
| 🟣 `vless` / `vless2` | پیاده‌سازی خروجی پروتکل VLESS |
| 🟠 `socks5` / `remote-socks5` | پیاده‌سازی و استخر پروکسی SOCKS5 |
| ⚪ `dns` | توسعه‌های مرتبط با DNS |
| ⚫ `code1` / `code2` | ویژگی‌های در حال توسعه |

</div>

---

## ☁️ دیپلوی روی Cloudflare Pages

سریع‌ترین راه برای شروع 🚀

**۱.** یه ویدیوی آموزشی کامل هست، ببینش:

<div align="center">

[![یوتیوب](https://img.shields.io/badge/▶️_مشاهده_ویدیوی_آموزشی-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/watch?v=8I-yTNHB0aw)

</div>

**۲.** ریپازیتوری رو Fork یا Clone کن و روی Cloudflare Pages دیپلویش کن. همین!

---

## ⚙️ دیپلوی روی Cloudflare Workers

**۱.** فایل `_worker.js` رو از [اینجا](https://github.com/3Kmfi6HP/EDtunnel/blob/main/_worker.js) کپی کن.

**۲.** یا با یه کلیک، مستقیم دیپلویش کن 👇

<div align="center">

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/3Kmfi6HP/EDtunnel)

</div>

---

## 😴 برای تنبل‌ها

حوصله دیپلوی نداری؟ مشکلی نیست، این کانفیگ رایگان Clash.Meta رو داشته باش:

```
aHR0cHM6Ly9vc3MudjJyYXlzZS5jb20vcHJveGllcy9kYXRhLzIwMjMtMDctMzAvRnJFS1lvQS50eHQ=
```

> ⚠️ **هشدار دوستانه:** این یه لینک عمومیه، پس روی پایداری و امنیت بالاش زیاد حساب نکن.

---

## 🆔 تنظیم UUID

UUID همون کلید شخصی توئه؛ بدون اون کسی نمی‌تونه از تانل تو استفاده کنه 🔐

| محل دیپلوی | فایل | نام متغیر |
|:---:|:---:|:---:|
| Cloudflare Pages | `wrangler.toml` | `UUID` |
| Cloudflare Workers | `_worker.js` | `userID` (یا env `UUID`) |

**یه UUID:**
```env
UUID = "uuid-دلخواه-شما"
```

**چند تا UUID با هم:**
```env
UUID = "uuid1,uuid2,uuid3"
```

💡 هر UUID رو با ویرگول جدا کن. بعدش می‌تونی با آدرس `.../uuid1` کانفیگ همون UUID رو بگیری.

---

## 🔗 لینک اشتراک vless://

<div align="center">

| هدف | آدرس |
|:---|:---|
| 📥 دریافت کانفیگ + لینک vless | `edtunnel.pages.dev/uuid-شما` |
| 📄 دریافت محتوای اشتراک | `edtunnel.pages.dev/sub/uuid-شما` |
| 🐟 خروجی فرمت Clash (base64) | `edtunnel.pages.dev/sub/uuid-شما/?format=clash` |

</div>

> 📌 اگه چند UUID داری، فقط اولی توی مسیر `sub` پشتیبانی می‌شه.

---

## 🌍 بهترین آی‌پی Cloudflare

**۱.** این آدرس رو بگیر:
```
edtunnel.pages.dev/bestip/uuid-شما
```

**۲.** توی هر کلاینتی مثل **Clash**، **v2rayN** یا **v2rayNG** به‌عنوان لینک اشتراک وارد کن.

**۳.** تمام! سوالی بود بیا [تلگرام](https://t.me/edtunnel) 🎉

---

## 🔌 پشتیبانی چند پورت

پیش‌فرض: `80` و `443` ✅ ولی می‌تونی از این پورت‌ها هم استفاده کنی:

```diff
+ HTTP:  80, 8080, 8880, 2052, 2086, 2095
+ HTTPS: 443, 8443, 2053, 2096, 2087, 2083
```

📖 لیست کامل: [مستندات رسمی Cloudflare](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/ports)

> ⚠️ روی Cloudflare Pages، پورت‌های HTTPS پشتیبانی نمی‌شن.

---

## 🛰 تنظیم proxyIP

| محل دیپلوی | فایل | نام متغیر |
|:---:|:---:|:---:|
| Cloudflare Pages | `wrangler.toml` | `PROXYIP` |
| Cloudflare Workers | `_worker.js` | `proxyIP` |

`proxyIP` ترافیک رو از یه واسط عبور می‌ده به‌جای اتصال مستقیم به Cloudflare. چون بعضی وقتا اتصال مستقیم TCP به آی‌پی‌های Cloudflare محدود می‌شه، تنظیم این مقدار پیشنهاد می‌شه. [جزئیات بیشتر →](https://developers.cloudflare.com/workers/runtime-apis/tcp-sockets/#considerations)

---

## 🖥 نحوه استفاده

```bash
1️⃣ دامنه Pages خودت رو باز کن:
   https://edtunnel.pages.dev/

2️⃣ UUID خودت رو به انتهای آدرس اضافه کن:
   https://edtunnel.pages.dev/uuid-شما

3️⃣ کانفیگ Clash و لینک vless:// رو بگیر و لذت ببر 🎉
```

---

<div align="center">

## ⭐ Star History

<a href="https://star-history.com/#3Kmfi6HP/EDtunnel&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=3Kmfi6HP/EDtunnel&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=3Kmfi6HP/EDtunnel&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=3Kmfi6HP/EDtunnel&type=Date" />
  </picture>
</a>

<br><br>

**اگه این پروژه به دردت خورد، یه ⭐ بهش بده!**

✌️✌️✌️

</div>
