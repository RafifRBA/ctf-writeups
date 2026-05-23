# Challenge Name

Glory of the Garden


# Description
 This file contains more than it seems.

Get the flag from garden.jpg.

# Solution

Pertama donwload dulu garden.jpg yang ada pada soal.

Analyze!

Sesuai yang pertama, kita coba grep strings flagnya siapa tahu nemu
```
strings garden.jpg | grep "picoCTF"
```
Hasilnya adalah: 
```
Here is a flag: picoCTF{more_than_m33ts_the_3y395e12915}

```
Ternyata langsung dapet hahaha.

Tapi kalau sesuai sama hint nya yang mengarah ke hex. kita bisa pake command:
```
xxd garden.jpg
```
# Flag

picoCTF{more_than_m33ts_the_3y395e12915}
