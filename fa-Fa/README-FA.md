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
<div dir='rtl'>

###### 1.خروجی چیست؟

</div>

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


داخل تابع، ابتدا متغیر `name` را که با کلمه کلیدی `var` تعریف کرده‌ایم، تعریف می‌شود. این به این معناست که متغیر فضایی از حافظه را می‌گیرد و مقدار اولیه آن به صورت پیشفرض `undefined` خواهد بود و تا زمانی که به خطی نرسیده‌ایم که این متغیر در آن نوشته‌شده و مقداردهی‌شده مقدار آن همچنان `undefined` خواهد بود، جایی که می‌‌خواهیم متغیر را چاپ کنیم هنوز (مقدار) آن را تعریف نکرده ایم! پس مقدار چاپ شده آن `undefined` خواهد بود.
متغیرها با کلمه کلیدی `let` (و `const` به صورت ثابت) نیز تعریف می‌شوند، اما برخلاف `var` مقداردهی اولیه نمی‌شوند، آنها قبل از خطی که تعریف شده اند(مقدار دهی شده‌اند) در دسترس نیستند. این "temporal dead zone" نامیده می‌شود. وقتی که تلاش می‌کنیم به متغیرها قبل از جایی که آنها را تعریف کرده‌ایم دسترسی داشته باشیم، جاوااسکریپت یک ارور `ReferenceError` را به ما نشان خواهد داد.
</p>
</details>
</div>

---
<div dir='rtl'>

###### 2.خروجی چیست؟

</div>

```javascript
for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 1);
}

for (let i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 1);
}
```

- A: `0 1 2` , `0 1 2`
- B: `0 1 2` , `3 3 3`
- C: `3 3 3` , `0 1 2`
<div dir='rtl'>
<details><summary><b>پاسخ</b></summary>
<p>

#### پاسخ: C

در جاوااسکریپت هنگام استفاده از `setTimeout`، تابع کال‌بک (callback function) فراخوانی شده و پس از حلقه اجرا می‌شود. از آنجایی که متغیر `i` در اولین حلقه با کلمه کلیدی `var` تعریف شده، مقدار آن به صورت سراسری است. در داخل حلقه مقدار `i` با استفاده از عملگر `++` هربار `1` تا افزایش می‌یابد.زمانی که تابع کال‌بک در `setTimeout` فراخوانی شده، مقدار `i` برابر با `3` است.
در حلقه دوم متغیر `i` با کلمه کلیدی `let` تعریف شده: در حالتی که متغیر (یا ثابت) را با `let` یا `const` تعریف می‌کنیم، اسکوپ‌ها باعث میشوند که مقدار متغیر فقط در همان اسکوپ در دسترس باشد و `i` در هربار تکرار حلقه مقداری جدید خواهد داشت و هرمقدار در اسکوپ مخصوص به خود در دسترس خواهد بود(در اینجا مقادیر به اصطلاح کپچر می‌شوند) و مقدار `i` را بر اساس زمانی که `setTimeout` فراخوانی شده چاپ می‌کند.
</p>
</details>
</div>

---
<div dir='rtl'>

###### 3.خروجی چیست؟

</div>

```javascript
const shape = {
    radius: 10,
    diameter() {
        return this.radius * 2;
    },
    perimeter: () => 2 * Math.PI * this.radius,
};

console.log(shape.diameter());
console.log(shape.perimeter());
```

- A: `20` , `62.83185307179586`
- B: `20` , `NaN`
- C: `20` , `63`
- D: `NaN` , `63`

<div dir='rtl'>
<details><summary><b>پاسخ</b></summary>
<p>

#### پاسخ: B

توجه کنید مقدار `diameter` یک **regular function** است در حالی که مقدار `perimeter` یک **arrow function** است.
در **arrow function** ها،‌ کلمه کلیدی `this` به اسکوپ والد (اسکوپی که این تابع در آن قرار گرفته است) اشاره دارد، در حالی که در **regular function** ها اینطور نیست. زمانی که تابع `perimeter` فراخوانی می‌شود، `this` به شی `shape` اشاره ندارد پس به مقدار `radius` هم دسترسی ندارد.

بنابراین مقدار `radius` در `this` وجود نداشته و خروجی برابر `NaN` خواهد بود.

</p>
</details>
</div>

---
<div dir='rtl'>

###### 4.خروجی چیست؟

</div>

```javascript
+true;
!'Lydia';
```

- A: `1` , `false`
- B: `false` , `NaN`
- C: `false` , `false`
<div dir='rtl'>
<details><summary><b>پاسخ</b></summary>
<p>

#### پاسخ: A

در اینجا عملگر `+` عملوند را به یک عدد تبدیل می‌کند. `true` معادل `1` است و `false` معادل `0`.

رشته‌ی `'lydia'` یک مقدار **truthy** است و معادل `ture` در نظر گرفته شده: پس `'Lydia'!` مقدار `false` خواهد داشت.
</p>
</details>
</div>

---