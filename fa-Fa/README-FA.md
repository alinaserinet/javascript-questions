<div dir='rtl'>
<div align="center">
  <img height="60" src="https://img.icons8.com/color/344/javascript.png">
  <h1>سوالات جاوااسکریپت</h1>

---

سوالات چندگزینه‌ای جاوا اسکریپت را در **وضعیت (استوری)** [اینستاگرام](https://www.instagram.com/theavocoder/) قرار می‌دهم.

از سطح مقدماتی تا پیشرفته: با تست ها جاوااسکریپت را یاد بگیریم! دانش خود را به روز کنیم، یا حتی برای مصاحبه ها آماده شویم! :muscle: :rocket:
در **بخش جمع شونده** در زیر سوال پاسخ آن سوال را قرار داده ام و برای مشاهده کافی است فقط روی آن کلیک کنید تا باز شود. این فقط برای فان و سرگرمی است. موفق باشید!:heart:

</div>

| می‌توانید از آنها در پروژه‌ استفاده کنید! 😃 _واقعا_ ممنون خواهم بود اگر به پاس قدردانی به این مخرن ارجاع دهید!  💪🏼 متشکرم، امیدوارم لذت ببرید! |
| ------------------------------------------------------------------------------------------------------------------------------------------------- |

---

<details><summary><b>زبان های ترجمه شده:</b></summary>
<p>

- [🇸🇦 العربية](./ar-AR/README_AR.md)
- [🇪🇬 اللغة العامية](./ar-EG/README_ar-EG.md)
- [🇧🇦 Bosanski](./bs-BS/README-bs_BS.md)
- [🇩🇪 Deutsch](./de-DE/README.md)
- [🇪🇸 Español](./es-ES/README-ES.md)
- [🇫🇷 Français](./fr-FR/README_fr-FR.md)
- [🇮🇩 Indonesia](./id-ID/README.md)
- [🇯🇵 日本語](./ja-JA/README-ja_JA.md)
- [🇰🇷 한국어](./ko-KR/README-ko_KR.md)
- [🇳🇱 Nederlands](./nl-NL/README.md)
- [🇧🇷 Português Brasil](./pt-BR/README_pt_BR.md)
- [🇷🇺 Русский](./ru-RU/README.md)
- [🇹🇭 ไทย](./th-TH/README-th_TH.md)
- [🇹🇷 Türkçe](./tr-TR/README-tr_TR.md)
- [🇺🇦 Українська мова](./uk-UA/README.md)
- [🇻🇳 Tiếng Việt](./vi-VI/README-vi.md)
- [🇨🇳 简体中文](./zh-CN/README-zh_CN.md)
- [🇹🇼 繁體中文](./zh-TW/README_zh-TW.md)
- [🇫🇦 فارسی](./fa-Fa/README-FA.md)

</p>
</details>
</div>

---
###### 1. خروجی چیست?

```javascript
function sayHi() {
  console.log(name);
  console.log(age);
  var name = 'Lydia';
  let age = 21;
}

sayHi();
```

- A: `Lydia` ,`undefined`
- B: `Lydia` ,`ReferenceError`
- C: `ReferenceError` ,`21`
- D: `undefined` ,`ReferenceError`

<div dir='rtl'>
<details><summary><b>پاسخ</b></summary>
<p>

#### پاسخ: D


داخل تابع، ابتدا متغیر `name` را با کلمه کلیدی `var` تعریف کرده‌ایم، تعریف می‌شود. این به این معناست که متغیر فضایی از حافظه را می‌گیرد و مقدار اولیه آن به صورت پیشفرض `undefined` خواهد بود: تا زمانی که ما به خطی برسیم که این متغیر را نوشته‌ایم، جایی که می‌‌خواهیم متغیر را چاپ کنیم هنوز (مقدار) آن را تعریف نکرده ایم! پس مقدار چاپ شده آن `undefined` خواهد بود.
متغیرها با کلمه کلیدی `let` (و `const` به صورت ثابت) نیز تعریف می‌شوند، اما برخلاف `var` مقداردهی اولیه نمی‌شوند، آنها قبل از خطی که تعریف شده اند(مقدار دهی شده‌اند) در دسترس نیستند. این "temporal dead zone" نامیده می‌شود. وقتی که تلاش می‌کنیم به متغیرها قبل از جایی که آنها را تعریف کرده‌ایم دسترسی داشته باشیم، جاوااسکریپت یک ارور `ReferenceError` را به ما نشان خواهد داد.
</p>
</details>
</div>

---