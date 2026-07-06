# Challenge Name

Disk,disk,sleuth!

# Description
 Use srch_strings from the sleuthkit and some terminal-fu to find a flag in this disk image.
 
 dds1-alpine.flag.img.gz

# Solution

Pertama donwload dulu disk image yang ada pada soal.

Disk image ada pada GNU Zip, unzip dulu
```
gunzip -k dds1-alpine.flag.img.gz
```

Analyze!

Cari info offset dari linux partitionnya menggunakan command:
```
mmls dds1-alpine.flag.img
```

Karena dari deskripsi soal sudah diberi hint untuk search string, langsung saja kita pakai
```
srch_strings dds1-alpine.flag.img | grep "CTF"
```

dapat flag: picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}

# Flag

picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}
