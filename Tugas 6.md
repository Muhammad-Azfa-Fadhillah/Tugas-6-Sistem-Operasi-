Tugas Praktikum 6: Sistem Operasi

Nama : Muhammad Azfa Fadhillah

Nim  : 09011382530151

## 1. Eksekusi Seluruh Profile yang Ada

**a. Edit file `/etc/profile` dan tampilkan pesan:**
```bash
echo "Profile dari /etc/profile"
b. Edit semua profile yang ada (Asumsi nama user: azfa):
File yang diedit:

/home/azfa/.bash_profile

/home/azfa/.bash_login

/home/azfa/.profile

/home/azfa/.bashrc

Pada setiap file, cantumkan instruksi echo sesuai nama file. Contoh pada .bash_profile:

Bash
echo "Profile dari .bash_profile"
c. Perbedaan utilitas su dan su -:

Bash
$ su azfa
$ exit

$ su - azfa
$ exit
Penjelasan: su hanya mengganti user tanpa mengeksekusi file profile bawaan user baru (environment tetap seperti user lama). Sedangkan su - adalah proses login shell, environment lama dihapus dan seluruh file profile (seperti .bash_profile atau .profile) milik user baru akan dieksekusi secara penuh.

2. Prompt String (PS)
a. Edit file .bash_profile, ganti prompt PS1 dengan >:

Bash
PS1='> '
export PS1
b. Eksperimen hasil PS1 di terminal:

Bash
$ PS1="\! > "
69 > PS1="\d > "
Mon Sep 23 > PS1="\t > "
10:10:20 > PS1="Saya=\u > "
Saya=azfa > PS1="\w > "
~ > PS1="\h >"
3. Logout
Edit file .bash_logout, tampilkan pesan dan tahan selama 5 detik sebelum keluar:

Bash
echo "Terima kasih atas sesi yang diberikan"
sleep 5
clear
4. Bash Script
a. Buat 3 buah script (p1.sh, p2.sh, p3.sh):

p1.sh:

Bash
#!/bin/bash
echo "Program p1"
ls -l
p2.sh:

Bash
#!/bin/bash
echo "Program p2"
who
p3.sh:

Bash
#!/bin/bash
echo "Program p3"
ps x
b. Jalankan script tersebut dengan berbagai variasi:

Bash
$ ./p1.sh ; ./p3.sh ; ./p2.sh
$ ./p1.sh &
$ ./p1.sh & ./p2.sh & ./p3.sh &
5. Jobs
a. Buat shell-script nyawaktu.sh (loop tiap 10 detik):

Bash
#!/bin/bash
while [ true ]
do
  date >> hasil
  sleep 10
done
b. Jalankan di background bersama utilitas find:

Bash
$ ./nyawaktu.sh &
$ jobs
$ find . -print > files 2>/dev/null &
$ jobs
c. Manipulasi Foreground & Background:

Bash
$ fg %1
# (Tekan Ctrl+Z untuk suspend)
$ bg
d. Stop program background dengan utilitas kill:

Bash
$ ps x
$ kill [Nomor PID]
6. History
a. Ganti nilai HISTSIZE:

Bash
$ HISTSIZE=20
$ history
b. Mengedit instruksi baris ke-5 dari akhir:

Bash
$ !-5
c. Ulangi instruksi terakhir (Bisa pakai ^P dan ^N):

Bash
$ !!
d. Ulangi instruksi nomor 150:

Bash
$ !150
e. Ulangi instruksi dengan prefix "ls":

Bash
$ !ls

**Cara instan masukin ke GitHub dari terminal (buat jaga-jaga kalau kamu mager buka webnya):**
1. Buka folder tugasmu di terminal.
2. Buat filenya: `nano README.md`
3. *Paste* semua teks dari kotak di atas ke dalam terminal, lalu *Save* (Ctrl+O, Enter, Ctrl+X).
4. Jalankan:
   `git add README.md`
   `git commit -m "docs: menambahkan dokumentasi tugas praktikum 5"`
   `git push`
