# Links
اللينكات دي أهم حاجة حرفيا ف الويب و اللى اتعمل عشانها html أصلا و ليها استخدامات كتير اوي هنعرفها كلها ان شاء الله ركز معايا بقا

<br /><br />

## HTML Syntax
```HTML
<a href="https://google.com">Google</a>
```
- ال `a` هي اختصار `anchor` يعني مرساة السفينة و بالتالى تشبيه موفق انك بتستخدم اللينك عشان توصل لصفحة تانية كخطاف يعني
- ال `a` هو `paired tag` يعني ليه قفلة و فتحة و محتوى هيتحط بينهم زي ما واضح ف المثال
- مينفعش ابدا ابدا ابدا تهمل انك تضيف content جوا ال `a` و لا ينفع تنسى تحط ال `href` عشان اللينك يشتغل معاك و لازم تكون متأكد ان ال value بتاعت ال `href` مكتوبة صح
<br /><br />
> [!CAUTION]
> و دي شوية أمثلة لأخطاء مينفعش ترتكبها
> ```HTML
> <a>Google</a>
> <a href="https://google.com">Google</a>
> <a href="google.com">Google</a>
> <a href="https://google.com"></a>
> <a href="https://google.com">Google
> ```

<br /><br />

## Attributes
### `href`

اختصار ل`hypertext reference` و ده طبعا بتباصيله قيمة و ع حسب القيمة بتاعت ال `href` بيتحدد استخدام اللينك فمثلا
<br /><br /><br /><br />
* ممكن استخدم اللينك انه يروح لصفحة خارجية (مش تبع الموقع بتاعي) موجودة ع الويب و هنا هستخدم ال `//:https` ف الأول او ال `//:http` يعني ال `HyperText Transfer Protocol` عشان تكون القيمة هي `URL` الصفحة دي زي ما بيظهر ف المتصفحات زي كده
```HTML
<a href="https://google.com">Google</a>
```

<br /><br /><br /><br />
* ممكن كمان تستخدم اللينك انه يروح لصفحة تبع الموقع بتاعك و هناك هنستخدم ال `relative path` باعتبار المشروع هيكون كله ف فولدر واحد او ع سيرفر واحد

تخيل ال folder structure بتاعك بالشكل ده
```
project (Project Folder)
|
|
|__ assets
|   |
|   |__ imgs
|   |   |__ logo.png
|   |   |__ banner.svg
|   |   |__ favicon.ico
|   |
|   |__ videos
|   |   |__ How-to-deal-wih-links.mp4
|   |
|   |__ fonts
|       |__ Rubik-Italic-VariableFont_wght.ttf
|       |__ Rubik-VariableFont_wght.ttf
|
|
|__ pages
|   |
|   |__ test
|   |   |__ test2.html
|   |
|   |__ test1.html
|
|
|__ index.html
|__ contact.html
|__ about.html
```
<br /><br />
لو عايز اعمل لينك ف ال `index` يوديني ع ال `contact` هييبقى بالشكل ده
```HTML
<a href="./contact.html">Contact Us</a>
```
ال `/.` معناها `ف نفس الفولدر اللى الفايل ده فيه` و طبعا زي ما واضح ال `index.html` و ال `contact.html` جيران ف نفس الفولدر
```
project (Project Folder)
|
|__ index.html
|__ contact.html
```
<br /><br />
لو عايز اعمل لينك ف ال `about.html` يوديني ع ال `test2` هييبقى بالشكل ده
```HTML
<a href="./pages/test/test2.html">Test2</a>
```
بقوله ف نفس الفولدر اللى منه ال `about.html` انت شايف الفولدر اللى اسمه `pages` هات منه الفولدر اللي اسمه `test` هات منه الفايل `test2.html`
```
project (Project Folder)
|
|__ pages
|   |__ test
|       |__ test2.html
|
|__ about.html
```
<br /><br />
لو عايز اعمل لينك ف ال `test1.html` عشان اوصل لل `index.html` مينفعش دلوقتى استخدم نفس الطريقة
```
project (Project Folder)
|
|__ pages
|   |__ test1.html
|
|__ index.html
```
 زي ما انت شايف ال `test1.html` مش شايف ف نفس الفولدر بتاعه غير فولدر تاني اسمه `test` فبالتالي لازم يرجع بضهره للفولدر الأصلي بتاع المشروع و ده بالظبط اللى بتعمله ال `/..`
```HTML
<a href="../index.html">Home</a>
```
<br /><br />
نفس الكلام لو عايز اوصل من `test2.html` ل `contact.html`
```
project (Project Folder)
|
|__ pages
|   |__ test
|       |__ test2.html
|
|__ contact.html
```
المرادي `test2.html` محشور ف الفولدر اللى اسمه `test` لو رجع بضهره خطوة بقا شايف محتويات الفولدر اللى اسمه `pages` محتاج ارجع كمان خطوة عشان اوصل للفولدر الأساسي للمشروع و اقدر اشوف ال `contact.html`
```HTML
<a href="../../contact.html">Contact Us</a>
```
<br /><br />
طيب تخيل معايا بقا انا عندي فايلات كتير ف فولدرات جوا بعض و عايز احط فيهم كلهم تلات لينكات يودوني ع ال `index.html` و ال `contact.html` و ال `about.html` أكيد م هوجع دماغي اني اشوف كل فايل موجود ف فولدر اي و محتاج ارجع كام خطوة المشترك بين التلات فايلات اللى عايز اوصلها ان كلها موجودة ف ال `home directory` يعني الفولدر الأساسي للمشروع اللى شايف كل حاجة و عشان اوصل ليه بسرعه هستخدم `/`
```HTML
<a href="/index.html">Home</a>
<a href="/contact.html">Contact Us</a>
<a href="/about.html">About Us</a>
```
كده اى يكن مكانك هترجع لل `home directory` و تشوف منه اللى انت عايزه

> [!NOTE]
> اعمل سيرش ع استخدام ال `//` ممكن تحتاجها يوما ما

<br /><br /><br /><br />
* ممكن استخدم اللينك انه يوديني لجزء معين ف نفس الصفحة اللى انا فيها و ده اللى بسميه `bookmark` و دي بتستخدم طريقة ال `URI fragments` يعني آخر ال `URI` هيكون عندك `#` و بعدها identifier للجزء اللى انت عايز تروحله
```HTML
<a href="/index.html#vendors">vendors</a>
```
طبعا لازم اكون معرف المكان اللى انا رايحله ف صفحة `index.html` بإني أحطله attribute ال `id` و لازم تكون ال value بتاعته نفس ال `fragment` اللى بعد ال `#` ف اللينك
```HTML
<p id="vendors">vendors: Microsoft - Google - Amazon</p>
```
تقدر تشوف مثال حقيقي من [هنا](./bookmarks-example.md)

<br /><br /><br /><br />
* ممكن استخدم اللينك ف اني احط فيه معلومات تواصل ليا زي مثلا احط رقم تليفوني او ايميلي او لينك الواتساب و البروفايلات بتاعتي ع السوشيال ميديا
```HTML
<a href="mailto:mustafayasser031212@gmail.com">Email</a>
<a href="tel:+201553566100">Call Me</a>
<a href="https://wa.me/+201553566100">Chat with me on Whatsapp</a>
<a href="https://www.facebook.com/profile.php?id=61560263336743">Facebook profile</a>
```

> [!CAUTION]
> مينفعش تحط مسافات ف قيمة ال `href` يعني مينفعش
> ```HTML
> <a href="mailto: mustafayasser031212@gmail.com">Email</a>
> ```
> و مينفعش تفتكس من عندك يعني متكتبش `email` بدل `:mailto` و لا `:telephone number` بدل `:tel` و هكذا

<br /><br /><br /><br />
* ممكن استخدم اللينك ف انى احمل download ملف عندي ع الجهاز مثلا `PDF` او `SQL` او صورة او غيرهم او حتى أعرضهم ع المتصفح بتاعي لو بيدعم ده
```HTML
<a href="https://static.toiimg.com/thumb/msid-53891743,width-748,height-499,resizemode=4,imgsize-152022/.jpg">Preview Image for Paris</a>
<a href="https://tourism.gov.in/sites/default/files/2019-04/dummy-pdf_2.pdf" download="dummy-pdf_2.pdf">Download Dummy PDF</a>
<a href="https://www.samplefiles.org/?dl_id=267">Download SQL File</a>
<a href="https://filesamples.com/samples/document/txt/sample3.txt">Text File Previewing</a>
```

> [!CAUTION]
> عشان تحمل ملف pdf مثلا ده لازم يتحقق شرطين الأول انك تكون أصلا حاطط ال pdf ف نفس سيرفر الموقع اللى بتحمل منه و الشرط التاني انك تستخدم ال `download` attribute و تباصيله اسم الملف اللى انت متارجته بال extension بتاعته و ده بيفسر لي اللينك اللى بيحمل ال pdf فوق ده مش هيشتغل لو حطيته ف موقعك الموضوع ده بيكون لأسباب أمنية و م بيطبق ع كل حاجة عشان في حاجات ال browser م هيقدر يعرضها زي ال SQL File زي المثال اللى فوق بردو

<br /><br />

### `target`
ال attribute ده بيستخدم عشان يحدد ال frame اللى انت هتفتح فيه الصفحة اللى هيوديك ليها اللينك ده يعني و ليه قيم معروفة تختار منهم عشان تحدد ده و طبعا م محتاج أقولك لازم تكتب القيم دي زي ما هي كده لا تنسي `_` و لا تغير ف الكلام او تكون مسمي انت ال frame بتاعك
- `_self`
- `_blank`
- `_parent`
- `_top`
- framename

دي صورة بتوضح اللى بيعمله الاربع قيم

![Target Attribute Values](./target-attribute.png)

> [!NOTE]
> مش هينفع استفيض ف شرح الموضوع ده دلوقتى اعرف بس ان ال `self_` دي القيمة الافتراضية و اللى بتخليني افتح الصفحة اللى انا عايز اروحها ف نفس الصفحة اللى انا واقف فيها و ده بيكون مع اغلب استخدامك للينكات زي انك تتنقل بين صفحات موقعك و كده اما بقا ال `blank_` دي بتخليك تفتح الصفحة اللى انت رايحلها ف صفحة جديدة و تحتفظ بالصفحة القديمة مفتوحة عادي و ده ممكن يكون مع لينكات بروفايلاتك ع السوشيال ميديا مثلا و كده

> [!CAUTION]
> يفضل تستخدم attribute ال `rel` و تباصيله القيم `noopener` `norefrrer`عشان تمنع مشاكل ف ال security و ال performance حطها بس ف دماغك دلوقتى و لما نيجي ان شاء الله نشرح performance و security هنتطرقلها ان شاء الله و ده مثال عشان يوصلك قصدي و ممكن تسيرش لو حابب
> ```HTML
> <a href="https://example.com" target="_blank" rel="noopener noreferrer">Link</a>
> ```

<br /><br />

### `title`
تقدر تستخدم ال attribute ده ف انك توفر معلومات أكتر للمستخدم عن اللينك اللى انت مستخدمه فيه ف بيفتح معاك tooltip فيها القيمة اللى انت مباصيها لل `title` attribute و ده مثال عشان يوصلك قصدي
```HTML
<a href="https://example.com" title="example is a deployed webpage with dummy contect">example</a>
```

<br /><br />

## To be Cont...
طبعا ال links مخلصتش لحد هنا في حاجة انا مأجلها لحد ما ناخد ال buttons و التعامل مع ال js عشان هتقابل links كتير لما تيجي تدوس عليها مبتعملش navigation لأي صفحات او بتشتغل ك bookmark و لا بتعمل download ممكن تكون بتنفذ js code ممكن تكون شكل لينك بس لكن مبتعملش اى حاجة ممكن تشغل اللينك ع انه button بردو منها اللى صح و منها اللى غلط لكن شايع فلازم نعرفه

بالتالى كده احنا أجلنا تلات حاجات
- ازاى استخدم ال `//` و شوية حوارات ف ال protocols
- القيم بتاعت ال `target` attribute لحد ما ناخد `iframe`
- التعامل مع اللينكات بوظيفة تانية غير ال navigation زي تنفيذ functionality او غيرها