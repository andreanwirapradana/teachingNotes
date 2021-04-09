# ECMA SCRIPT 6

## Pointers

- Variable Declaration (var, let, const)
- Hoisting
- Scope
- Template Literal


## Variable Declaration

Di dalam JavaScript terdapat beberapa syntax untuk mendeklarasikan variable.

1. var
2. let
3. const

Mari kita lihat satu persatu.

`var` adalah cara pertama yang kita pelajari untuk mendeklarasikan variable. Sayangnya, penggunaan `var` sudah tidak direkomendasikan lagi. Kenapa? Karena sifat daripada `var` itu sendiri.

`var` memiliki sifat di mana dirinya dapat di *re-declare*. Bayangkan saja, jika kita membuat sebuah app atau website yang terdiri dari banyak file dan ratusan lines of code, lalu di suatu line kita deklarasikan variable yang kita deklarasi dengan `var`. Maka yang akan terjadi adalah variable tersebut di deklarasikan ulang dan diberikan value yang kita yang berikan pada saat itu. Padahal variable tersebut adalah sebuah variable yang penting untuk program kita dan valuenya tidak boleh berubah. Tentunya hal ini akan menjadi sebuah masalah besar. Oleh karena itu, penggunaan `var` tidak lagi direkomendasikan bahkan bisa dikatakan sebagai bad practice.

`let` adalah syntax pendeklarasian variable yang kita gunakan saat value dari variable tersebut ingin kita rubah di lain waktu. Mari kita lihat contohnya.

```js
let phase = "Prep";
console.log(phase); // Expected output: Prep

phase = "Immersive";
console.log(phase) // Expected output: Immersive
```

Nah, di sini kita lihat bahwa value dari variable phase dapat berubah sesuai dengan keinginan kita.

Kemudian kita akan lihat bagaimana jika kita deklarasikan ulang.

```js
let number = 10;
let number = 99;
console.log(number); // Expected output: SyntaxError: Identifier 'number' has already been declared
```
Ternyata pada saat kita deklarasikan ulang, malah terjadi error. Dari sini kita bisa tahu bahwa kita tidak bisa mendeklarasikan variable yang menggunakan `let`. Tentunya ini sangat baik bagi kita, karena kita tidak akan bisa melakukan kesalahan seperti di `var` tadi.


`const` adalah syntax deklarasi variable yang digunakan saat kita tidak ingin merubah value dari variable tersebut di lain waktu. Artinya, value yang sudah kita assign kepadanya akan tetap sepanjang waktu, tidak bisa kita rubah lagi.

Mari kita lihat contohnya.
```js
const makanan = "Pizza";
console.log(makanan); // Expected output: Pizza
```

Sekarang kita lihat jika kita rubah value tersebut dengan yang lain.
```js
const makanan = "Pizza";
console.log(makanan); // Expected output: Pizza

makanan = "Bakso";
console.log(makanan); // Expected output: TypeError: Assignment to constant variable.
```
Ternyata error, ya. Dari errornya sendiri kita sudah bisa tahu bahwa kita tidak bisa mengganti value dari variable yang deklarasinya menggunakan `const`.

Lalu bagaimana dengan deklarasi ulang? Mari kita lihat.
```js
const makanan = "Pizza";
const makanan = "Bakso";
console.log(makanan); // Expected output: SyntaxError: Identifier 'nama' has already been declared
```
Sama dengan `let` tadi ya errornya. Kita tidak bisa mendeklarasikan ulang sebuah variable yang menggunakan `const`.


Jadi, mulai sekarang, gunakanlah `let` dan `const` untuk pendeklarasian variable.

## Hoisting

`Hoisting` adalah sebuah mekanisme JavaScript yang memindahkan semua **DEKLARASI** variable dan function ke paling atas *scope* nya. ika kalian belum belajar function, maka abaikan saja functionnya untuk sekarang.

Mari kita lihat contohnya.
```js
console.log(nama); // Expected output => undefined
var nama = "Poco";
```

Nah, jika kalian jeli, pasti akan ada merespon, "Tentu saja itu akan undefined, kan deklarasi variable nama dilakukan setelah console.log, bukan sebelumnya. Lalu apa bedanya dengan yang tanpa hoisting?"

Begini, seperti yang telah aku jelaskan, bahwa "Hoisting memindahkan semua deklarasi variable dan function ke paling atas scope". artinya yang dipindahkan ke atas adalah deklarasinya saja.

Sekarang kita lihat apa yang terjadi, jika kita console.log sebuah variable yang tidak sama sekali kita deklarasikan.
```js
console.log(umur); // Expected output => ReferenceError: umur is not defined
```

Nah, ternyata dia menjadi error dengan pesan *ReferenceError*. Ini berarti bahwa JavaScript sama sekali tidak tau variable yang kita ingin display. Bagi dirinya variable umur sama sekali tidak ada, BUKAN bernilai undefined.

Itulah `hoisting`, sebuah mekanisme JavaScript yang memindahkan semua deklarasi variable dan function ke paling atas scope nya.

## Scope

`Scope` mengacu pada konteks code yang menentukan aksesibilitas dari variable. Berat ya? Coba aku gambarkan ya.

```js
let tombol = true;
if (tombol) {
    let tv = "menyala";
};
```
Coba lihat potonga code ini. Di sini kita punya sebuah conditional yang memeriksa apakah value dari tombol bernilai true atau false. Kemudian ada kurung kurawal ({}). Nah, semua yang di dalam kurung kurawal tersebut disebut sebagai scope dari conditionalnya. Kita lihat juga bahwa ada variable tv yang kita deklarasikan di dalam conditional tersebut. Jika kita console.log(tv) di luar dari scope, maka kita akan mendapatkan error bahwa variable tv tidak dideklarasikan. Kenapa? Karena hidup dan matinya variable tv hanya berada di scope conditional tempat dia dideklarasikan.

Ada dua jenis scope, yaitu:
1. Global: Semua variable yang kita deklarasikan di luar kurung kurawal apapun akan masuk ke scope global. Variable ini disebut juga sebagai variable global.
2. Local: Semua variable yang dideklarasikan di dalam kurung kurawal.

Untuk penggunaannya, tergantung dari kebutuhan.

## Template Literal

Pernahkah kalian merasa bahwa membuat string yang di dalamnya ada variable itu sangat merepotkan saat kita harus concating string dan variablenya? Nah, JavaScript punya jawaban untuk problem itu, yaitu `Template Literal`.

Horeee!!! Sekarang aku gak perlu bingung lagi menaruh spasi.

Betul banget teman-teman, dengan adanya `template literal` kita akan lebih mudah membuat string yang di dalamnya ada variable. Mari kita lihat contohnya.

```js
let hobi = "Ngoding";
console.log(`Hobiku adalah ${hobi}`);
```

Mari kita bedah. Untuk menggunakan `template literal` kita membutuhkan kutip khusus, yaitu *backtick*. Teman-teman bisa menemukannya di sebelah tombol 1 pada keyboard kalian. Semua yang diapit oleh *backtick* akan menjadi string.

Kemudian untuk menaruh variable di dalamnya, kita memerlukan dolar sign ($) dan kurung kurawal ({}). Lihat contoh kembali!

Sekarang jauh lebih mudah, kan.