---
toc: true
title: Yetim dasturchi kundaligi
description: O'zbek internet segmentida online hujjatlar va shaxsiy blogni rivojlantirishga qaratilgan stsenariy.
keywords: "Ma\u2019lumotlar, bitga, sharafiga, muhandisi, fransuz, bo\u2018lgan, ixtirochisi,
  apparat, Telegraf, necha"
---

## Xususiyatlar
- Tezkorlik
- Optimallashtirilgan seo
- Qulaylik, hujjatlar va jildlar bilan avtonom ishlay olish
- Avtomatik sahifalarni generatsiya qilish
- Unicode emojilar bilan ishlash

## O'rnatish

### Talablar
1. **PHP 5.6** yoki undan yuqori versiya
2. **Nginx** yoki **apache**
3. PHP uchun **yaml** va **mbstring** kengaytmasi
4. **Markdown** hujjatlari bilan ishlay olish :)

___
1. mbstring va yaml kengaytmalarini php uchun qo'shish
```bash
sudo apt-get install php-mbstring
sudo apt-get install php-yaml
```

2. ```src``` papkasidagi fayllarni domenning o'zak papkasiga ko'chirish.

3. `docs` papkasidagi hujjatlarni kerakli joyga o'tkazib, `config/main.php` faylidan `$config['docs_path']` o'zgaruvchisiga hujjatlar papkasini ko'rsatish.

## Foydalanish

### Jildlarni sozlash
Hujjatlar jildi ostidagi har bir `index.yml` fayli bu jildni foydalanuvchi interfeysiga generatsiya qilish uchun xizmat qiladi.

*Yaml fayliga misol:*

```yml
title: "Yetim dasturchi kundaligi"
description: "Yetim dasturchi tomonidan yozilgan blogpostlar."
keywords: "dastur, dasturlash, dasturchi, blog, wiki"
entries:
  - title: ma'lumotnoma
    url: about.htm
  - title: qo'llanmalar
    entries:
     - post_list: guides
       limit: 3
       show_more: true
  - title: blog
    entries:
     - post_list: blog
       limit: 5
       order: random
       show_more: true
       show_more_text: ko'proq...
       show_more_url: blog
  - title: aloqa
    url: contact.htm
```
| O'zgaruvchi |Qiymat|Parametr|Tasnif
|--|--|--|--|
|title|*string*|-|Sahifa sarlavhasi 
|description|*string*|-|Sahifa tasnifi (SEO)
|keywords|*string*|-|Sahifa uchun kalit so'zlar (SEO)
|pagination|*boolean*|`true` ko'rsatish<br /> --- <br />`false` o'chirish|Jild uchun sahifalash tizimini ko'rsatish. Sahifalash yoqilganda jild ostidagi havolalar `20` donadan sahifalanib ko'rsatiladi.
|entries|*array*|-|Sahifa kontenti uchun havolalar ro'yxati
|entries > title|*string*|-|Havola sarlavhasi
|entries > title > url|*string*|-|Havola url manzili
|entries > post_list|*string*|-|Kerakli hujjatlar jildi ostidagi yaml faylidan havolalar ro'yxatini olish
|entries > post_list > limit|*int*|cheklanmagan|havolalar chegarasi
|entries > post_list > order|*string*|`asc` to'g'ri tabtiblash<br /> --- <br />`desc` teskari tartiblash<br /> --- <br />`random` tasodifiy tartiblash|havolalarni tabtiblash
|entries > post_list > show_more|*boolean*|`true` ko'rsatish<br /> --- <br />`false` o'chirish|"***ko'proq***" havolasini ko'rsatish
|entries > post_list > show_more_text|*string*|-|"***ko'proq***" havolasi uchun sarlavha
|entries > post_list > show_more_url|*string*|-|"***ko'proq***" havolasi uchun manzil

### Markdown fayllar
Blogpostlar uchun berilgan fayllarda `yaml` va `markdown`  bir vaqtda tahlil qilingani sababli ularning har ikkisini berish majburiy hisoblanadi. Faqatgina `yaml` konfiguratsiyalari uchun ma'lum bir qiymatlarnigina istisno qilish mumkin.

> **Eslatma:** `index.yml` fayli tarkibida berilgan `url` o'zgaruvchisiga markdown fayl nomi va `.md` o'rnida `.html` yoki `.htm` kengaytmasi berilishi lozim. Tizim faylni o'qish uchun avtomatik `html` kengaytmasini `md` ga o'giradi.

*Markdown fayliga misol:*

```markdown
---
toc: false
title: "Namuna uchun sahifa"
description: "Namuna uchun sahifa tasnifi"
keywords: "sahifa, namuna"
---

## Talia cuncti quaecumque

Facienda sanguine haec iam. Tua libat accipit hic comas [obstantis addidit
cecini](http://silvis-socio.io/cromyona.aspx) secedere quae refert! Umeroque
coniuge Hippomenes patrias contineat meritis, pectora volucres porrigit ligno,
iungit. Cum Siphnon sacrata poterisne, Sisyphon!

> *In gentem* timido lumen auras; late numquam. Pecudes [vocem
> nec](http://www.sumererespondit.net/thalamos) qua fecit te penetralia illa
> Gortyniaco remota tantum luserat. Tauri quercus imagine pomo sed.

```

| O'zgaruvchi |Qiymat|Parametr|Tasnif
|--|--|--|--|
|title|*string*|-|Sahifa sarlavhasi 
|description|*string*|-|Sahifa tasnifi (SEO)
|keywords|*string*|-|Sahifa uchun kalit so'zlar (SEO)
|toc|*boolean*|`true` ko'rsatish<br /> --- <br />`false` o'chirish|Markdown tarkibida ishlatilgan sarlavhalar orqali avtomatik mundarija ishlab chiqish

## Sozlamalar

[config/defaults.php](https://github.com/mad-maids/maid.manu/src/config/defaults.php) ushbu fayl ostida tizim `yaml` fayllarida foydalanilmagan qiymatlarni to'ldirish uchun foydalanadi.
___
[config/main.php](https://github.com/mad-maids/maid.manu/src/config/main.php)

|O'zgaruvchi| Qiymat | Tasnif
|--|--|--|
| `$config['docs_path']` | *string* | Hujjatlar joylashgan jild |
| `$config['md']['auto_embed']` | *boolean* | Turli veb-saytlardagi kontentlarni (videolar, tvitlar va h.k.) joylashtirishni belgilash.<br>Misol: https://youtu.be/LXb3EKWsInQ url manzili markdown fayliga kiritilsa tizim url manzilni avtomatik video player bilan almashtiradi. |
| `$config['md']['embed_width']` | *int* | Auto joylashuv oynasi kengligi |
| `$config['md']['embed_height']` | *int* | Auto joylashuv oynasi balandligi |
| `$config['md']['embed_allowed_domains']` | *array* | Auto joylashuv uchun ruxsat etilgan xostlar |

## Kodlarni tahrirlash

Tizimga qo'shimcha imkoniyatlar kiritish uchun siz bemalol kodlarni tahrirlashingiz mumkin. Buning ozgina tizim haqida tushuncha kerak xolos :)

***Fayllar navigatori:*** 

```
├── config
│   ├── defaults.php
│   ├── main.php
│   └── routes.php
├── controllers
│   ├── Directory.php
│   └── File.php
├── helpers
│   ├── core.php
│   ├── parser.php
│   └── url.php
├── index.php
├── models
│   ├── Emojis.php
│   ├── Paging.php
│   ├── Parser.php
│   └── View.php
├── res
│   ├── min.css
│   ├── min.js
├── third_party
│   ├── autoload.php
│   └── bin
└── view
    ├── errors
    │   └── html
    │       ├── error_404.php
    │       ├── error_general.php
    │       └── error_php.php
    ├── foot.php
    ├── head.php
    └── layout
        ├── dir.php
        └── file.php

```
___

1. `controllers` jildi ostida joylashgan fayllar tizim routeri uchun xizmat qilib ushbu fayllar orqali tizimdagi navigatsiyalar belgilanadi.

*Misol:*

```
http://domain.uz/hello	// string(11) "Salom dunyo"
http://domain.uz/hello/eshmat // string(12) "Salom eshmat"
```

```php
<?php
//Namuna controlleri
namespace Controller;
use Model;

class Hello {
	public function say() {
		echo "Salom dunyo";
	}

	public function sayname( $name ) {
		echo "Salom: {$name}";
	}
}
```
```php
<?php
// config/routes.php fayli
$router['/hello'] = array('Hello', 'say');
$router['/hello/(.+)'] = array('Hello', 'sayname');
```

2. `helpers` jildi ostida joylashgan fayllar qo'shimcha yordamchi funksiyalarni kiritish imkonini beradi.
3. `models` jildi ostida joylashgan fayllar qo'shimcha yordamchi obyektlarni kiritish imkonini beradi.
```
http://domain.uz/hello	// string(11) "Salom dunyo"
```

```php
<?php
//Namuna controlleri
namespace Controller;
use Model;

class Hello {
	public function say() {
		Model\Custom::hello();
	}
}
```
```php
<?php
//Namuna Modeli
namespace Model;
class Custom {
	
	public function hello() {
		echo "Salom dunyo";
	}

}
```
3. `config` konfiguratsion fayllar jildi
4. `views` stsenariy mavzulari (front) jildi
5. `res` front resuslar uchun jild (js, css, rasmlar va h.k)
6. `third_party` qo'shimcha kutubxonalarni o'rnatish

## Litsenziya
`mad-maids/maid.manu` AGPL-3.0 litsenziyasi ostida litsenziyalangan. Batafsil ma'lumot uchun [`LICENSE`](https://github.com/mad-maids/maid.manu/LICENSE) fayliga qarang.