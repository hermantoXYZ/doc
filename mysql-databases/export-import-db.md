---
hidden: true
icon: arrow-down-left-and-arrow-up-right-to-center
---

# Export/Import DB

Ini menjadi penting ketika sdr mengelola sejumlah project, disini saya akan bagikan cara saya mengelola database MySQL dalam project saya, pertama saya akan melakukan export database dari layanan hosting yang saya gunakan.

## 1.1 Export Database dari PhpMyadmin&#x20;

Sebagai user interfacenya kita menggunakan PhpmyAdmin untuk mengelola database MySQL.

> ## A web-based application that provides a user interface for database operations

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Pilih metode ekspor:
  * **Quick**: Ekspor cepat tanpa pengaturan tambahan.
  * **Custom**: Mengatur opsi ekspor seperti format file dan tabel.
  * Klik tombol **Go** untuk mengunduh file `.sql`.

Selain cara tersebut, dapat mengggunakan `Menggunakan Command Line`untuk mengexport database yang anda kelola.

Gunakan perintah `mysqldump` untuk mengekspor database ke file `.sql`.

`mysqldump -u username -p database_name > backup_file.sql`

## 1.2 Export Database MySQL

