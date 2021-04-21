# OBJECT LITERAL

## Prakata

Pada materi kali ini, kita akan belajar mengenai `Object` pada JavaScript. Bagi kalian yang baru pertama kali membaca dokumen ini, sit back, relax and enjoy. Setelah kalian membaca dokumen ini, kalian akan mengetahui mengenai `Object` dan bagi kalian yang sudah mengetahui akan lebih memahaminya lagi.


## Daftar Isi
- Definisi
- Akses data
- Insert, update, delete
- Object vs Array
- Pass References (Will be updated later)
- Akses value di object of object
- Penamaan

## Definisi

Sebelum kita masuk ke dalam `Object`, mari kita bayangkan sebuah mobil. Dalam bahasa, `object` berarti sebuah benda. Mobil dalam hal ini adalah `object` atau benda. Pada mobil, terdapat properti atau atribut yang terkandung di dalamnya, seperti warna, harga, nama, merk, jumlah ban, jenis mesin, dan lain-lainnya. Begitu pula dengan `Object` pada pemrograman.

`Object` pada JavaScript adalah sebuah variable tunggal yang menyimpan banyak data dalam bentuk property. Untuk lebih memahaminya, mari kita lihat contohnya terlebih dahulu.

```js
let mobil = {
    warna: "biru",
    harga: 500000000,
    merk: "honda"
};
```
Pada contoh ini, kita memiliki sebuah variable yang memiliki data object. `Object` itu sendiri ditandai dengan ada kurung kurawal dan tiap data yang ada di dalamnya terdiri atas 1 pasang key dan value (key value pair). Key value pair ini bisa dikatakan sebagai property. Key adalah syntax yang ada di sebelah kiri titik dua (:), value adalah syntax yang ada di sebelah kanan titik dua (:).

## Akses Data

```js
let mobil = {
    warna: "biru",
    harga: 500000000,
    merk: "honda"
};
```
Mari kita lihat contoh kita ini. Untuk dapat mengakses value yang ada di dalam object mobil, kita dapat menggunakan 2 cara.

1. Menggunakan . (dot / titik)

```js
console.log(mobil.warna)
```
Untuk menggunakan . (dot), kita dapat menuliskan nama variable yang menyimpan object, kemudian tuliskan . (dot) setelah nama variablenya. Nah, apapun yang kita tulis setelah . (dot) akan secara mentah-mentah di anggap sebagai sebuah key yang ada di dalam object tersebut.


2. Menggunakan [] (bracket square / kurung siku)

```js
console.log(mobil["warna"]);

let key = "warna";
console.log(mobil[key]);
```

Berbeda dengan . (dot), penggunaan [] (bracket square) digunakan dalam kondisi tertentu. Apa saja kondisinya? 1. Pada saat value yang kita ingin akses memiliki key berupa string yang ada spasinya (e.g. "menu makanan"). 2. Pada saat kita ingin menggunakan variable sehingga key bersifat dinamis.

## Insert, Update, Delete

Mari kita buat sebuah variable yang menyimpan `Object` kosong.

```js
let person = {};
```

1. Insert

Mari kita masukan data baru ke dalam object person yang sudah kita buat.

```js
// Cara pertama
person.name = "Budi";
console.log(person);

// Cara kedua
let key = "hobbies";
person[key] = ["berenang", "makan", "coding"];
console.log(person);
```

2. Update

```js
person.name = "Andrean";
console.log(person);
```

Ternyata untuk mengupdate sebuah data di object, kita tinggal re-assign saja seperti biasa.

3. Delete

```js
delete person.hobbies;
```

Untuk delete kita bisa menggunakan delete operator.


## Object vs Array

Keduanya sama-sama struktur data. Namun, perbedaan utamanya adalah pada sifatnya.

1. Array menggunakan [] sedangkan Object menggunakan {} pada deklarasinya
2. Untuk mengakses item pada Array kita memerlukan index, sedangkan Object hanya butuh key
3. Jika kita ingin mencari sebuah item, kita harus mengakses tiap itemnya dengan looping, sedangkan Object hanya perlu key nya saja
4. Array digunakan untuk menyimpan data yang satu tipe, sedangkan Object digunakan untuk menyimpan data yang berkaitan satu sama lain.


## Object of Object

Seperti halnya Array multidimensi, Object juga mampu menyimpan Object lagi. Kita bayangkan saja, jika person (orang) mengendarai sebuah mobil (object). Tentunya kita bisa menyimpan semua properti mobil pada object mobil juga kan.

Untuk mengakses data pada Object of Object, mudahnya seperti ini.

```js
let person = {
    name: "budi",
    car: {
        brand: "honda",
        color: "black"
    }
};

// Display the color of the car
console.log(person.car.color);
```

Kita juga bisa menggunakan [] (kurung siku) untuk mengakses tiap valuenya.