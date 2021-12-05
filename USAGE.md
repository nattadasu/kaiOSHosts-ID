<!-- markdownlint-disable MD047 MD033 MD031 -->

# Penggunaan

Berkas ini akan menjelaskan bagaimana Anda dapat menerapkan berkas hosts yang telah disediakan di
repo ini.

_**Peringatan**: Resiko kerusakan (seperti situs tidak dapat memuat) ditanggung oleh pengguna
tersendiri. Repo ini hanya mencakup pengguna KaiOS/Android yang memiliki clockworkmod (`cwm`)
terpasang di partisi `recovery`._

## Daftar Isi

* [Daftar Isi](#daftar-isi)
* [🦊 KaiOS/Firefox OS](#-kaiosfirefox-os)
  * [Melalui `cwm`](#melalui-cwm)
  * [Melalui `adb`](#melalui-adb)
* [🤖 Android](#-android)
  * [Root](#root)
  * [Non-root](#non-root)
* [🏠 Windows](#-windows)
* [🐧 Linux](#-linux)
  * [Metode perangkat lunak penyunting teks](#metode-perangkat-lunak-penyunting-teks)
  * [Metode `wget`](#metode-wget)
* [😈 BSD](#-bsd)
* [🍎 macOS](#-macos)
* [Definisi](#definisi)

<!-- START OF USAGE TUTORIAL -->

## 🦊 KaiOS/Firefox OS

**Perhatian!**

Telepon genggam KaiOS Anda harus sudah ter-*root* agar dapat mengubah berkas `hosts`.

Untuk info mengenai cara *rooting*, tergantung merek, silakan baca:

* [Forum Pengguna Advan Smart Feature Phone 2406 KaiOS (Facebook)][forumAdvan]
* [*Root* hampir segala gawai KaiOS][root]

### Melalui `cwm`

> **Catatan:**
>
> Petunjuk di bagian ini ditulis untuk pengguna [gawai](#fn1) Advan Smart Feature Phone 2406 dan
> telah terpasang CWM sebelumnya.
>
> Dapat digunakan untuk ROM Bawaan dengan root, R2, Digit4G, dan Dark R2.
>
> Untuk pengguna [gawai](#fn1) merek lainnya, disarankan menggunakan
> [metode melalui `adb`](#melalui-adb).

1. Masuk ke menu `cwm` dengan mematikan [gawai](#fn1) terlebih dahulu.
2. Nyalakan kembali gawai Anda sekaligus menekan tombol `#`.
3. Apabila menu muncul. Pilih "Recovery Mode" dengan menekan tombol `#` dan konfirmasi opsi dengan
   menekan tombol `*`.
4. Tuju menu "Install zip" > "Choose zip from ExtraSD" > Cari berkasnya > klik berkas dengan nama
   varian yang telah diunduh.
5. Tunggu proses selesai lalu kembali ke menu utama, pilih "Reboot Phone".

### Melalui `adb`

#### Sebelum memulai

Anda memerlukan:

1. PC/Laptop dengan OS Windows, macOS, ataupun Linux/BSD.
   * Sudah terinstall `adb-fastboot driver`, jika belum bisa dicari (direkomendasikan *system
     wide*).
2. Telepon genggam dan kabel data.
   * Sudah *root*/*jailbreak*/*cache injection* dan dapat *mount* r/w *system* di `adb`.

#### Pencadangan berkas

1. Pastikan fitur debugger/developer pada telepon genggam aktif. (muncul logo bug/serangga di status
   bar).
   * Jika tidak ada, buka "Settings" >  
2. Buka Command Prompt (Windows), Terminal (Linux, BSD, macOS), ataupun Powershell.
3. Ketik `adb devices` pada terminal, lalu tekan Enter/Return.
4. Konfirmasi apa yang terdaftar:
   * Apabila muncul (atau serupa):
     ```sh
     0123456789ABCDEF     device
     ```
     maka gawai sudah terbaca. Silakan ke tahap selanjutnya.
   * Apabila tidak terdaftar, silakan periksa kembali [Sebelum memulai](#sebelum-memulai) no.2.
   * Apabila muncul (atau serupa):
     ```bat
     ################     unauthorized
     ```
     Pastikan kembali dan coba:
     1. Telepon genggam tidak dalam posisi terkunci.
     2. Coba mencabut dan memasang kembali kabel data.
     3. Ganti kabel data.
     4. Ganti ke port USB lainnya.
     5. Gunakan mode *recovery*.
     6. Pasang kembali *driver*.
     7. Nyalakan kembali PC.
5. Ketik `adb remount` untuk *mount file system* dari `r/o` ke `r/w`.
6. Ketik
   ```ps1
   adb pull /system/etc/hosts [TUJUAN PENYIMPANAN]
   ```
   * Ganti tujuan folder backup (`[TUJUAN PENYIMPANAN]`) sesuai keinginan. Contoh:
     1. Windows
        ```bat
        E:\KaiOS\
        ```
     2. Linux/BSD/macOS:
        ```sh
        ~/KaiOS/
        ```
   * Pastikan garis miring "hadir" pada akhir alamat tujuan.
7. Periksa berkas yang baru saja dicadangkan.

#### Pemuatan berkas

1. Unduh salah satu versi berkas `hosts` dalam format RAW.
   * Pastikan kembali format berkas `hosts` bukan dokumen teks (`[VERSI].hosts.txt`).
     * Jika ada, ubah nama berkas menjadi `hosts` saja.
     * Untuk dapat mengubah `.txt`, buka:
       * **Windows 11**:
         1. Tekan logo 🔎 di *taskbar* (atau tekan `Win`+`S`)
         2. Cari "File Explorer Options".
         3. Arahkan ke tab "*View*".
         4. Di kolom "*Advanced Setting*," hapus centang "*Hide extensions for known file types*."
         5. Tekan "*OK*."
       * **Windows 8, 8.1, 10**:
         1. Buka *File Explorer*.
         2. Di bagian tab, ikuti:\
            ![Sample](assets/win10.png)
       * **Windows XP, Vista, 7**:
         1. Buka *File Explorer*.
         2. Ketuk tombol "*Organize*."
         3. Arahkan ke tab "*View*".
         4. Di kolom "*Advanced Setting*," hapus centang "*Hide extensions for known file types*."
         5. Tekan "*OK*."
2. Berdasarkan OS:
   * Untuk pengguna Windows:
     * Dari lokasi `hosts` yg baru, sambil tahan `shift`, klik kanan mouse > "Open Command Here".
   * Untuk pengguna Linux/BSD/macOS:
     * Arahkan terminal Anda ke lokasi `hosts` terbaru. Biasa terdapat di `~/Downloads/`.
3. Ketik
   ```sh
   adb remount
   ```
4. Ketik
   ```sh
   adb push hosts /system/etc/
   ```
5. [Muat ulang](#fn2) telepon genggam.

<!--
  Panduan berikut (Android hingga macOS, kecuali Linux) diambil dari
  https://github.com/bebasid/bebasid di bawah lisensi MIT, dengan modifikasi.
-->

## 🤖 Android

### Root

1. Unduh versi `hosts` yang Anda inginkan dalam format RAW.
   * Kami menyarankan untuk mengambil versi `hosts` yang tidak ada implementasi KaiAds.
     <!-- Soalnya kagak bermanfaat kali bruh. -->
   * Pastikan kembali format berkas `hosts` bukan dokumen teks (`[VERSI].hosts.txt`).
     * Jika ada, ubah nama berkas menjadi `hosts` saja.
     * Untuk dapat mengubah `.txt`, buka:
       * **Windows 11**:
         1. Tekan logo 🔎 di *taskbar* (atau tekan `Win`+`S`)
         2. Cari "File Explorer Options".
         3. Arahkan ke tab "*View*".
         4. Di kolom "*Advanced Setting*," hapus centang "*Hide extensions for known file types*."
         5. Tekan "*OK*."
       * **Windows 8, 8.1, 10**:
         1. Buka *File Explorer*.
         2. Di bagian tab, ikuti:\
            ![Sample](assets/win10.png)
       * **Windows XP, Vista, 7**:
         1. Buka *File Explorer*.
         2. Ketuk tombol "*Organize*."
         3. Arahkan ke tab "*View*".
         4. Di kolom "*Advanced Setting*," hapus centang "*Hide extensions for known file types*."
         5. Tekan "*OK*."
2. Salin file `hosts` dan tempel di folder `/etc` kemudian [muat ulang](#fn2) telepon genggam.

### Non-root

1. Unduh versi `hosts` yang Anda inginkan.
   * Kami menyarankan untuk mengambil versi `hosts` yang tidak ada implementasi KaiAds.
     <!-- Soalnya kagak bermanfaat kali bruh. -->
   * Pastikan kembali format berkas `hosts` bukan dokumen teks (`[VERSI].hosts.txt`).
     * Jika ada, ubah nama berkas menjadi `hosts` saja.
     * Untuk dapat mengubah `.txt`, buka:
       * **Windows 11**:
         1. Tekan logo 🔎 di *taskbar* (atau tekan `Win`+`S`)
         2. Cari "File Explorer Options".
         3. Arahkan ke tab "*View*".
         4. Di kolom "*Advanced Setting*," hapus centang "*Hide extensions for known file types*."
         5. Tekan "*OK*."
       * **Windows 8, 8.1, 10**:
         1. Buka *File Explorer*.
         2. Di bagian tab, ikuti:\
            ![Sample](assets/win10.png)
       * **Windows XP, Vista, 7**:
         1. Buka *File Explorer*.
         2. Ketuk tombol "*Organize*."
         3. Arahkan ke tab "*View*".
         4. Di kolom "*Advanced Setting*," hapus centang "*Hide extensions for known file types*."
         5. Tekan "*OK*."
2. Install aplikasi [Hosts Go][hostsGo].
3. Buka aplikasinya.
4. Ketuk "Hosts Settings".
5. Pilih hosts.
6. Kemudian jalankan.

## 🏠 Windows

1. Unduh versi `hosts` yang Anda inginkan.
   * Kami menyarankan untuk mengambil versi `hosts` yang tidak ada implementasi KaiAds.
     <!-- Soalnya kagak bermanfaat kali bruh. -->
   * Pastikan kembali format berkas `hosts` bukan dokumen teks (`[VERSI].hosts.txt`).
     * Jika ada, ubah nama berkas menjadi `hosts` saja.
     * Untuk dapat mengubah `.txt`, buka:
       * **Windows 11**:
         1. Tekan logo 🔎 di *taskbar* (atau tekan `Win`+`S`)
         2. Cari "File Explorer Options".
         3. Arahkan ke tab "*View*".
         4. Di kolom "*Advanced Setting*," hapus centang "*Hide extensions for known file types*."
         5. Tekan "*OK*."
       * **Windows 8, 8.1, 10**:
         1. Buka *File Explorer*.
         2. Di bagian tab, ikuti:\
            ![Sample](assets/win10.png)
       * **Windows XP, Vista, 7**:
         1. Buka *File Explorer*.
         2. Ketuk tombol "*Organize*."
         3. Arahkan ke tab "*View*".
         4. Di kolom "*Advanced Setting*," hapus centang "*Hide extensions for known file types*."
         5. Tekan "*OK*."
2. Ekstrak (jika berkas dalam kompresi ZIP) dan/atau sunting nama (*rename*) dengan menghilangkan
   format berkas seperti `txt` (jika ada).
3. Salin file `hosts` dan tempel di folder `C:\Windows\System32\drivers\etc`

## 🐧 Linux

> **Catatan**:
>
> Panduan berikut berdasarkan distribusi (distro) Ubuntu/Debian.
>
> Jika Anda menggunakan distro lain, silakan untuk membaca panduan berdasarkan distro
> masing-masing, karena adanya kemungkinan perangkat lunak yang tertera di contoh tidak terpasang di
> sistem/tersedia di pengelola paket.

<!--
  Metode di kedua bagian ini menggunakan referensi dari MUO dengan modifikasi.
  https://www.makeuseof.com/tag/modify-manage-hosts-file-linux/
-->

### Metode perangkat lunak penyunting teks

> Metode ini direkomendasikan untuk pengguna awam.

1. Buka aplikasi terminal favorit.
2. Lakukan pencadangan terlebih dahulu
   ```sh
   sudo cp /etc/hosts /etc/hosts.old
   ```
3. Unduh versi `hosts` yang Anda inginkan.
   * Kami menyarankan untuk mengambil versi `hosts` yang tidak ada implementasi KaiAds.
     <!-- Soalnya kagak bermanfaat kali bruh. -->
4. Berdasarkan aplikasi penyunting teks kesukaan Anda:
   * **GUI**
     * Microsoft Visual Studio `code`
       ```sh
       sudo code /etc/hosts
       ```
     * `sublime-text`
       ```sh
       sudo subl /etc/hosts
       ```
     * Gnome DE `gedit`
       ```sh
       sudo gedit /etc/hosts
       ```
     * KDE `kate`
       ```sh
       sudo kate /etc/hosts
       ```
     * GNU `emacs`
       ```sh
       sudo emacs /etc/hosts
       ```
     * Xfce `mousepad`
       ```sh
       sudo mousepad /etc/hosts
       ```
   * **CLI**
     * GNU `nano`
       ```sh
       sudo nano /etc/hosts
       ```
     * `vim`
       ```sh
       sudo vim /etc/hosts
       ```
     * `jed`
       ```sh
       sudo jed /etc/hosts
       ```
5. Salin data dari berkas yang Anda unduh, dan tempelkan ke berkas `hosts` sistem.
6. Simpan berkas.
7. Lakukan [muat ulang](#fn2) gawai jika diperlukan.

### Metode `wget`

> Anda dapat menggunakan `curl` dalam tahap ini, tapi memerlukan beberapa parameter harus diubah.
>
> 1. Ubah `-O` dari perintah untuk `wget` ke `-o` (tanpa kapitalisasi).

1. Buka aplikasi terminal favorit.
2. Lakukan pencadangan terlebih dahulu
   ```sh
   sudo cp /etc/hosts /etc/hosts.old
   ```
3. Dari beberapa cara, ketik
   1. Berkas dari halaman "*Release*"
      ```sh
      sudo wget https://github.com/nattadasu/kaiOSHosts-ID/releases/latest/download/<VERSI>.hosts.txt -O /etc/hosts
      ```
   2. Berkas dari repo
      ```sh
      sudo wget https://raw.githubusercontent.com/nattadasu/kaiOSHosts-ID/master/release/raw/<VERSI>/hosts -O /etc/hosts
      ```
   * Kami menyarankan untuk mengambil versi `hosts` yang tidak ada implementasi KaiAds.
   <!-- Soalnya kagak bermanfaat kali bruh. -->
   * Versi yang tersedia:\
     `clear`, `adblock`, `adblock-bypass`
4. Lakukan [muat ulang](#fn2) gawai jika diperlukan.

## 😈 BSD

1. Buka aplikasi terminal favorit.
2. Lakukan pencadangan terlebih dahulu
   ```sh
   sudo cp /etc/hosts /etc/hosts.old
   ```
3. Dari beberapa cara, ketik
   1. Berkas dari halaman "*Release*"
      ```sh
      sudo curl https://github.com/nattadasu/kaiOSHosts-ID/releases/latest/download/<VERSI>.hosts.txt -o /etc/hosts
      ```
   2. Berkas dari repo
      ```sh
      sudo curl https://raw.githubusercontent.com/nattadasu/kaiOSHosts-ID/master/release/raw/<VERSI>/hosts -o /etc/hosts
      ```
   * Kami menyarankan untuk mengambil versi `hosts` yang tidak ada implementasi KaiAds.
   <!-- Soalnya kagak bermanfaat kali bruh. -->
   * Versi yang tersedia:\
     `clear`, `adblock`, `adblock-bypass`
4. Lakukan [muat ulang](#fn2) gawai jika diperlukan.

> **Catatan**:
>
> Anda juga dapat menggunakan langkah-langkah penerapan berkas host dari Linux menggunakan GUI.
> Mungkin Anda perlu sedikit modifikasi dengan perintah agar sukses. Langkah-langkah tersebut bisa
> Anda baca di [sini](#metode-perangkat-lunak-penyunting-teks).
>
> Untuk itu silakan untuk membaca panduan dari distro masing-masing, karena adanya kemungkinan
> perangkat lunak yang tertera di contoh tidak terpasang di sistem/tersedia di pengelola
> paket/didukung.

## 🍎 macOS

1. Buka aplikasi Terminal.
2. Lakukan pencadangan terlebih dahulu
   ```sh
   sudo cp /etc/hosts /etc/hosts.old
   ```
3. Dari beberapa cara, ketik
   1. Berkas dari halaman "*Release*"
      ```sh
      sudo curl https://github.com/nattadasu/kaiOSHosts-ID/releases/latest/download/<VERSI>.hosts.txt -o /etc/hosts
      ```
   2. Berkas dari repo
      ```sh
      sudo curl https://raw.githubusercontent.com/nattadasu/kaiOSHosts-ID/master/release/raw/<VERSI>/hosts -o /etc/hosts
      ```
   * Kami menyarankan untuk mengambil versi `hosts` yang tidak ada implementasi KaiAds.
   <!-- Soalnya kagak bermanfaat kali bruh. -->
   * Versi yang tersedia:\
     `clear`, `adblock`, `adblock-bypass`
4. Lakukan [muat ulang](#fn2) gawai jika diperlukan.

> **Catatan**:
>
> Anda juga dapat menggunakan langkah-langkah penerapan berkas host dari Linux menggunakan GUI.
> Mungkin Anda perlu sedikit modifikasi dengan perintah agar sukses. Langkah-langkah tersebut bisa
> Anda baca di [sini](#metode-perangkat-lunak-penyunting-teks).
>
> Untuk itu silakan untuk membaca panduan dari Apple, karena adanya kemungkinan perangkat lunak yang
> tertera di contoh tidak terpasang di sistem/didukung.

<!-- END OF USAGE TUTORIAL -->

## Definisi

1. **Gawai**: <a id="fn1"></a>\
   *Gadget*; telepon genggam, laptop, komputer, dst.
2. **Muat Ulang**: <a id="fn2"></a>\
   *Restart*.

<!-- Links -->

[forumAdvan]: https://www.facebook.com/groups/799381347207480/files
[root]: https://ivan-hc.github.io/bananahackers/ROOT.html
[hostsGo]: https://play.google.com/store/apps/details?id=dns.hosts.server.change