**Primitive list in singly linked list c++ programming language**

## 🔗 **KONSEP DASAR SINGLE LINKED LIST (Contoh objek kasus analisis objeknya adalah mahasiswa)**

- Notes: Bisa diganti objek mana saja sesuai kebutuhan misal barang, buku, dsb yang memiliki properti objek yang berbeda 

```
[Data | Next] → [Data | Next] → [Data | Next] → NULL
```

Setiap node terdiri dari:
- **Data** (misal: nama, npm)
- **Next** (pointer ke node berikutnya)

## 📝 **1. INSERT FIRST**

### **Kode:**
```cpp
void insertFirst(pointer &first, pointer pBaru) {
    if (first == NULL) {
        first = pBaru;
    } else {
        pBaru->next = first;
        first = pBaru;
    }
}
```

### **Ilustrasi:**
```
SEBELUM:
[Andi|123] → [Budi|456] → NULL
 ↑
first

INSERT [Citra|789] di FIRST:

pBaru->next = first;    // [Citra|789] → [Andi|123] → [Budi|456] → NULL
first = pBaru;          // first = [Citra|789]

HASIL:
[Citra|789] → [Andi|123] → [Budi|456] → NULL
 ↑
first
```

## 📝 **2. INSERT LAST**

### **Kode:**
```cpp
void insertLast(pointer &first, pointer pBaru) {
    if (first == NULL) {
        first = pBaru;
    } else {
        pointer last = first;
        while(last->next != NULL) {
            last = last->next;
        }
        last->next = pBaru;
    }
}
```

### **Ilustrasi:**
```
SEBELUM:
[Andi|123] → [Budi|456] → NULL
        ↑
        last

INSERT [Citra|789] di LAST:

last->next = pBaru;     // [Andi|123] → [Budi|456] → [Citra|789] → NULL

HASIL:
[Andi|123] → [Budi|456] → [Citra|789] → NULL
```

## 📝 **3. INSERT AFTER**

### **Kode:**
```cpp
void insertAfter(pointer &first, pointer pBaru, pointer pCari) {
    if (pCari->next == NULL) {
        insertLast(first, pBaru);
    } else {
        pBaru->next = pCari->next;
        pCari->next = pBaru;
    }
}
```

### **Ilustrasi:**
```
SEBELUM:
[Andi|123] → [Budi|456] → [Dedi|000] → NULL
          ↑
         pCari

INSERT [Citra|789] AFTER [Budi|456]:

pBaru->next = pCari->next;  // [Citra|789] → [Dedi|000]
pCari->next = pBaru;        // [Budi|456] → [Citra|789]

HASIL:
[Andi|123] → [Budi|456] → [Citra|789] → [Dedi|000] → NULL
```

## 🗑️ **4. DELETE FIRST**

### **Kode:**
```cpp
void deleteFirst(pointer &first, pointer &pHapus) {
    if (first == NULL) {
        pHapus = NULL;
    } else if (first->next == NULL) {
        pHapus = first;
        first = NULL;
    } else {
        pHapus = first;
        first = first->next;
        pHapus->next = NULL;
    }
}
```

### **Ilustrasi:**
```
SEBELUM:
[Andi|123] → [Budi|456] → [Citra|789] → NULL
 ↑
first

DELETE FIRST:

pHapus = first;         // pHapus = [Andi|123]
first = first->next;    // first = [Budi|456]

HASIL:
[Budi|456] → [Citra|789] → NULL
 ↑
first

[Andi|123] → NULL (siap di-delete)
 ↑
pHapus
```

## 🗑️ **5. DELETE LAST**

### **Kode:**
```cpp
void deleteLast(pointer &first, pointer &pHapus) {
    if (first == NULL) {
        pHapus = NULL;
    } else if (first->next == NULL) {
        pHapus = first;
        first = NULL;
    } else {
        pointer last = first;
        pointer prelast = NULL;
        while (last->next != NULL) {
            prelast = last;
            last = last->next;
        }
        pHapus = last;
        prelast->next = NULL;
    }
}
```

### **Ilustrasi:**
```
SEBELUM:
[Andi|123] → [Budi|456] → [Citra|789] → NULL
		↑            ↑
		prelast     last

DELETE LAST:

pHapus = last;           // pHapus = [Citra|789]
prelast->next = NULL;    // [Budi|456] → NULL

HASIL:
[Andi|123] → [Budi|456] → NULL

[Citra|789] → NULL (siap di-delete)
 ↑
pHapus
```

## 🗑️ **6. DELETE AFTER**

### **Kode:**
```cpp
void deleteAfter(pointer &first, pointer pCari, pointer &pHapus) {
    if (pCari->next == NULL) {
        pHapus = NULL;
    } else {
        pHapus = pCari->next;
        pCari->next = pHapus->next;
        pHapus->next = NULL;
    }
}
```

### **Ilustrasi:**
```
SEBELUM:
[Andi|123] → [Budi|456] → [Citra|789] → NULL
	 ↑         ↑
	pCari    pHapus

DELETE AFTER [Andi|123]:

pHapus = pCari->next;       // pHapus = [Budi|456]
pCari->next = pHapus->next; // [Andi|123] → [Citra|789]

HASIL:
[Andi|123] → [Citra|789] → NULL

[Budi|456] → NULL (siap di-delete)
 ↑
pHapus
```

## 🔍 **7. SEARCHING**

### **Kode:**
```cpp
void searching(pointer first, char key[15], int &found, pointer &pCari) {
    found = 0;
    pCari = first;
    while (pCari != NULL) {
        if (strcmp(pCari->npm, key) == 0) {
            found = 1;
            break;
        } else {
            pCari = pCari->next;
        }
    }
}
```

### **Ilustrasi (cari NPM "456"):**
```
List: [Andi|123] → [Budi|456] → [Citra|789] → NULL

Iterasi 1:
pCari = [Andi|123] → "123" ≠ "456" → pCari = [Andi|123]->next = [Budi|456]

Iterasi 2:
pCari = [Budi|456] → "456" = "456" → FOUND! break

Hasil: found = 1, pCari = [Budi|456]
```

## 👀 **8. TRAVERSAL**

### **Kode:**
```cpp
void traversal(pointer first) {
    pointer pBantu = first;
    if (first == NULL) {
        cout << "Linked list kosong!" << endl;
    } else {
        int counter = 1;
        do {
            cout << counter << ". Nama: " << pBantu->nama << endl;
            cout << "   NPM : " << pBantu->npm << endl;
            pBantu = pBantu->next;
            counter++;
        } while (pBantu != NULL);
    }
}
```

### **Ilustrasi:**
```
List: [Andi|123] → [Budi|456] → [Citra|789] → NULL

Iterasi 1:
pBantu = [Andi|123] → Tampilkan "Andi, 123" → pBantu = [Andi|123]->next = [Budi|456]

Iterasi 2:
pBantu = [Budi|456] → Tampilkan "Budi, 456" → pBantu = [Budi|456]->next = [Citra|789]

Iterasi 3:
pBantu = [Citra|789] → Tampilkan "Citra, 789" → pBantu = [Citra|789]->next = NULL → STOP

Output:
1. Nama: Andi
   NPM : 123
2. Nama: Budi
   NPM : 456
3. Nama: Citra
   NPM : 789
```

## 🎯 **POLA UMUM OPERASI:**

### **INSERT:**
```cpp
// Pattern: sambung node baru ke target
newNode->next = targetNode->next;  // atau first
targetNode->next = newNode;        // atau first = newNode
```

### **DELETE:**
```cpp
// Pattern: bypass node yang dihapus
prevNode->next = nodeToDelete->next;  // atau first = first->next
nodeToDelete->next = NULL;            // putuskan hubungan
```

### **TRAVERSE:**
```cpp
// Pattern: loop sampai NULL
pointer current = first;
while (current != NULL) {
    // process current node
    current = current->next;
}
```

## 💡 **KESIMPULAN:**

**Single Linked List seperti RANTAI:**
- **Insert** = tambah mata rantai baru
- **Delete** = lepas mata rantai  
- **Traverse** = ikuti rantai dari awal sampai akhir
- **Search** = cari mata rantai tertentu