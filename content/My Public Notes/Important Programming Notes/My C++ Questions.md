### Needed to be sort out

#### Post vs pre

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 5;
    int b = a--; // post-decrement
    int c = --a; // pre-decrement
    cout << "b = " << b << endl;
    cout << "c = " << c << endl;
    cout << "a = " << a << endl;
    return 0;
}
```

---

### 🔹 1. `int a = 5;`

- Nilai awal: `a = 5`.
    

---

### 🔹 2. `int b = a--;`

👉 **Post-decrement** berarti:

1. Ambil nilai `a` dulu (yang masih 5).
    
2. Simpan ke `b`. → jadi `b = 5`.
    
3. Baru setelah itu, kurangi `a` satu angka. → jadi `a = 4`.
    

📌 Setelah baris ini:

- `a = 4`
    
- `b = 5`
    

---

### 🔹 3. `int c = --a;`

👉 **Pre-decrement** berarti:

1. Kurangi dulu nilai `a`. → `a = 3`.
    
2. Baru simpan ke `c`. → jadi `c = 3`.
    

📌 Setelah baris ini:

- `a = 3`
    
- `c = 3`
    

---

### 🔹 4. Output

Sekarang dicetak:

```
b = 5
c = 3
a = 3
```

---

### 🔑 Intinya:

- `x--` (**post-decrement**) → pakai dulu nilai lama `x`, baru dikurangi.
    
- `--x` (**pre-decrement**) → kurangi dulu `x`, baru pakai hasilnya.
    

---

👉 Analogi sederhana:  
Bayangkan kamu punya **apel di tangan** 🍎.

- Kalau `b = a--` (post):  
    Kamu **kasih apel dulu ke temanmu**, lalu kamu makan 1 apel.
    
- Kalau `c = --a` (pre):  
    Kamu **makan dulu 1 apel**, baru kasih sisanya ke temanmu.
    

---

#### Pass by value vs pass by reference


---

## 🔹 1. Pass by Value

👉 **Artinya:**  
Ketika kita memanggil fungsi, **nilai asli dari variabel dikirimkan salinannya (copy)** ke fungsi.

- Fungsi hanya mengubah salinan.
    
- Nilai asli di luar fungsi **tidak berubah**.
    

📌 Contoh:

```cpp
#include <iostream>
using namespace std;

void tambahLima(int x) {
    x = x + 5;
    cout << "Di dalam fungsi, x = " << x << endl; //15
}

int main() {
    int a = 10;
    tambahLima(a);
    cout << "Di luar fungsi, a = " << a << endl; //10
    return 0;
}
```

👉 Output:

```
Di dalam fungsi, x = 15
Di luar fungsi, a = 10
```

📝 Penjelasan:

- `a` dikirim sebagai **salinan** ke parameter `x`.
    
- `x` berubah, tapi `a` di luar tetap **10**.
    

---

## 🔹 2. Pass by Reference

👉 **Artinya:**  
Ketika kita memanggil fungsi, yang dikirimkan adalah **alamat/rujukan (reference)** variabel.

- Fungsi akan mengubah variabel aslinya.
    
- Nilai asli di luar fungsi **ikut berubah**.
    

📌 Contoh:

```cpp
#include <iostream>
using namespace std;

void tambahLima(int &x) {  // tanda & artinya by reference
    x = x + 5;
    cout << "Di dalam fungsi, x = " << x << endl;
}

int main() {
    int a = 10;
    tambahLima(a);
    cout << "Di luar fungsi, a = " << a << endl;
    return 0;
}
```

👉 Output:

```
Di dalam fungsi, x = 15
Di luar fungsi, a = 15
```

📝 Penjelasan:

- `a` dikirim ke fungsi sebagai **referensi (alamat asli)**.
    
- Jadi ketika `x` diubah dalam fungsi, `a` di luar juga berubah.
    

---

## 🔑 Perbandingan Singkat

|Cara|Kode|Efek|
|---|---|---|
|**Pass by Value**|`void f(int x)`|Fungsi dapat salinan variabel → variabel asli tidak berubah|
|**Pass by Reference**|`void f(int &x)`|Fungsi dapat referensi (alamat variabel asli) → variabel asli bisa berubah|

---

👉 **Analogi Sehari-hari:**

- Pass by Value → seperti kamu **fotokopi kunci** dan kasih ke teman. Kalau teman rusak, kunci aslinya aman.
    
- Pass by Reference → kamu kasih **kunci asli** ke teman. Kalau hilang atau bengkok, aslinya ikut kena.
    

---
#### struct vs array

## 🔹 1. Array

👉 **Array** adalah kumpulan **data dengan tipe yang sama** yang disimpan berurutan dalam satu variabel.

📌 Contoh:

```cpp
#include <iostream>
using namespace std;

int main() {
    int angka[5] = {10, 20, 30, 40, 50}; // array dengan 5 elemen
    
    cout << angka[0] << endl; // cetak elemen pertama (10)
    cout << angka[3] << endl; // cetak elemen ke-4 (40)
    return 0;
}
```

📝 Catatan:

- Semua elemen harus **tipe data yang sama** (contoh: semua `int`).
    
- Elemen diakses pakai **indeks** (`[0]`, `[1]`, dst).
    

---

## 🔹 2. Struct

👉 **Struct** (structure) adalah **kumpulan data yang bisa berbeda tipe** tapi masih dalam satu kesatuan.

📌 Contoh:

```cpp
#include <iostream>
using namespace std;

// definisi struct
struct Mahasiswa {
    string nama;
    int umur;
    float ipk;
};

int main() {
    Mahasiswa mhs1; // buat variabel dari struct
    mhs1.nama = "Naruto";
    mhs1.umur = 19;
    mhs1.ipk = 3.9;

    cout << "Nama: " << mhs1.nama << endl;
    cout << "Umur: " << mhs1.umur << endl;
    cout << "IPK: " << mhs1.ipk << endl;

    return 0;
}
```

👉 Output:

```
Nama: Naruto
Umur: 19
IPK: 3.9
```

📝 Catatan:

- Dalam **satu struct**, kamu bisa gabungin data berbeda tipe (`string`, `int`, `float`, dll).
    
- Struct cocok untuk merepresentasikan **satu objek nyata** (misalnya seorang mahasiswa, sebuah mobil, sebuah buku, dll).
    

---

## 🔑 Perbandingan Array vs Struct

|Fitur|**Array**|**Struct**|
|---|---|---|
|Tipe data|Semua elemen **harus sama tipe**|Bisa gabungan tipe data berbeda|
|Akses|Pakai **indeks** (`[0]`, `[1]`, dst)|Pakai **nama field** (`.nama`, `.umur`, dst)|
|Kegunaan|Menyimpan **banyak data sejenis** (misalnya daftar nilai ujian)|Menyimpan **satu objek kompleks** dengan banyak atribut (misalnya data mahasiswa)|

---

👉 **Analogi sehari-hari:**

- **Array** = rak buku 📚 → semua isinya buku (sama tipe).
    
- **Struct** = kartu identitas 🪪 → isinya nama (string), umur (int), alamat (string), tinggi badan (float). Data bisa campur.

#### Function in general

# 🔹 Jenis Fungsi di C++

## 1. **Void Function (tanpa return value)**

```cpp
void sapa() {
    cout << "Halo Chelsy!" << endl;
}
```

👉 **Kapan dipakai?**

- Kalau fungsi hanya **melakukan aksi** (misalnya mencetak, menyimpan data, mengupdate sesuatu) dan **tidak perlu mengembalikan nilai**.
    
- Cocok untuk menulis “perintah saja”, bukan perhitungan.
    

📌 Contoh nyata: fungsi untuk menampilkan menu, mencetak pesan, membersihkan layar, dsb.

---

## 2. **Function dengan Return Value**

```cpp
int tambah(int a, int b) {
    return a + b;
}
```

👉 **Kapan dipakai?**

- Kalau fungsi perlu **menghasilkan sebuah nilai** yang akan dipakai di tempat lain.
    
- Cocok untuk perhitungan, logika, atau pemrosesan data.
    

📌 Contoh nyata: fungsi untuk menghitung luas lingkaran, mencari maksimum dari dua angka, menghitung total belanja, dsb.

---

## 3. **Function dengan Parameter**

```cpp
void cetakPesan(string nama) {
    cout << "Halo " << nama << "!" << endl;
}
```

👉 **Kapan dipakai?**

- Kalau kita ingin fungsi **fleksibel** dengan masukan berbeda-beda.
    
- Membuat fungsi bisa digunakan ulang untuk banyak kasus.
    

📌 Contoh nyata: fungsi yang menerima nama, angka, atau data lain, lalu bekerja sesuai inputnya.

---

## 4. **Function dengan Parameter Default**

```cpp
void sapa(string nama = "Teman") {
    cout << "Halo " << nama << endl;
}
```

👉 **Kapan dipakai?**

- Kalau kamu ingin fungsi bisa dipanggil **dengan atau tanpa parameter**.
    
- Cocok untuk kasus “nilai standar” kalau tidak diberikan input.
    

📌 Contoh nyata: fungsi menyapa dengan nama default kalau pengguna tidak mengisi namanya.

---

## 5. **Pass by Value Function**

```cpp
void ubah(int x) {
    x = 10; // hanya ubah salinan
}
```

👉 **Kapan dipakai?**

- Kalau kamu **tidak ingin variabel asli berubah** di luar fungsi.
    
- Cocok untuk operasi sementara atau hanya butuh salinan.
    

📌 Contoh nyata: hitung luas dari nilai yang dikirim, tapi jangan mengubah nilai aslinya.

---

## 6. **Pass by Reference Function**

```cpp
void ubah(int &x) {
    x = 10; // ubah nilai asli
}
```

👉 **Kapan dipakai?**

- Kalau kamu ingin **fungsi bisa mengubah nilai variabel asli** di luar fungsi.
    
- Cocok untuk update data, swap variabel, atau efisiensi (agar tidak menyalin data besar).
    

📌 Contoh nyata: fungsi yang mengupdate skor, mengisi array, atau menukar dua angka.

---

## 7. **Overloaded Function**

```cpp
int tambah(int a, int b) { return a + b; }
double tambah(double a, double b) { return a + b; }
```

👉 **Kapan dipakai?**

- Kalau kamu ingin **nama fungsi sama**, tapi bisa bekerja untuk tipe data berbeda.
    
- Cocok untuk operasi umum seperti penjumlahan, perbandingan, dll.
    

📌 Contoh nyata: `tambah(3,4)` dan `tambah(2.5, 1.2)` tetap bisa dipanggil dengan nama sama.

---

## 8. **Recursive Function**

```cpp
int faktorial(int n) {
    if (n == 1) return 1;
    return n * faktorial(n-1);
}
```

👉 **Kapan dipakai?**

- Kalau masalah bisa dipecah menjadi **masalah yang sama tapi lebih kecil**.
    
- Cocok untuk perhitungan matematis (faktorial, fibonacci, GCD), struktur pohon, algoritma DFS, dll.
    

📌 Contoh nyata: menghitung faktorial, menelusuri folder dalam folder.

---

# 🔑 Rangkuman Pemilihan Fungsi

| Jenis Fungsi          | Kapan Dipakai                                              |
| --------------------- | ---------------------------------------------------------- |
| **Void**              | Hanya melakukan aksi, tidak perlu hasil balik              |
| **Return value**      | Butuh hasil untuk dipakai lagi di luar fungsi              |
| **Parameter**         | Fungsi perlu input dari luar agar fleksibel                |
| **Default parameter** | Fungsi bisa dipakai dengan atau tanpa input                |
| **Pass by Value**     | Data asli tidak boleh berubah                              |
| **Pass by Reference** | Data asli harus bisa diubah/diperbarui                     |
| **Overloading**       | Nama fungsi sama tapi untuk tipe data berbeda              |
| **Recursive**         | Masalah bisa dipecah menjadi masalah lebih kecil yang sama |

---

👉 **Analogi Sederhana:**

- Fungsi `void` = **orang yang cerita** tapi tidak kasih hasil.
    
- Fungsi dengan return = **orang yang kasih jawaban/angka**.
    
- Pass by value = **pinjam fotokopi dokumen** (asli aman).
    
- Pass by reference = **pinjam dokumen asli** (kalau ditulis ulang, aslinya ikut berubah).
    

---
Contoh sederhana
---

## 1. Fungsi dengan `return` (mengembalikan nilai)

- Digunakan saat kita ingin fungsi **menghasilkan sebuah nilai** untuk dipakai lagi.
    
- Misalnya: menghitung hasil penjumlahan, luas, atau nilai tertentu.
    

### Contoh:

```cpp
#include <iostream>
using namespace std;

// Fungsi dengan return (mengembalikan int)
int tambah(int a, int b) {
    return a + b;  // hasil dikembalikan ke pemanggil
}

int main() {
    int hasil = tambah(5, 3);  // memanggil fungsi
    cout << "Hasil tambah: " << hasil << endl;  // Output: 8
    return 0;
}
```

➡️ Gunakan `return` jika kamu perlu **nilai balik** dari fungsi.

---

## 2. Fungsi `void` (tidak mengembalikan nilai)

- Dipakai saat fungsi hanya melakukan **aksi**, bukan menghitung hasil.
    
- Misalnya: menampilkan teks, mencetak data, atau mengubah sesuatu tapi tidak perlu mengembalikan nilai.
    

### Contoh:

```cpp
#include <iostream>
using namespace std;

// Fungsi void (tidak mengembalikan nilai)
void sapa() {
    cout << "Halo, selamat belajar C++!" << endl;
}

int main() {
    sapa();  // memanggil fungsi
    return 0;
}
```

➡️ Gunakan `void` jika fungsi hanya **melakukan sesuatu**, bukan memberi hasil.

---

## 3. Fungsi dengan Pass by Reference (`&`)

- Digunakan saat kita ingin **mengubah langsung nilai variabel di luar fungsi**.
    
- Ini hemat memori (tidak membuat salinan).
    
- Berguna saat kamu ingin data yang diproses langsung berubah.
    

### Contoh:

```cpp
#include <iostream>
using namespace std;

// Fungsi pass by reference (parameter pakai &)
void ubahNilai(int &x) {
    x = x * 2;  // nilai x akan langsung berubah
}

int main() {
    int angka = 10;
    ubahNilai(angka);  
    cout << "Nilai angka setelah fungsi: " << angka << endl;  // Output: 20
    return 0;
}
```

➡️ Gunakan reference (`&`) kalau fungsi harus **mengubah data asli**.

---

## Ringkasan kapan dipakai:

- **`return`** → kalau fungsi harus memberi nilai balik.
    
- **`void`** → kalau fungsi hanya menjalankan aksi (cetak, log, dll).
    
- **`reference (&)`** → kalau ingin data asli yang dikirim ke fungsi ikut berubah.
    

---