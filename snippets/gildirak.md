---
toc: false
title: "Linux foydalanuvchi interfeysida sichqoncha g'ildiragi tezligi (scroll speed) ni sozlash."
description: "Linux foydalanuvchi interfeysida sichqoncha g'ildiragi tezligi (scroll speed) ni sozlash."
keywords: "Linux, foydalanuvchi, interfeysida, sichqoncha, g'ildiragi, tezligi, scroll, speed, sozlash"
---

1. Kerakli kutubxonani o'rnatish
```bash
# ubuntu debian
sudo apt-get install imwheel
# arch
sudo apt-get install imwheel
```
2. Quyidagi kodni `gildirak.sh` nomi bilan saqlash
```bash
#!/bin/bash
if [ ! -f ~/.imwheelrc ]
then

cat >~/.imwheelrc<<EOF
".*"
None,      Up,   Button4, 1
None,      Down, Button5, 1
Control_L, Up,   Control_L|Button4
Control_L, Down, Control_L|Button5
Shift_L,   Up,   Shift_L|Button4
Shift_L,   Down, Shift_L|Button5
EOF

fi
##########################################################

CURRENT_VALUE=$(awk -F 'Button4,' '{print $2}' ~/.imwheelrc)

NEW_VALUE=$(zenity --scale --window-icon=info --cancel-label "Bekor qilish" --ok-label=Saqlash --title="G'ildirak" --text "Gildirak tezligi:" --min-value=1 --max-value=100 --value="$CURRENT_VALUE" --step 1)

if [ "$NEW_VALUE" == "" ];
then exit 0
fi

sed -i "s/\($TARGET_KEY *Button4, *\).*/\1$NEW_VALUE/" ~/.imwheelrc
sed -i "s/\($TARGET_KEY *Button5, *\).*/\1$NEW_VALUE/" ~/.imwheelrc

cat ~/.imwheelrc
imwheel -kill
```
3. Chmod sozlamalarini to'g'rilash
```bash
chmod a+x gildirak.sh
```
4. Ishga tushirish va sozlash
```bash
./gildirak.sh
```