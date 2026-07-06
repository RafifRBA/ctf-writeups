# Challenge Name

Sleuthkit Intro


# Description
 Download the disk image and use mmls on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.

 Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.

Download disk image

# Solution

Pertama donwload dulu disk image yang ada pada soal.

Disk image ada pada GNU Zip, unzip dulu
```
gunzip -k disk.img.gz
```

Analyze!

Jalankan dulu instance yang ada dengan netcat.

Muncul pertanyaan:
```
What is the size of the Linux partition in the given disk image?
Length in sectors:
```

Cari info length dari linux partitionnya menggunakan command:
```
mmls disk.img.gz
```

Masukkan length `(202752)` ke soal untuk mendapatkan flag

output:
```
202752
Great work!
picoCTF{mm15_f7w!}
```

# Flag

picoCTF{mm15_f7w!}
