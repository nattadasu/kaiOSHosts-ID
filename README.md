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

- [Tentang](#about)
- [Memulai](#getting_started)
- [Daftar Variasi Berkas](#lists)
- [Catatan Kaki](#footnotes)
<!--
- [Deployment](#deployment)
- [Usage](#usage)
- [Built Using](#built_using)
- [Authors](#authors)
- [Acknowledgments](#acknowledgement)
-->

## 🧐 Tentang <a id= "about"></a>

Repo ini dibuat untuk membantu para pengguna KaiOS di Indonesia, terlebih pengguna telepon genggam
Advan Hape Online, dalam berselancar internet tanpa *diganggu* oleh iklan maupun
[penyensoran pemerintah](https://www.jetorbit.com/blog/apa-itu-internet-positif-apakah-diperlukan/).

Kami memanfaatkan daftar `hosts` dari [Energized][energized] untuk adblock berdasarkan alamat IPV4
dan IPV6 dan [bebasid][bebasid] untuk *bypass* Internet Positif.

Kami juga menyediakan versi terpisah untuk memblokir iklan dari [KaiAds][kaiads], <strong>akan
tetapi versi ini dapat merusak beberapa fitur internal, seperti mengunduh atau memperbarui aplikasi
</strong>.<sup><a href="#fn1">1</a></sup> Pengguna diharapkan waspada jika ingin menggunakan versi
ini.

Untuk keterangan lebih lanjut, berkas *image* cwm ini sudah diujicoba di Advan Hape Online.

> Repo ini juga dapat digunakan bagi pengguna OS lainnya seperti Windows, Linux, BSD, macOS, hingga
> Android (diperlukan *rooting*). Silakan baca [`USAGE.md`](USAGE.md) untuk mengetahui lebih lanjut.
>
> Resiko kerusakan (seperti situs tidak dapat memuat) ditanggung oleh pengguna tersendiri. Repo ini
> hanya mencakup pengguna KaiOS/Android yang memiliki clockworkmod (cwm) terpasang di partisi
> *`recovery`*.

## 🗒 Daftar Variasi Berkas <a id = "lists"></a>

Untuk mulai mengunduh, silakan pilih salah satu opsi variasi:

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
    <td></td>
    <td></td>
    <td>
      <a href="https://github.com/EnergizedProtection/block">Energized Basic</a>,
      <a href="https://github.com/EnergizedProtection/block">Regional</a>
    </td>
  </tr>
  <tr>
    <td style="text-align:right;vertical-align:center;">Adblock + KaiAds</td>
    <td>Dapat menghilangkan iklan browser dan aplikasi</td>
    <td></td>
    <td></td>
    <td>
      <a href="https://github.com/EnergizedProtection/block">Energized Basic</a>,
      <a href="https://github.com/EnergizedProtection/block">Regional</a>,
      <a href="https://ivan-hc.github.io/bananahackers/ADBlock.html">KaiAds</a>
    </td>
  </tr>
  <tr>
    <td style="text-align:right;vertical-align:center;">Adblock + Bypass</td>
    <td>Cocok untuk hanya menghilangkan iklan browser dan bypass Internet Positif</td>
    <td></td>
    <td></td>
    <td>
      <a href="https://github.com/EnergizedProtection/block">Energized Basic</a>,
      <a href="https://github.com/EnergizedProtection/block">Regional</a>,
      <a href="https://github.com/bebasid/bebasid">bebasid</a>
    </td>
  </tr>
  <tr>
    <td style="text-align:right;vertical-align:center;">Adblock + Bypass + KaiAds</td>
    <td>Dapat menghilangkan iklan browser dan aplikasi, juga bypass Internet Positif</td>
    <td></td>
    <td></td>
    <td>
      <a href="https://github.com/EnergizedProtection/block">Energized Basic</a>,
      <a href="https://github.com/EnergizedProtection/block">Regional</a>,
      <a href="https://github.com/bebasid/bebasid">bebasid</a>,
      <a href="https://ivan-hc.github.io/bananahackers/ADBlock.html">KaiAds</a>
    </td>
  </tr>
</tbody>
</table>
<!--
## 🏁 Memulai <a id= "getting_started"></a>

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See [deployment](#deployment) for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them.

```
Give examples
```

### Installing

A step by step series of examples that tell you how to get a development env running.

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo.

## 🔧 Running the tests <a id= "tests"></a>

Explain how to run the automated tests for this system.

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## 🎈 Usage <a id="usage"></a>

Add notes about how to use the system.

## 🚀 Deployment <a id= "deployment"></a>

Add additional notes about how to deploy this on a live system.

## ⛏️ Built Using <a id= "built_using"></a>

- [MongoDB](https://www.mongodb.com/) - Database
- [Express](https://expressjs.com/) - Server Framework
- [VueJs](https://vuejs.org/) - Web Framework
- [NodeJs](https://nodejs.org/en/) - Server Environment

## ✍️ Authors <a id= "authors"></a>

- [@nattadasu](https://github.com/nattadasu) - Idea & Initial work

See also the list of [contributors](https://github.com/nattadasu/kaiOSHosts-ID/contributors) who participated in this project.

## 🎉 Acknowledgements <a id= "acknowledgement"></a>

- Hat tip to anyone whose code was used
- Inspiration
- References
-->

## 👣 Catatan Kaki <a id="footnotes"></a>

1. <a id= "fn1"></a> Baca: [BananaHackers.net - Adblock][kaiads]

<!--Links-->
[energized]: https://github.com/EnergizedProtection/block
[kaiads]: https://ivan-hc.github.io/bananahackers/ADBlock.html
[bebasid]: https://github.com/bebasid/bebasid