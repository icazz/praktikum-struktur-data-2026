## Contoh logika CRUD
- CREATE
```cpp
class Perpustakaan {
private:
    Koleksi* rakPerpus[100]; 
    int totalKoleksi;

    void tambahKoleksi() {
        int tipe;
        cout << "Pilih Jenis (1. Buku, 2. Komik): ";
        cin >> tipe; cin.ignore();

        string j; int t;
        cout << "Judul: "; getline(cin, j);
        cout << "Tahun Terbit: "; cin >> t; cin.ignore();

        if (tipe == 1) {
            string p; int hal;
            cout << "Nama Penulis: "; getline(cin, p);
            cout << "Jumlah Halaman: "; cin >> hal;
            
            rakPerpus[totalKoleksi] = new Buku(j, t, p, hal);
            totalKoleksi++;
            cout << ">> Buku berhasil ditambahkan!\n";
        } 
        ...
    }
    ...
}
```

- READ
```cpp
class Perpustakaan {
private:
    Koleksi* rakPerpus[100]; 
    int totalKoleksi;

void tampilkanSemua() {
        ...
        for (int i = 0; i < totalKoleksi; i++) {
            cout << i + 1 << ". ";
            rakPerpus[i]->tampilkanInfo(); 
        }
    }
    ...
}
```

- UPDATE
```cpp
class Perpustakaan {
private:
    Koleksi* rakPerpus[100]; 
    int totalKoleksi;

    void updateKoleksi() {
    ...
            string judulBaru; int tahunBaru;
            cout << "Judul Baru: "; getline(cin, judulBaru);
            cout << "Tahun Terbit Baru: "; cin >> tahunBaru;

            rakPerpus[no - 1]->setJudul(judulBaru);
            rakPerpus[no - 1]->setTahun(tahunBaru);
            ...
    }
    ...
}
```

- DELETE
```cpp
class Perpustakaan {
private:
    Koleksi* rakPerpus[100]; 
    int totalKoleksi;

    void hapusKoleksi() {
            ...
        if (no > 0 && no <= totalKoleksi) {
            delete rakPerpus[no - 1]; 

            for (int i = no - 1; i < totalKoleksi - 1; i++) {
                rakPerpus[i] = rakPerpus[i + 1];
            }
            totalKoleksi--;
            ...
        }
    }
    ...
}
```

### SEMANGAT ;)