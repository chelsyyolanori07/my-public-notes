## Stack Linked List

### 📚 Konsep Stack dengan Linked List

**Stack** adalah struktur data LIFO (Last-In-First-Out) dimana elemen terakhir yang dimasukkan akan menjadi elemen pertama yang dikeluarkan.

### 🎯 Karakteristik Stack Linked List:

- **Top** selalu menunjuk ke node teratas
    
- Setiap **node** berisi data dan pointer ke node berikutnya
    
- **Dinamis** - ukuran dapat bertambah/shrink sesuai kebutuhan
    
- Tidak ada batasan maksimal (kecuali memory)


```
TOP → [Data|Next] → [Data|Next] → [Data|Next] → NULL
```

### Penjelasan Fungsi-Fungsi
#### 1. IsEmpty Function

```cpp
bool Isempty(tumpukan first) {
    return first == NULL;
}
```
**Fungsi**: Mengecek apakah stack kosong  
**Proses**: 
- Cek apakah pointer `first` menunjuk ke NULL
- Jika NULL, berarti stack kosong

```
Diagram:
first → NULL
Status: KOSONG
```

#### 2. IsFull Function
```cpp
bool Isfull(tumpukan first) {
    int count = 0;
    tumpukan hitung = first;
    while (hitung != NULL) {
        count++;
        hitung = hitung->next;
    }
    return count == MAX;
}
```
**Fungsi**: Mengecek apakah stack penuh  
**Proses**:
- Traverse linked list sambil menghitung node
- Bandingkan jumlah node dengan MAX

```
Contoh:
first → [A|•] → [B|•] → [C|NULL]
Count: 3
MAX: 100
Status: TIDAK PENUH
```

#### 3. Clear Function
```cpp
void clear(tumpukan &first) {
    first = NULL;
}
```
**Fungsi**: Mengosongkan seluruh stack  
**Proses**:
- Set pointer `first` menjadi NULL
- Semua node akan terputus dari linked list

```
Sebelum:
first → [A|•] → [B|•] → [C|NULL]

Sesudah:
first → NULL
```
#### 4. Push Function
```cpp
void push(tumpukan &first, char value) {
    if (Isfull(first)) {
        cout << "Tumpukan penuh" << endl;
    } else {
        Node* tambah = new Node;
        tambah->data = value;
        tambah->next = first;
        first = tambah;
        cout << "Data '" << value << "' berhasil ditambahkan" << endl;
    }
}
```
**Fungsi**: Menambahkan elemen ke stack  
**Proses**:
1. Buat node baru
2. Isi data dengan value
3. Pointer next node baru menunjuk ke node yang sebelumnya menjadi first
4. Pointer first sekarang menunjuk ke node baru

```
Contoh push('X'):

Sebelum:
first → [A|•] → [B|•] → [C|NULL]

Proses:
1. Buat node: [X|•]
2. Set next: [X|•] → [A|•] → [B|•] → [C|NULL]
3. Update first: first → [X|•]

Sesudah:
first → [X|•] → [A|•] → [B|•] → [C|NULL]
```
#### 5. Pop Function
```cpp
char pop(tumpukan &first) {
    if (Isempty(first)) {
        cout << "Tumpukan kosong" << endl;
        return '\0';
    } else {
        char popped = first->data;
        tumpukan hapus = first;
        first = first->next;
        delete hapus;
        return popped;
    }
}
```
**Fungsi**: Mengambil dan menghapus elemen dari stack  
**Proses**:
1. Simpan data dari node first
2. Simpan alamat node yang akan dihapus
3. Geser first ke node berikutnya
4. Hapus node lama

```
Contoh pop():

Sebelum:
first → [X|•] → [A|•] → [B|•] → [C|NULL]

Proses:
1. popped = 'X'
2. hapus = alamat node X
3. first = first->next → [A|•]
4. delete node X

Sesudah:
first → [A|•] → [B|•] → [C|NULL]
Return: 'X'
```
#### 6. Peek Function
```cpp
char peek(tumpukan first) {
    if (Isempty(first)) {
        cout << "Tumpukan kosong" << endl;
        return '\0';
    }
    return first->data;
}
```
**Fungsi**: Melihat elemen teratas tanpa menghapus  
**Proses**:
- Ambil data dari node first tanpa mengubah struktur

```
Contoh:
first → [A|•] → [B|•] → [C|NULL]
Return: 'A'
```
#### 7. Display Function
```cpp
void display(tumpukan first) {
    tumpukan bantu = first;
    if (Isempty(first)) {
        cout << "Tumpukan kosong" << endl;
    } else {
        cout << "Isi tumpukan: " << endl;
        while (bantu != NULL) {
            cout << bantu->data << endl;
            bantu = bantu->next;
        }
        cout << endl;
    }
}
```
**Fungsi**: Menampilkan seluruh isi stack  
**Proses**:
- Traverse linked list dari first sampai NULL
- Tampilkan data setiap node

```
Contoh:
first → [A|•] → [B|•] → [C|NULL]

Output:
Isi tumpukan:
A
B
C
```

### Keunggulan Stack Linked List:
1. **Dinamis** - Tidak ada batasan maksimum (kecuali batasan memori)
2. **Efisien** - Operasi push/pop O(1)
3. **Flexible** - Ukuran dapat berubah sesuai kebutuhan

### Kelemahan:
1. **Memory overhead** - Setiap node butuh space untuk pointer next
2. **Akses terbatas** - Hanya bisa akses elemen teratas

## Stack Array

### 📚 Konsep Stack Array

Stack Array adalah struktur data stack yang diimplementasikan menggunakan array. Prinsip LIFO (Last-In-First-Out) diimplementasikan dengan pointer `top` yang menunjuk ke elemen teratas.

```
Index:   0    1    2   ...  MAX-1
Data:   [ ]  [ ]  [ ]  ...  [ ]
     ↑
    top = -1 (kosong)
```

### Penjelasan Fungsi
#### 1. Struktur Datanya
```cpp
struct Stack {
    char data[MAX];
    int top;
};
```
**Struktur Data**: 
- `data[MAX]`: Array untuk menyimpan elemen stack
- `top`: Index yang menunjuk ke elemen teratas

```
Initial state:
Index:  0   1   2   3   4   ...  MAX-1
Data:  [ ] [ ] [ ] [ ] [ ] ...   [ ]
top = -1
```

#### 2. IsEmpty Function
```cpp
bool isempty(Stack s) {
    return s.top == -1;
}
```
**Fungsi**: Mengecek apakah stack kosong  
**Proses**: 
- Cek apakah `top` bernilai -1

```
Contoh:
top = -1
Status: KOSONG

top = 2
Status: TIDAK KOSONG
```
#### 3. IsFull Function
```cpp
bool isfull(Stack s) {
    return s.top == MAX - 1;
}
```
**Fungsi**: Mengecek apakah stack penuh  
**Proses**:
- Cek apakah `top` sudah mencapai index terakhir array

```
Contoh MAX = 5:
top = 4 → Status: PENUH
top = 3 → Status: TIDAK PENUH
```
#### 4. Inisialisasi Stack
```cpp
void init(Stack &s) {
    s.top = -1;
}
```
**Fungsi**: Inisialisasi stack  
**Proses**:
- Set `top` menjadi -1 (menandakan stack kosong)

```
Sebelum: top = 2
Data: [A] [B] [C] [ ] [ ]

Sesudah: top = -1
Data: [A] [B] [C] [ ] [ ]  (data masih ada tapi dianggap tidak valid)
```
#### Push Function
```cpp
void push(Stack &s, char value) {
    if (isfull(s)) {
        cout << "Tumpukan penuh" << endl;
    } else {
        s.top++;
        s.data[s.top] = value;
        cout << "Data '" << value << "' berhasil ditambahkan" << endl;
    }
}
```
**Fungsi**: Menambahkan elemen ke stack  
**Proses**:
1. Naikkan `top` terlebih dahulu
2. Isi array pada posisi `top` dengan value

```
Contoh push('X'):

Sebelum:
Index:  0   1   2   3   4
Data:  [A] [B] [C] [ ] [ ]
     ↑       ↑
    index0  top=2

Proses:
1. top++ → top = 3
2. data[3] = 'X'

Sesudah:
Index:  0   1   2   3   4
Data:  [A] [B] [C] [X] [ ]
           ↑
        top=3
```
#### 5. Pop Function
```cpp
char pop(Stack &s) {
    if (isempty(s)) {
        cout << "Tumpukan kosong" << endl;
        return '\0';
    } else {
        char popped = s.data[s.top];
        s.top--;
        return popped;
    }
}
```
**Fungsi**: Mengambil dan menghapus elemen dari stack  
**Proses**:
1. Ambil data dari posisi `top`
2. Turunkan `top` (elemen masih ada di array tapi dianggap tidak valid)

```
Contoh pop():

Sebelum:
Index:  0   1   2   3   4
Data:  [A] [B] [C] [X] [ ]
           ↑
        top=3

Proses:
1. popped = data[3] = 'X'
2. top-- → top = 2

Sesudah:
Index:  0   1   2   3   4
Data:  [A] [B] [C] [X] [ ]  (X masih ada tapi dianggap terhapus)
         ↑
        top=2
Return: 'X'
```
#### 6. Peek Function
```cpp
char peek(Stack s) {
    if (isempty(s)) {
        cout << "Tumpukan kosong" << endl;
        return '\0';
    }
    return s.data[s.top];
}
```
**Fungsi**: Melihat elemen teratas tanpa menghapus  
**Proses**:
- Ambil data dari posisi `top` tanpa mengubah `top`

```
Contoh:
Index:  0   1   2   3   4
Data:  [A] [B] [C] [X] [ ]
	       ↑
        top=3
Return: 'X'
```
#### 7. Display Function
```cpp
void display(Stack s) {
    if (isempty(s)) {
        cout << "Tumpukan kosong" << endl;
    } else {
        cout << "Isi tumpukan: " << endl;
        for (int i = s.top; i >= 0; i--) {
            cout << s.data[i] << endl;
        }
        cout << endl;
    }
}
```
**Fungsi**: Menampilkan seluruh isi stack  
**Proses**:
- Loop dari `top` sampai index 0 (menampilkan dari atas ke bawah)

```
Contoh:
Index:  0   1   2   3   4
Data:  [A] [B] [C] [X] [ ]
		   ↑
         top=3

Output:
Isi tumpukan:
X
C
B
A
```

### Perbandingan Stack Array dan Linked List

**KEUNGGULAN STACK ARRAY:**
1. **Memory efisien** - Tidak butuh pointer tambahan
2. **Akses cepat** - Akses langsung via index
3. **Lokalitas cache** - Data tersimpan berurutan di memory

**KELEMAHAN STACK ARRAY:**
1. **Ukuran fixed** - Terbatas oleh MAX
2. **Stack overflow** - Bisa penuh meski memory masih ada
3. **Resizing mahal** - Perlu alokasi baru jika ingin memperbesar

**ILUSTRASI PERBEDAAN:**

```
STACK ARRAY:
Index: 0   1   2   3   4
Data: [A] [B] [C] [ ] [ ]
        ↑
        top=2

STACK LINKED LIST:
first → [C|•] → [B|•] → [A|NULL]
```

Stack array lebih sederhana dan efisien untuk ukuran yang pasti, sedangkan stack linked list lebih flexible untuk ukuran yang dinamis.
