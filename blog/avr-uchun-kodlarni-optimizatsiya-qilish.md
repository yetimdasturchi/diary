---
toc: true
title: "Avr uchun kodlarni optimizatsiya qilish"
description: "Inson tiliga yaqinlashganimiz sari resurslar sarfidan yutqazib boraveramiz. Misol uchun pythondagi 1 qator kod q.."
keywords: "arduino, c++, avr, qurilma, software, hardware, dasturlash, robototexnika"
---

Arduino board resurs tejamaydigan parazit dasturchilar uchun juda foydali qurilma hisoblanadi. Chunki ushbu kichik qurilmadagi resurslar bugungi kun uchun juda ham cheklangan. ATmega328P misolida buni ko'radigan bo'lsak:

**Flesh xotira**: 32 KB (0.5 KB bootloader uchun ishlatiladi)

**SRAM**: 2 KB

**EEPROM**: 1 KB

**SOAT TEZLIGI**: 16 MHz

Yuqoridagi xusuytlardan 32 KB xotira uchun dastur yozgan bilan ham uning ishlashi uchun sizda 2 KB dinamik xotira mavjud xolos. Qishlaqchasiga aytganda 2 KB ram.

Arduino uchun dasturlash tili C va C++ bazasida ishlab chiqilgan. Xohlovchilar albatta assemblerdan ham foydalanishlari mukin. Alohida interpretatsiya qilingan til sodda bo'lgani bilan resurslar masalasida tejamkor bo'la olmaydi. Shu sababli ham ushbu qurilma bilan doimiy ishlovchi dasturchilar har doim ham o'zlarining ideal loyihalarini chiqara olmasliklari mumkin.

Lekin qurilmaning qanday ishlashini o'rganidan bo'lsak undagi 2 KB xotira ham juda katta narsa ekanligini tushunib yetamiz. Axir Applening tarixi 4 KB bilan boshlangan edi.

## Lamercha kod yozish

Arduinoda yonib-o'chuvchi dastur kodini olaylik. Deyarli juda ko'pchilik quyidagi variantda kod yozishga odatlangan. Albatta bu juda sodda ko'rishishga ega. Lekin kompilyator bergan statistikaga qaraydigan bo'lsak juda kichik dastur uchun ham katta resurs ishlatilayotganini ko'rishimiz mumkin. 
```
924 bytes (2%) of program storage space
9 bytes (0%) of dynamic memory
```

![sample code](https://i.ibb.co/gD2YrzQ/image.png)

## Manipulatsiya
Keling ishni arduino kutubxonalarini titkilashdan boshlasak. Quyidagi katalogda ko'rsatilgan fayl orqali `pinMode()` va `digitalWrite()` funsksiyalari qanday ishlashini ko'rishimiz mumkin. Ushbu funksiyalar oddiy foydalanuvchi uchun registerlarga yozishni soddalashtirib beryapti xolos. Bu esa ushbu funksiyalarsiz ham ishlash mumkinligini bildiradi.

`~/.arduino/packages/arduino/hardware/avr/1.8.5/cores/arduino/wiring_digital.c`
*Eslatma: Men linux OSdan foydalanaman, sizdagi operatsion tizim turiga qarab fayllar katalogi farq qilishi mumkin.*

Atmega chipining texnik hujjatiga qaraydigan bo'lsak portlarning uchta seksiyaga qarab bo'linganini ko'ramiz:

**B** - 8dan 13gacha bo'lgan pinlar (D8-D13)

**C** - analog pinlar (A0-A5)

**D** -  0dan 7gacha bo'lgan pinlar (D0-D7)

Registerlarni boshqarish:

**DDR** - pinlarni kiritish yoki chiqarish rejimini boshqarish

**PORT** - pinni yoqish yoki o'chirish (HIGH va LOW)

**PIN** - kiritish pinlaridagi holatni o'qish

Demak arduinoning uchta pin blokdan tashkil topganini hisobga oladigan bo'lsak:

**-DDRB, PORTB, PINB** - 8 dan 13 gacha bo'lgan pinlar uchun

**-DDRC, PORTC, PINC**  - A0 dan A5 gacha bo'lgan pinlar uchun

**-DDRD, PORTD, PIND** - 0 dan 7 gacha pinlar uchun

Har bir registrdagi bir bit bitta pinga mos keladi, DDRB misolida:

|XTAL|XTAL|D13|D12|D11|D10|D9|D8|
|--|--|--|--|--|--|--|--|--|
|1|1|0(1)|0(1)|0(1)|0(1)|0(1)|0(1)|

*\* - Pinlar soni 6ta bo'lishiga qaramasdan kristal sababli 8 bitda berilishi lozim (XTAL)*

Yuqorida biz DDRB registrida 8 dan 13 gacha pinlar rejimini kirish yoki chiqish sifatida boshqarish imkoniyatini ko'rishimiz mumkin. Misol uchun, agar 8-pin uchun bit **0 qiymatiga** ega bo'lsa, bu 8-pin uchun **kirish rejimini** anglatadi , aks holda **1 qiymatida** bo'lsa, **chiqish rejimi**.

Arduino dasturi uchun kiritish (misol):

**DDRB=B11111111;** - olti pinning barchasi uchun chiqish rejimini yoqish

**DDRB=B11111100;**  -  8 va 9 pinlarni kirish va 10 dan 13 gacha bo'lgan pinlarni chiqish uchun sozlash.

Yoki hex orqali kiritish:

**DDRB=0xff;**

**DDRB=0xfc;**

Chiqish rejimida pin holatini o'chirish va yoqish ham xuddi **DDRB** kabi ishlaydi. Faqat bundan **PORTB** orqali berish lozim:

**PORTB = B11111111;** - Barcha pinlarni yoqish

**PORTB = B11011111;** - 13-pinni o'chirish

Led chiroq yonib-o'chuvchi dastur misolida:

```c
void setup() {
  DDRB=B11100000; // 13-pinni chiqish uchun sozlash
}

void loop() {
  PORTB=B11100000; // 13-pinni yoqish
  delay(1000);
  PORTB=B11000000; // 13-pinni o'chirish
  delay(1000);
}
```
```
648 bytes (2%) of program storage space
9 bytes (0%) of dynamic memory
```
`pinMode()` va `digitalWrite()` funksiyasi bilan yozilgan koddagi resurs bilan solishtiradigan bo'lsak 276 baytga farq qildi.

## setup() va loop() funksiyalaridan kechish

Arduinoda `void setup()`  funksiyasi qurilma yongandan so'ng turli sozlamalarni berishga ishlatiladi. `void loop()` esa kristal tezligiga qarab cheksiz sikl hisobida ishlaydi.

Demak  `void setup()` va `void loop()` funksiyalarini AVR kodlaridan izlaymiz. 

`~/.arduino/packages/arduino/hardware/avr/1.8.5/cores/arduino/main.cpp`

Ushbu fayl ichida setup() va cheksiz sikl ichida loop() funksiyasiga qilingan murojaatni ko'rishimiz mumkin. Demakki biz `setup()` va `loop()` funksiyalaridan voz kechib to'g'ridan to'g'ri `int main (void)` orqali dasturni yoza olamiz. Qo'shimcha sifatida esa serial uchun ajratilgan ortiqcha qismlarni ham chetlashimiz mumkin (serial port, kristalning ashaddiy qotili).

![main.cpp](https://i.ibb.co/f2cByJ0/Arch-Labs-2022-10-04-58-1920x1080.png)

Birinchi kod:
```cpp
int main() {
  DDRB = B11100000; // 13-portni chiqish uchun sozlash
  while (true) { // cheksiz sikl
    PORTB = B11100000; // 13-portni yoqish
    delay(1000); // 1 soniya kutish
    PORTB = B11000000;  // 13-portni o'chirish
    delay(1000); // 1 soniya kutish
  }
}
```
```
500 bytes (1%) of program storage space
9 bytes (0%) of dynamic memory
```
Sarflangan resurslar:

**pinMode** va **digitalWritega** nisbatan farq: 424 bayt

**setup()** va **loop()** ga nisbatan farq: 148 bayt

## Delay uchun alternativ
Lekin yuqoridagi kodimizni ishga tushiradigan bo'lsak 13-pin doimiy yoniq qolayotganini ko'rishimiz mumkin. Chunki `Arduino.h` kutubxonasi ishga tushmayapti va shu sababli `delay()` funksiyamiz ham o'z ishini bajarmayapti.

Demak delay uchun muqobil variant qo'llashimiz kerak. Buning eng optimal usuli esa for sikli hisoblanadi. Lekin for siklni ham bo'l holatda qoldirib bo'lmaydi. Shu sababli kompilyatorni chalg'itish uchun chunchaki `asm()` funksiyasidan foydalanamiz. Buda komplyatorda xuddiki assembler kodini ishga tushirayotgandagi kabi tasasavvur paydo bo'ladi va oraliq pauza kuzatiladi.
```c
for (long i = 0; i < 500000; i++) {
  asm("");
}
```
```c
int main() {
  DDRB = B11100000;
  while (true) {
    PORTB = B11100000;
    for (long i = 0; i < 500000; i++) {
      asm("");
    }
    PORTB = B11000000;
    for (long i = 0; i < 500000; i++) {
      asm("");
    }
  }
}
```
```
178 bytes (0%) of program storage space
0 bytes (0%) of dynamic memory
```
Sarflangan resurslar:

**pinMode** va **digitalWritega** nisbatan farq: 746 bayt

**setup()** va **loop()** ga nisbatan farq: 322 bayt

## Piru komil rejimi

924 baytdan 178 baytga tushish yomon natija emas albatta. Lekin bunga ham qoniqmaydilarga uchun PINB orqali ham inversiya amalga oshirish mumkin (`boolean = !boolean`)

```c
int main() {
  DDRB = 0xE0;
  while (true) {
    PINB = 0xE0;
    for (long i = 0; i < 1000000; i++) {
      asm("");
    }
  }
}
```
```
158 bytes (0%) of program storage space
0 bytes (0%) of dynamic memory
```
## Xulosa

Inson tiliga yaqinlashganimiz sari resurslar sarfidan yutqazib boraveramiz. Misol uchun pythondagi 1 qator kod qiladigan vazifa C tilida 100 qator bo'lishi mumkin. Lekin resurs va tezkorlik jihatdan 100 qator kod doimiy birinchilikda qolaveradi. Chunki 1 qator kodni minglab qatorlarda yozilgan kodlar orqali qurilmagan tushuntirish lozim.

Agarda qurilma bilan to'g'ridan to'g'ri muloqot qilish arzon tushadigan bo'lsa, nega shu yo'ldan foydalanmasligimiz kerak?
