## Contoh logika CRUD
- CREATE
```cpp
class laporanPanen {
private:
    Sawit* laporanPanenSawit[100]; 
    int totalSawit;

    void tambahlaporanPanen() {
        if (totalSawit >= 100) {
            cout << ">> Laporan panen sawit penuh!\n";
            return;
        }

        double b, h;
        cout << "Berat (kg): "; cin >> b; cin.ignore();
        cout << "Harga (per kg): "; cin >> h; cin.ignore();

        string tipe;
        cout << "Pilih Sumber Panen (1. Petani Lokal, 2. Perusahaan): ";
        cin >> tipe; cin.ignore();

        if (tipe == 1) {
            string n;
            cout << "Nama Petani: "; getline(cin, n);
            
            laporanPanenSawit[totalSawit] = new Petani(b, h, n);
            totalSawit++;
            cout << ">> Laporan Petani berhasil ditambahkan!\n";
        } 
        ...
    }
    ...
}
```

- READ
```cpp
class laporanPanen {
private:
    Sawit* laporanPanenSawit[100]; 
    int totalSawit;

void tampilkanlaporanPanen() {
        ...
        for (int i = 0; i < totalSawit; i++) {
            cout << i + 1 << ". ";
            laporanPanenSawit[i]->tampilkanInfo(); 
        }
    }
    ...
}
```

- UPDATE
```cpp
class laporanPanen {
private:
    Sawit* laporanPanenSawit[100]; 
    int totalSawit;

    void updatelaporanPanen() {
    ...
        if (no > 0 && no <= totalSawit) {
            double beratBaru, hargaBaru;
            cout << "Berat Baru (kg): "; cin >> beratBaru; cin.ignore();
            cout << "Harga Baru (Rp): "; cin >> hargaBaru; cin.ignore();

            laporanPanenSawit[no - 1]->setBerat(beratBaru);
            laporanPanenSawit[no - 1]->setHarga(hargaBaru);
            cout << ">> Data berat & harga berhasil diperbarui!\n";
        } else {
            ...
        }
    }
    ...
}
```

- DELETE
```cpp
class laporanPanen {
private:
    Sawit* laporanPanenSawit[100]; 
    int totalSawit;

    void hapuslaporanPanen() {
            ...
        if (no > 0 && no <= totalSawit) {
            delete laporanPanenSawit[no - 1]; 

            for (int i = no - 1; i < totalSawit - 1; i++) {
                laporanPanenSawit[i] = laporanPanenSawit[i + 1];
            }
            totalSawit--;
            ...
        }
    }
    ...
}
```

### SEMANGAT ;)