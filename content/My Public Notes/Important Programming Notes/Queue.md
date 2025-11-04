## Queue Linked List

### 📚KONSEP QUEUE LINKED LIST

Queue Linked List adalah struktur data queue yang diimplementasikan menggunakan linked list dengan prinsip FIFO (First-In-First-Out). Elemen pertama yang masuk akan menjadi elemen pertama yang keluar.

```
HEAD → [Data|Next] → [Data|Next] → [Data|Next] → TAIL → NULL
```

Berikut penjelasan detail setiap fungsi dengan diagram:

### **1. Struktur Data**
```cpp
struct ElementQueue {
  char data;
  ElementQueue *next;
};

typedef ElementQueue *pointer;

struct Queue {
  pointer head;
  pointer tail;
};
```
**Struktur**: 
- `ElementQueue`: Node yang menyimpan data dan pointer next
- `Queue`: Menyimpan pointer head (depan) dan tail (belakang)

```
Initial state:
head → NULL
tail → NULL
```

### **2. Fungsi createQueue**
```cpp
void createQueue (Queue &Q) {
  Q.head = NULL;
  Q.tail = NULL;
}
```
**Fungsi**: Inisialisasi queue kosong  
**Proses**: Set head dan tail menjadi NULL

```
Sebelum: head → [A|•] → [B|•] → [C|NULL] ← tail
Sesudah: head → NULL, tail → NULL
```

### **3. Fungsi createElement**
```cpp
void createElement (pointer &pBaru) {
  pBaru = new ElementQueue;
  cout << "Data: ";
  cin >> pBaru -> data;
  pBaru -> next = NULL;
}
```
**Fungsi**: Membuat elemen baru  
**Proses**:
1. Alokasi memory untuk node baru
2. Input data
3. Set pointer next menjadi NULL

```
Contoh createElement('X'):
pBaru → [X|NULL]
```

### **4. Fungsi insertQueue (ENQUEUE)**
```cpp
void insertQueue (Queue &Q, pointer pBaru) {
  if (Q.head == NULL && Q.tail == NULL) {
    Q.head = pBaru;
    Q.tail = pBaru;
  } else {
    Q.tail -> next = pBaru;
    Q.tail = pBaru;
  }
}
```
**Fungsi**: Menambahkan elemen ke belakang queue  
**Proses**:

**Kasus 1: Queue kosong**
```
Sebelum: head → NULL, tail → NULL
pBaru → [X|NULL]

Proses: 
head → [X|NULL] ← tail

Sesudah: head dan tail sama-sama menunjuk ke node X
```

**Kasus 2: Queue tidak kosong**
```
Sebelum:
head → [A|•] → [B|•] → [C|NULL] ← tail
pBaru → [X|NULL]

Proses:
1. tail->next = pBaru: [C|•] → [X|NULL]
2. tail = pBaru: tail → [X|NULL]

Sesudah:
head → [A|•] → [B|•] → [C|•] → [X|NULL] ← tail
```

### **5. Fungsi deleteQueue (DEQUEUE)**
```cpp
void deleteQueue (Queue &Q, pointer &pHapus) {
  if (Q.head == NULL && Q.tail == NULL) {
    pHapus = NULL;
    cout << "Queue kosong, tidak ada data yang bisa dihapus" << endl;
  } else if (Q.head -> next == NULL) {
    pHapus = Q.head;
    Q.head = NULL;
    Q.tail = NULL;
  } else {
    pHapus = Q.head;
    Q.head = Q.head -> next;
    pHapus -> next = NULL;
  }
}
```
**Fungsi**: Menghapus elemen dari depan queue  
**Proses**:

**Kasus 1: Queue kosong**
```
head → NULL, tail → NULL
Output: "Queue kosong"
```

**Kasus 2: Hanya 1 elemen**
```
Sebelum: head → [A|NULL] ← tail

Proses:
1. pHapus = head → [A|NULL]
2. head = NULL, tail = NULL

Sesudah: head → NULL, tail → NULL
Return: node A
```

**Kasus 3: Lebih dari 1 elemen**
```
Sebelum:
head → [A|•] → [B|•] → [C|NULL] ← tail

Proses:
1. pHapus = head → [A|•]
2. head = head->next → [B|•]
3. pHapus->next = NULL

Sesudah:
head → [B|•] → [C|NULL] ← tail
pHapus → [A|NULL] (siap dihapus)
```

### **6. Fungsi displayQueue**
```cpp
void displayQueue (Queue Q) {
  pointer pBantu;
  if (Q.head == NULL) {
    cout << "Queue kosong" << endl;
  } else {
    pBantu = Q.head;
    cout << "Data dalam queue: " << endl;
    cout << endl;
    do {
      cout << pBantu -> data << "\t";
      pBantu = pBantu -> next;
    } while (pBantu != Q.tail -> next);
    cout << endl;
    cout << endl;
  }
}
```
**Fungsi**: Menampilkan seluruh isi queue  
**Proses**: Traverse dari head sampai tail

```
Contoh:
head → [A|•] → [B|•] → [C|NULL] ← tail

Output:
Data dalam queue:
A   B   C
```

## PERBANDINGAN QUEUE ARRAY vs LINKED LIST:

### **Queue Array:**
```cpp
struct Queue {
  char isi[MAX];
  int head;
  int tail;
};
```
**Ilustrasi:**
```
Index: 0   1   2   3   4
Data: [A] [B] [C] [ ] [ ]
       ↑           ↑
      head=0     tail=2
```

### **Queue Linked List:**
```cpp
struct Queue {
  pointer head;
  pointer tail;
};
```
**Ilustrasi:**
```
head → [A|•] → [B|•] → [C|NULL] ← tail
```

## CONTOH PROSES KOMPLIT:

```
1. createQueue()
   head → NULL, tail → NULL

2. insertQueue('A')
   head → [A|NULL] ← tail

3. insertQueue('B')  
   head → [A|•] → [B|NULL] ← tail

4. insertQueue('C')
   head → [A|•] → [B|•] → [C|NULL] ← tail

5. deleteQueue() → return 'A'
   head → [B|•] → [C|NULL] ← tail

6. deleteQueue() → return 'B'  
   head → [C|NULL] ← tail

7. deleteQueue() → return 'C'
   head → NULL, tail → NULL
```


## Queue Array

### 📚KONSEP QUEUE ARRAY

Queue Array adalah struktur data queue yang diimplementasikan menggunakan array dengan prinsip FIFO (First-In-First-Out). Menggunakan dua pointer: `head` (depan) dan `tail` (belakang).

```
Index:   0    1    2   ...  MAX-1
Data:   [ ]  [ ]  [ ]  ...  [ ]
     ↑    ↑
    head tail
```

Berikut penjelasan detail setiap fungsi dengan diagram:

### **1. Struktur Data**
```cpp
struct Queue {
  char isi[MAX];
  int head;
  int tail;
};
```
**Struktur**: 
- `isi[MAX]`: Array untuk menyimpan elemen queue
- `head`: Index elemen depan (yang akan dihapus)
- `tail`: Index elemen belakang (tempat penambahan baru)

```
Initial state:
Index:  0   1   2   3   4
Data:  [ ] [ ] [ ] [ ] [ ]
head = 0, tail = -1
```

### **2. Fungsi createQueue**
```cpp
void createQueue (Queue &Q) {
  Q.head = 0;
  Q.tail = -1;
}
```
**Fungsi**: Inisialisasi queue kosong  
**Proses**: 
- `head` di set ke 0
- `tail` di set ke -1 (menandakan tidak ada elemen)

```
Sebelum: head=2, tail=4
Data: [C] [D] [E] [ ] [ ]

Sesudah: head=0, tail=-1
Data: [C] [D] [E] [ ] [ ] (data masih ada tapi dianggap tidak valid)
```

### **3. Fungsi createElement**
```cpp
void createElement (char &elemen) {
  cout << "Masukkan isi: ";
  cin >> elemen;
}
```
**Fungsi**: Input data untuk elemen baru  
**Proses**: Meminta input dari user

```
Contoh: User input 'X'
elemen = 'X'
```

### **4. Fungsi insertQueue (ENQUEUE)**
```cpp
void insertQueue (Queue &Q, char &elemen) {
  if (Q.tail == MAX - 1) {
    cout << "Queue sudah penuh" << endl;
  } else {
    Q.tail++;
    Q.isi[Q.tail] = elemen;
  }
}
```
**Fungsi**: Menambahkan elemen ke belakang queue  
**Proses**:

**Kasus 1: Queue penuh**
```
MAX = 5, tail = 4
Index:  0   1   2   3   4
Data:  [A] [B] [C] [D] [E]
                 ↑       ↑
                head=2  tail=4
Output: "Queue sudah penuh"
```

**Kasus 2: Queue kosong → insert pertama**
```
Sebelum: head=0, tail=-1
Data:  [ ] [ ] [ ] [ ] [ ]

Proses:
1. tail++ → tail = 0
2. isi[0] = 'A'

Sesudah: head=0, tail=0
Data:  [A] [ ] [ ] [ ] [ ]
```

**Kasus 3: Queue tidak kosok → insert tambahan**
```
Sebelum: head=0, tail=2
Data:  [A] [B] [C] [ ] [ ]

Proses insert('D'):
1. tail++ → tail = 3
2. isi[3] = 'D'

Sesudah: head=0, tail=3
Data:  [A] [B] [C] [D] [ ]
```

### **5. Fungsi deleteQueue (DEQUEUE) - VERSI SHIFTING**
```cpp
void deleteQueue (Queue &Q, char &hapus) {
  if (Q.head > Q.tail) {
    cout << "Queue kosong, tidak ada data yang bisa dihapus" << endl;
  } else {
    hapus = Q.isi[Q.head];
    for (int i = 0; i < Q.tail; i++) {
      Q.isi[i] = Q.isi[i + 1];
    }
    Q.tail--;
  }
}
```
**Fungsi**: Menghapus elemen dari depan queue dengan shifting  
**Proses**:

**Kasus 1: Queue kosong**
```
head=0, tail=-1
head > tail → 0 > -1 → TRUE
Output: "Queue kosong"
```

**Kasus 2: Queue tidak kosong**
```
Sebelum: head=0, tail=3
Data:  [A] [B] [C] [D] [ ]

Proses:
1. hapus = isi[0] = 'A'
2. Shifting: 
   isi[0] = isi[1] → [B] [B] [C] [D] [ ]
   isi[1] = isi[2] → [B] [C] [C] [D] [ ] 
   isi[2] = isi[3] → [B] [C] [D] [D] [ ]
3. tail-- → tail=2

Sesudah: head=0, tail=2
Data:  [B] [C] [D] [D] [ ] (D terakhir dianggap tidak valid)
Return: 'A'
```

### **6. Alternatif DeleteQueue (CIRCULAR QUEUE APPROACH)**
```cpp
// Alternatif yang lebih efisien (circular queue)
void deleteQueueCircular(Queue &Q, char &hapus) {
  if (Q.head > Q.tail) {
    cout << "Queue kosong" << endl;
  } else {
    hapus = Q.isi[Q.head];
    Q.head++;
    // Jika head melewati tail, reset queue
    if (Q.head > Q.tail) {
      Q.head = 0;
      Q.tail = -1;
    }
  }
}
```
**Proses tanpa shifting:**
```
Sebelum: head=0, tail=3
Data:  [A] [B] [C] [D] [ ]

Proses:
1. hapus = isi[0] = 'A'
2. head++ → head=1

Sesudah: head=1, tail=3
Data:  [A] [B] [C] [D] [ ] (A dianggap tidak valid)
         ↑           ↑
        head        tail
```

### **7. Fungsi displayQueue**
```cpp
void displayQueue (Queue Q) {
  int i = 0;
  cout << "Isi Queue: " << endl;
  cout << endl;
  while (i != Q.tail + 1) {
    cout << Q.isi[i] << "\t";
    i++;
  }
  cout << endl;
  cout << endl;
}
```
**Fungsi**: Menampilkan seluruh isi queue  
**Proses**: Loop dari index 0 sampai tail

```
Contoh: head=1, tail=3
Data:  [A] [B] [C] [D] [ ]

Output:
Isi Queue:
B   C   D
```

## ILUSTRASI PROSES KOMPLIT:

```
1. createQueue()
   head=0, tail=-1
   Data: [ ] [ ] [ ] [ ] [ ]

2. insertQueue('A')
   head=0, tail=0
   Data: [A] [ ] [ ] [ ] [ ]

3. insertQueue('B')
   head=0, tail=1  
   Data: [A] [B] [ ] [ ] [ ]

4. insertQueue('C')
   head=0, tail=2
   Data: [A] [B] [C] [ ] [ ]

5. deleteQueue() → return 'A'
   head=0, tail=1  (dengan shifting)
   Data: [B] [C] [C] [ ] [ ]

6. insertQueue('D')
   head=0, tail=2
   Data: [B] [C] [D] [ ] [ ]

7. deleteQueue() → return 'B'
   head=0, tail=1
   Data: [C] [D] [D] [ ] [ ]
```

### KEUNGGULAN DAN KELEMAHAN:

**Queue Linked List:**
- ✅ **Dinamis** - Tidak ada batasan maksimum
- ✅ **Efisien** - Enqueue/dequeue O(1)
- ❌ **Memory overhead** - Butuh space untuk pointer

**Queue Array:**
- ✅ **Memory efisien** - Tidak butuh pointer
- ✅ **Akses cepat** - Akses langsung via index
- ❌ **Ukuran fixed** - Terbatas oleh MAX
- ❌ **Wasteful** - Bisa ada space yang tidak terpakai