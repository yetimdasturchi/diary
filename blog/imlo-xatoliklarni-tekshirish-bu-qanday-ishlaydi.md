---
toc: true
title: "Imlo xatoliklarni tekshirish. Bu qanday ishlaydi?"
description: "FOdatda hujjat bor ekan inson omili sabab kiritilgan turli morfologik xatoliklar ham bo'lishi tayin. Bugungi kundagi ko'plab kompyuter dasturlari esa ana shunday omildagi xatoliklarni ham aniqlay oladi va foydalanuvchiga xatoliklarni tuzatish uchun so'zlarni ham taklif bera oladi."
keywords: "imlo, korrektor, xatolik, hatolik, tekshirish, grammatika"
---

Hisoblash qurilmalari ofislarga ko'chgandan buyon insonlarning turli ehtiyojlarini qondirib kelayotgani ma'lum. Hujjatlar bilan ishlash, ularni chop etish, qayta saqlash kabi ko'plab vazifalarni bajara oladi bugungi kunda.

Odatda hujjat bor ekan inson omili sabab kiritilgan turli morfologik xatoliklar ham bo'lishi tayin. Bugungi kundagi ko'plab kompyuter dasturlari esa ana shunday omildagi xatoliklarni ham aniqlay oladi va foydalanuvchiga xatoliklarni tuzatish uchun so'zlarni ham taklif bera oladi.

Bungi kunda aspell (apple tomonidan ishlab chiqilgan), misspel, pspell yoki mspell asosida ishlaydigan hunspell dasturiy ta'minotlar mavjud. Odatda ular o'zi uchun juda ko'plab lug'atlarni bazasiga olgan. Hattoki foydalanuvchi tomonidan istisnolarni kiritish imkoniyati ham bor.

## Jarayon

- So'zni xatoligini belgilash
- Xatolikni to'g'rilash uchun takliflar berish
- Berilgan takliflarni xato so'zga nisbatan yaqinligini hisobga olish

Imlo xatolikga ega so'zni xato deb belgilash jarayoni juda oson. Mantiqan o'ylab qaralsa shunchaki bazada mavjud bo'lmagan so'zlarni xato deb belgilash mumkin.

Lekin xatolikga nisbatan alohida takliflar berish, morfologik jarayonni nazorat qilish alohida masala. Takliflarni jamlash uchun Levenshteyn masofasi kabi algoritmlar mavjud.

## So'z xatoligini belgilash

Birinchi navbatda foydalanuvchidan kelgan matndagi so'zlarni alohida massivga aylantirish olishimiz lozim. So'ngra har bir so'zni bazadan tekshirish kerak.

Matn: *salom sizga salomatlika tilayman*
```
Array
(
    [0] => salom
    [1] => sizga
    [2] => salomatlika
    [3] => tilayman
)
```


### Tekshirish uchun so'zlar bazasi

Bazaga shunchaki so'zlarni qatorlar asosida kiritish yoki ma'lum bir qo'shimchalarga egalarini regex orqali belgilash mumkin.

**Misol:** 
**So'z:** odam
***Ko'plik:** odamlar*
***Regex**: odam(lar)?*

Ya'ni -lar qo'shimchasini biz so'z uchun majburiy etib belgilamayapmiz. Foydalanuvchidan odam yoki odamlar shakli kelganda ham regex buni to'g'ri deb baholaydi.

*Fayl: database.txt*
```
assalom
salom/(at)?/(lik)?
salomatlan
assalomalaykum
dunyo
vassalom
sizga
tilayman
```

### Masivni tekshirish
```
function search_database($w=''){
  $lines = file('database.txt');
  foreach($lines as $line){
    $rgx = '/\b('.trim( str_replace("/", "", $line) ).')\b/';
    if( preg_match( $rgx, $w) ) return TRUE;
  }
  return FALSE;
}
```

## Levenshteyn masofasi

Odatda ikki so'z orasidagi masofani hisoblash. Ya'ni bir so'zni ikkinchisiga almashtirish uchun nechta harakatlar amalga oshirish kerakligini aniqlash.

**Masalan:**

"salam" so’zini eng kam amallar bajarish orqali "salom" so’ziga aylantirish uchun "a" ni "o" ga almashtirish kerak bo’ladi. Ya'ni amallar soni 1ta. Demak masofa birga teng.

![matritsa](https://i.ibb.co/1Z2ySz0/screen222.jpg)

-    _**s**alom_:  1-pozitsiyadagi  _s_ begisini  o'z holicha qoldirish
-   _s**a**lom_:  2-pozitsiyadagi  _a_ begisini  o'z holicha qoldirish
-   _sa**l**om_:  3-pozitsiyadagi  _i_ begisini  o'z holicha qoldirish
-   _sal**a**m_:  4-pozitsiyadagi  _a_  ni  _o_  bilan almashtirish
-   _sala**m**_:  5-pozitsiyadagi  _m_ begisini  o'z holicha qoldirish

**Masofani hisoblash algotirmi:**

Masofani hisoblash uchun eng oson yo'llardan biri bu birinchi so'z uzunligiga +1 hisobda massiv yaratish. So'ngra massivni ikki so'zdagi belgilarni baholash orqali to'ldirish.
```php
function levenshtein_distance( $s, $t ) {
  $m = strlen( $s );
  $n = strlen( $t );

  for( $i=0; $i <= $m; $i++ ) $d[$i][0] = $i;
  for( $j=0; $j <= $n; $j++) $d[0][$j] = $j;
  
  for( $i=1; $i <= $m; $i++) {
    for( $j=1; $j <= $n; $j++ ) {
      $c = ( $s[$i-1] == $t[$j-1] )?0:1;
      $d[$i][$j] = min( $d[$i-1][$j]+1, $d[$i][$j-1]+1, $d[$i-1][$j-1]+$c );
    }
  }
  return $d[$m][$n];
}
```