# Challenge Name

Sleuthkit Apprentice

# Description
Download this disk image and find the flag.

Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.

Download compressed disk image

# Solution

Pertama donwload dulu disk image yang ada pada soal.

Disk image ada pada GNU Zip, unzip dulu
```
gunzip -k disk.flag.img.gz
```

Analyze!

Cari info offset dari linux partitionnya menggunakan command:
```
mmls disk.flag.img
```

Ternyata di dalamnya ada 2 partisi linux. Pada offset `2048` dan `360448`

kita cari file file yang ada di dalamnya sekaligus inodenya menggunakan `fls`:
```
fls -r -p -o [offsetnya] disk.flag.img
```

ketika melihat yang kedua, akan terlihat jelas di akhir ada output:
```
r/r * 2082(realloc):	root/my_folder/flag.txt
r/r 2371:	root/my_folder/flag.uni.txt
```

karena sudah rellocate untuk `flag.txt` kita coba langsung cari tahu isi yang `flag.uni.txt` saja
```
icat -o 360448 disk.flag.img 2371
```

dapat flagnya : picoCTF{by73_5urf3r_adac6cb4}

# Flag

picoCTF{by73_5urf3r_adac6cb4}