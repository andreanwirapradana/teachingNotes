# ARRAY

## Daftar Isi
- Definisi
- Deklarasi
- Array vs String
- Akses Data (manual & loop)
- Manipulasi Data

## Definisi

Array adalah sebuah variable tunggal yang mampu menyimpan lebih dari satu data. Kita bisa membayangkan `array` seperti sebuah lemari. Kita ambil contoh, lemari buku. Lemari buku dapat menyimpan lebih dari pada satu buku. Begitu pula dengan array, di dalam array kita bisa menyimpan string, number, boolean atau tipe data apapun.

Array merupakan sebuah struktur data. Apa itu struktur data? Banyak data yang dikumpulkan ke dalam suatu tempat dengan posisi tertentu sehingga mudah terbaca. Begitulah array. Kita menggunakan array untuk mengelompokkan data-data yang saling berkaitan sehingga mudah (make sense) untuk dibaca.

## Deklarasi

Untuk mendeklarasikan array pada sebuah variable, kita dapat melakukan hal ini:

```js
let lemariBuku = ["Harry potter", "Eloquent JavaScript"];
```
Mari kita bedah contoh kita. Untuk mendeklarasikan sebuah array, kita memerlukan kurung siku ([]), kemudian di apit di dalamnya kita bisa tuliskan data-data apa saja yang kita inginkan. Namun, tiap item atau element yang kita taruh di dalamnya kita harus pisahkan dengan koma (,).


## Array vs String

Mari kita lihat dua variable ini:

```js
let book = "Angels and demons";
let books = ["Harry potter", "Eloquent JavaScript"];
```
Pada variable book (perhatikan namanya singular), hanya terdapat 1 data saja yang kita simpan di dalamnya, yaitu sebuah string Angels and Demons. Lalu, kita lihat variable books (perhatikan namanya plural). Pada variable tersebut kita menyimpan sebuah array yang memiliki banyak judul buku.

Kedua variable ini (array dan string) memiliki properti length. Kita bisa mengetahui berapa banyak element/item yang tersimpan pada array dengan .length. Namun, seperti yang kita tahu bahwa kita tidak bisa mengubah sebuah karakter di dalam string secara langsung. Hal ini berbeda dengan array yang mana kita bisa merubah element-element di dalamnya secara langsung. Untuk lebih jelasnya, mari kita maju ke bab selanjutnya.

## Akses Data

Mari kita lihat bagaimana cara kita mengakses suatu data/element/item di dalam array.

```js
let books = ["Harry potter", "Eloquent JavaScript"];
```
Kita akan menggunakan variable yang sama, yaitu books. Di sini kita akan mencoba untuk mengakses Harry Potter. Temen-temen tentunya ingat bahwa nomor urut pada JavaScript selalu di mulai dari 0 dan untuk mengakses suatu karakter pada string, kita bisa menggunakan kurung siku ([]), *ingat index*.

```js
console.log(books[0]);
```
Hasil dari code di atas adalah string Harry Potter.

Itulah cara mengakses suatu item pada array. Sama halnya dengan string, kita menggunakan konsep indexing untuk mengaksesnya.

Sekarang kita akan lihat bagaimana cara mengakses semua item di dalam array secara dinamis menggunakan looping.

```js
let books = ["Harry potter", "Eloquent JavaScript"];
```
Kita akan menggunakan variable yang sama seperti sebelumnya.

```js
for (let i = 0; i < books.length; i++) {
    console.log(books[i]);
}
```
Nah, dengan code ini, kita akan mengakses semua item di dalam array books secara dinamis.

## Manpipulasi Data

Kita akan lanjutkan pembahasan kita di Array vs String. Mari kita lihat apakah kita bisa merubah suatu karakter di dalam string secara langsung.

```js
let str = "makan";
str[0] = "M";
console.log(str);
```
Jika kita jalankan code ini, maka kita akan melihat kata makan dengan m kecil. Kenapa ini terjadi? Padahal kita sudah akses dan re-assign dengan M besar. Ya, karena pada dasarnya semua data primitif seperti string, merupakan satu value. Kita bisa bayangkan seperti sebuah baju berwarna kuning. Untuk merubah warna baju tersebut menjadi biru, maka kita tidak bisa mengambil warnanya kemudian merubahnya dengan biru. Perlu ada proses yang dilakukan untuk bisa merubahnya menjadi warna biru.

Berbeda dengan array. Array bukanlah data primitif. Dia adalah struktur data. Tiap element atau item yang disimpan di dalamnya, bisa kita akses dan rubah sesuai keinginan kita.

```js
let books = ["Harry potter", "Eloquent JavaScript"];
books[0] = "Eragon";
console.log(books);
```
Saat kita jalankan codenya, element pertama yang tadinya Harry Potter, telah berubah menjadi Eragon.

Kita juga bisa merubah tiap item di dalam array secara dinamis dengan menggunakan loop (silahkan dicoba secara mandiri ya).

### Built-in Functions Array

Built-in functions atau disebut sebagai Method adalah function-function yang bisa kita gunakan untuk melakukan hal spesifik pada array. Silahkan cek dokumentasi mdn untuk mengetahui apa saja methods yang ada pada array.

Pada kali ini, kita akan mempelajari 4 built-in functions di dalam array. Apa saja?

1. Push
    
    berguna untuk memasukkan element baru ke belakang array.
    ```js
    let books = ["Harry potter", "Eloquent JavaScript"];
    books.push("PPKN");
    ```
2. Pop
    
    berguna untuk menghilangkan element terbelakang array.
    ```js
    let books = ["Harry potter", "Eloquent JavaScript"];
    books.pop()
    ```
3. Unshift

    berguna untuk memasukkan element baru ke depan array.
    ```js
    let books = ["Harry potter", "Eloquent JavaScript"];
    books.unshift("PPKN");
    ```
4. Shift

    berguna untuk menghilangkan item terdepan array.
    ```js
    let books = ["Harry potter", "Eloquent JavaScript"];
    books.shift();
    ```
