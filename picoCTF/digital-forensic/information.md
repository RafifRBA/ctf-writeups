# Challenge Name

Information


# Description
 Files can always be changed in a secret way. Can you find the flag?

# Solution

Pertama donwload dulu cat.jpg yang ada pada soal.

Analyze!

Karena nama filenya cat.jpg kita coba analisis pake cat.
```
cd ~/Downloads
cat cat.jpg
```
Hasilnya jelek hanya strings2 gajelas. Next coba grep strings flagnya siapa tahu nemu
```
strings cat.jpg | grep "PicoCTF"
```
Hasilnya adalah: 
```
PicoCTF
    <rdf:li xml:lang='x-default'>PicoCTF</rdf:li>
```
Ternyata gadapet apa-apa nih. Kita lanjut coba analyze metadata jpg ini
```
exiftool cat.jpg
```
Di license ada strings suspicious yang berupa base64, kita coba decode
```
echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 --decode
```

# Flag

picoCTF{the_m3tadata_1s_modified}