<!-- markdownlint-disable MD033 MD041 MD047 MD040 -->
<h2 align="center">kaiOSHosts-ID</h2>

<div align="center">

[![GitHub Issues](https://img.shields.io/github/issues/nattadasu/kaiOSHosts-ID.svg)](https://github.com/nattadasu/kaiOSHosts-ID/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/nattadasu/kaiOSHosts-ID.svg)](https://github.com/nattadasu/kaiOSHosts-ID/pulls)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

</div>

<p align="center">
    Hosts File untuk pengguna KaiOS asal Indonesia untuk adblock dan bypass sensor menggunakan CWM.
    <br>
</p>

## 📝 Daftar Isi

- [🧐 Tentang](#about)
- [🗒 Daftar Variasi Berkas](#lists)
- [🎈 Penggunaan](#usage)
- [⛏️ Dibangun Menggunakan](#built_using)
- [✍️ Pemilik](#authors)
- [🎉 Persembahan](#acknowledgement)
- [👣 Catatan Kaki](#footnotes)

## 🧐 Tentang <a id= "about"></a>

Repo ini dibuat untuk membantu para pengguna KaiOS di Indonesia, terlebih pengguna telepon genggam
Advan Hape Online, dalam berselancar internet tanpa *diganggu* oleh iklan maupun
[penyensoran pemerintah](https://www.jetorbit.com/blog/apa-itu-internet-positif-apakah-diperlukan/).

Kami memanfaatkan daftar `hosts` dari [Energized][energized] untuk *adblock* berdasarkan alamat IPV4
dan IPV6 dan [bebasid][bebasid] untuk *bypass* Internet Positif.

Kami juga menyediakan versi terpisah untuk memblokir iklan dari [KaiAds][kaiads], **akan tetapi
versi ini memiliki kemungkinan dapat merusak beberapa fitur internal, seperti mengunduh aplikasi di
KaiStore atau memperbarui sistem**.<sup><a href="#fn1">1</a></sup> Beberapa aplikasi yang
mengandalkan iklan untuk monetasi <!-- *cough cough* mocha *cough cough* --> juga diketahui tidak
dapat berfungsi sebagaimana seharusnya. Pengguna diharapkan waspada jika ingin menggunakan versi
ini.

Untuk keterangan lebih lanjut, berkas *image* cwm ini sudah diujicoba di Advan Hape Online
menggunakan *custom rom* Digit4G, R2, dan DarkR2.

> Repo ini juga dapat digunakan bagi pengguna OS lainnya seperti Windows, Linux, BSD, macOS, hingga
> Android (diperlukan *rooting*). Silakan baca [USAGE.md](USAGE.md) untuk mengetahui lebih lanjut.
>
> **Resiko kerusakan (seperti situs tidak dapat memuat dengan baik) ditanggung oleh pengguna
> tersendiri.**
>
> Pengguna operator XL beserta produknya (Live.ON dan Axis) tidak akan dapat melewati (*bypass*)
> pemblokiran dikarenakan pembaruan *firewall*. Silakan kunjungi [bebasid/bebasid#436][bebasid436]
> untuk diskusi.

## 🗒 Daftar Variasi Berkas <a id = "lists"></a>

Untuk mulai mengunduh, silakan tuju ke [Release][release] untuk variasi yang lengkap, ATAU silakan
pilih salah satu opsi variasi untuk variasi yang sering digunakan:

<table>
<thead>
  <tr>
    <th style="font-weight:bold;text-align:center;vertical-align:center;" rowspan="2">Nama Paket</th>
    <th style="font-weight:bold;text-align:center;vertical-align:center;" rowspan="2">Deskripsi</th>
    <th style="font-weight:bold;text-align:center;vertical-align:center;" colspan="2">Tautan Unduhan</th>
    <th style="font-weight:bold;text-align:center;vertical-align:center;" rowspan="2">Sumber</th>
  </tr>
  <tr>
    <th style="text-align:center;vertical-align:center;">ZIP CWM</th>
    <th style="text-align:center;vertical-align:center;">RAW</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td style="text-align:right;vertical-align:center;">Adblock</td>
    <td>Cocok untuk hanya menghilangkan iklan browser</td>
    <td style="text-align:center;"><a href="https://github.com/nattadasu/kaiOSHosts-ID/releases/latest/download/adblock.zip">Tautan</a></td>
    <td style="text-align:center;"><a href="https://raw.githubusercontent.com/nattadasu/kaiOSHosts-ID/master/release/raw/adblock/hosts">Tautan</a></td>
    <td>
      <a href="https://github.com/EnergizedProtection/block">Energized Basic</a>,
      <a href="https://github.com/EnergizedProtection/block">Regional</a>
    </td>
  </tr>
  <tr>
    <td style="text-align:right;vertical-align:center;">Adblock + KaiAds</td>
    <td>Dapat menghilangkan iklan browser dan aplikasi</td>
    <td style="text-align:center;"><a href="https://github.com/nattadasu/kaiOSHosts-ID/releases/latest/download/adblock-kaios.zip">⚠ Tautan</a></td>
    <td style="text-align:center;"><a href="https://raw.githubusercontent.com/nattadasu/kaiOSHosts-ID/master/release/raw/adblock-kaios/hosts">⚠ Tautan</a></td>
    <td>
      <a href="https://github.com/EnergizedProtection/block">Energized Basic</a>,
      <a href="https://github.com/EnergizedProtection/block">Regional</a>,
      <a href="https://ivan-hc.github.io/bananahackers/ADBlock.html">KaiAds</a>
    </td>
  </tr>
  <tr>
    <td style="text-align:right;vertical-align:center;">Adblock + Bypass</td>
    <td>Cocok untuk hanya menghilangkan iklan browser dan bypass Internet Positif</td>
    <td style="text-align:center;"><a href="https://github.com/nattadasu/kaiOSHosts-ID/releases/latest/download/adblock-bypass.zip">Tautan</a></td>
    <td style="text-align:center;"><a href="https://raw.githubusercontent.com/nattadasu/kaiOSHosts-ID/master/release/raw/adblock-bypass/hosts">Tautan</a></td>
    <td>
      <a href="https://github.com/EnergizedProtection/block">Energized Basic</a>,
      <a href="https://github.com/EnergizedProtection/block">Regional</a>,
      <a href="https://github.com/bebasid/bebasid">bebasid</a>
    </td>
  </tr>
  <tr>
    <td style="text-align:right;vertical-align:center;">Adblock + Bypass + KaiAds</td>
    <td>Dapat menghilangkan iklan browser dan aplikasi, juga bypass Internet Positif</td>
    <td style="text-align:center;"><a href="https://github.com/nattadasu/kaiOSHosts-ID/releases/latest/download/adblock-bypass-kaios.zip">⚠ Tautan</a></td>
    <td style="text-align:center;"><a href="https://raw.githubusercontent.com/nattadasu/kaiOSHosts-ID/master/release/raw/adblock-bypass-kaios/hosts">⚠ Tautan</a></td>
    <td>
      <a href="https://github.com/EnergizedProtection/block">Energized Basic</a>,
      <a href="https://github.com/EnergizedProtection/block">Regional</a>,
      <a href="https://github.com/bebasid/bebasid">bebasid</a>,
      <a href="https://ivan-hc.github.io/bananahackers/ADBlock.html">KaiAds</a>
    </td>
  </tr>
  <tr>
    <td style="text-align:right;vertical-align:center;">Clear</td>
    <td>Menghilangkan konfigurasi secara total dari repositori ini</td>
    <td style="text-align:center;"><a href="https://github.com/nattadasu/kaiOSHosts-ID/releases/latest/download/clear.zip">Tautan</a></td>
    <td style="text-align:center;"><a href="https://raw.githubusercontent.com/nattadasu/kaiOSHosts-ID/master/release/raw/clear/hosts">Tautan</a></td>
    <td>Repositori ini</td>
  </tr>
</tbody>
</table>

## 🎈 Penggunaan <a id="usage"></a>

Silakan menuju ke [USAGE.md](USAGE.md) untuk informasi lebih lanjut.

## ⛏️ Dibangun Menggunakan <a id= "built_using"></a>

- GitHub Action - Otomasi Perilisan
- [bebasid/bebasid][bebasid] - Berkas *hosts* untuk bypass pemblokiran dari pemerintah
- [Energized Protection][energized] - Berkas *hosts* untuk pemblokiran iklan.

## ✍️ Pemilik <a id= "authors"></a>

- [@nattadasu](https://github.com/nattadasu)

Lihat pula daftar [kontributor](https://github.com/nattadasu/kaiOSHosts-ID/contributors) yang telah
berpartisipasi di proyek ini.

## 🎉 Persembahan <a id= "acknowledgement"></a>

Terimakasih sebesar-besarnya untuk yang telah membantu pemilik proyek dalam membangun konfigurasi
sistem dan otomasi perilisan.

- [@yezki](https://github.com/yezki) - Untuk sarannya atas konfigurasi GitHub Actions
  <!-- yang bikin pusing super -->
- [Anggota Forum Pengguna Advan Smart Feature Phone 2406 KaiOS][forum] di Facebook.

## 👣 Catatan Kaki <a id="footnotes"></a>

1. <a id= "fn1"></a> Baca: [BananaHackers.net - Adblock][kaiads]

<!--Links-->
[energized]: https://github.com/EnergizedProtection/block
[kaiads]: https://ivan-hc.github.io/bananahackers/ADBlock.html
[bebasid]: https://github.com/bebasid/bebasid
[forum]: https://www.facebook.com/groups/799381347207480
[release]: https://github.com/nattadasu/kaiOSHosts-ID/releases/latest
[bebasid436]: https://github.com/bebasid/bebasid/issues/436