# MODULAR FUNCTIONS

## Daftar Isi
- Definisi
- Invoke (Direct & Storing)
- Naming

## Definisi

Modular Function adalah satu bagian dari konsep Modular pada Programming. Lalu, apa sih itu Modular? Modular adalah teknik design / rancangan yang menekankan pada pemisahan fungsionalitas program menjadi module-module yang independent. Nah, salah satu turunan dari konsep modular ini adalah modular function. Modular function berarti merupakan pemisahan function-function pada program sehingga tiap function melakukan satu aktivitas / proses yang spesifik dan berdiri sendiri.

Kenapa hal ini kita lakukan? Salah satunya adalah untuk membuat program yang kita buat menjadi DRY atau "Don't Repeat Yourself". Selain itu kita juga membuat program kita lebih mudah untuk dipelihara (maintain). Saat ada bug atau update, kita hanya perlu merubah function yang bermasalah atau menambah function baru tanpa perlu merusak function yang lainnya.

Sebenarnya untuk sekarang, ada cara lebih mudah dalam memahami modular function, yaitu, pemanggilan function di function lainnya. Selama ini, kita memanggil suatu function pada scope global. Nah, modular function ini, kita memanggil suatu function pada scope local (dalam function lain).

Untuk lebih jelas, mari kita lihat contoh dengan membuat sebuah program kalkulator yang dapat menambah dan mengurang 2 angka:
```js
function tambah(num1, num2) {
    return num1 +  num2;
};

function kurang(num1, num2) {
    return num1 - num2;
};

function kalkulator(num1, num2, operator) {
    switch(operator) {
        case "+":
            let hasilTambah = tambah(num1, num2);
            return hasilTambah;
        case "-":
            return kurang(num1, num2);
        default:
            return `${operator} tidak dikenali sebagai operator matematika yang terdaftar.`;
    };
};

console.log(kalkulator(1, 1, "+"))
```

Pada contoh di atas, kita memiliki 3 function. Mari kita lihat satu persatu tiap functionnya. Jika kita lihat dari function yang paling atas, kita punya function tambah yang menerima 2 parameter yaitu num1 dan num2, dan fungsi ini bertugas untuk menambahkan 2 angka yang diberikan. Kemudian ada fungsi kurang yang menerima 2 parameter juga dan berfungsi untuk mengurangi 2 angka yang diberikan. Lalu, yang terakhir adalah fungsi kalkulator yang menerima 3 parameter, yaitu num1, num2 dan operator.

Sebelum melajut lebih jauh, kita harus ingat bahwa deklarasi function itu di hoisting oleh javascript secara otomatis, jadi penempatan functionnya tidak bermasalah.

Jika kita lihat lebih detail pada function kalkulator, kita dapat melihat adanya pemanggilan function tambah dan kurang. Secara simple, inilah bentuk modular function. Saat kita sudah berhasil memisahkan tiap fungsionalitas dari program kita dan bisa dipanggil di function utama yang menjalankannya.

## Invoke

Mari kita lihat contoh kalkulator kita lagi,
```js
function tambah(num1, num2) {
    return num1 +  num2;
};

function kurang(num1, num2) {
    return num1 - num2;
};

function kalkulator(num1, num2, operator) {
    switch(operator) {
        case "+":
            let hasilTambah = tambah(num1, num2);
            return hasilTambah;
        case "-":
            return kurang(num1, num2);
        default:
            return `${operator} tidak dikenali sebagai operator matematika yang terdaftar.`;
    };
};

console.log(kalkulator(1, 1, "+"))
```

Kita masih berfokus pada fungsi kalkulator, lebih tepatnya pada invocation function tambah dan kurang. Di sini kita melihat bahwa hasilTambah merupakan sebuah variable yang valuenya adalah pemanggilan function tambah. Sehingga, variable hasilTambah akan memiliki hasil dari proses function tambah.

Sekarang kita lihat yang kedua, di function kurang. Pada function kurang kita secara langsung memanggil function kurang dan langsung kita return.

Jadi, sebenarnya ada 2 cara untuk memanggil function pada modular function. Pertama, kita simpan pada sebuah variable. Ini dilakukan saat hasil dari function tersebut ingin gunakan pada proses lain. Sedangkan yang Kedua adalah dengan mengembalikan dan memanggilnya secara langsung. Ini dilakukan saat function tersebut tidak memiliki proses lanjutan lagi.

## Naming

Karena pada modular function kita akan berhadapan dengan banyak function, maka pastikan bahwa nama dari setiap function itu berbeda dan sesuai dengan aktivitas yang dia lakukan (jangan sampai ada ambiguitas). Untuk memudahkan kita dalam menamakannya, kita dapat bagi tiap function ke dalam 2 jenis function, yaitu Main function yang bertugas untuk memanggil semua function kecil dan melakukan proses utama. Kita bisa bayangkan dia sebagai pabrik secara keseluruhan. Jenis yang kedua adalah subfunction, di mana kita bisa bayangkan dia sebagai mesin-mesin yang ada di dalam pabrik. Main function menjadi tempat di mana semua sub function di panggil.

Main function kita bisa namakan dengan nama program kita, sedangkan sub function kita bisa namakan dengan proses yang dia kerjakan.