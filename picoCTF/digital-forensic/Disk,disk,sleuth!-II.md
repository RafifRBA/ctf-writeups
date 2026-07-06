# Challenge Name

Disk,disk,sleuth! II

# Description
 All we know is the file with the flag is named down-at-the-bottom.txt...

 dds2-alpine.flag.img.gz

# Solution

Pertama donwload dulu disk image yang ada pada soal.

Disk image ada pada GNU Zip, unzip dulu
```
gunzip -k dds2-alpine.flag.img.gz
```

Analyze!

Cari info offset dari linux partitionnya menggunakan command:
```
mmls dds2-alpine.flag.img
```

Dari deskripsi soal sudah diberi hint bahwa flag ada di dalam file `down-at-the-bottom.txt`.

Kita cari nomor inode pada file txt ini untuk nanti kita baca isinya
```
fls -r -p -o 2048 dds2-alpine.flag.img | grep -i "down-at-the-bottom.txt"
```

output:
```
r/r 18291:	root/down-at-the-bottom.txt
```

Setelah dapat inode nya, kita pakai command `icat` untuk mencari tahu isi dari file txt ini
```
icat -o 2048 dds2-alpine.flag.img 18291
```

dapatlah flag : picoCTF{f0r3ns1c4t0r_n0v1c3_4bd721f2}

# Flag

picoCTF{f0r3ns1c4t0r_n0v1c3_4bd721f2}
