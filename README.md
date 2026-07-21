# Child Safety System - Metodologi

---

## 2.0 METODOLOGI

### 2.1 Reka Bentuk Projek

Projek ini merupakan sebuah sistem keselamatan kanak-kanak dalam kenderaan yang berasaskan Internet of Things (IoT). Sistem ini direka untuk mengesan kehadiran kanak-kanak yang tertinggal di dalam kereta dan memberi amaran awal sebelum suhu kabin mencapai tahap berbahaya. Sistem ini menggunakan ESP32 sebagai mikropengawal utama yang menyambungkan beberapa sensor dan modul komunikasi.

---

### 2.2 Konsep Reka Bentuk

Sistem ini menggunakan ESP32 sebagai mikropengawal utama yang menyambungkan empat (4) komponen utama:

1. **Radar LD2410C** – mengesan kehadiran manusia (pegun dan bergerak)
2. **Load Cell + HX711** – mengukur berat di atas tempat duduk
3. **SHT31** – mengukur suhu dan kelembapan kabin
4. **Sensor Pintu PS-3150** – mengesan status pintu kereta

Apabila radar mengesan kehadiran kanak-kanak, sistem akan menghantar notifikasi Telegram melalui modul 4G A7670C. Jika suhu melebihi 40°C dan pintu tertutup, buzzer akan diaktifkan sebagai amaran bunyi.

---

### Rajah 1: Blok Sistem Keselamatan Kanak-Kanak

![Blok Sistem](images/blok-sistem.png)

> *[Gambar rajah blok sistem akan diletakkan di sini]*

---

### 2.3 Senarai Mikropengawal Utama dan Komponen Utama

**Jadual 1: Senarai Komponen**

| No | Nama Komponen | Fungsi | Harga (RM) |
|----|---------------|--------|------------|
| 1 | ESP32 Dev Module | Mengawal keseluruhan sistem | 18.00 |
| 2 | HLK-LD2410C | Mengesan kehadiran manusia | 3.97 |
| 3 | Buzzer | Memberi amaran bunyi | 0.59 |
| 4 | SHT31 | Mengesan suhu dalam kereta | 8.97 |
| 5 | Load Cell + HX711 | Mengesan berat bayi | 19.44 |
| 6 | A7670C | Penghantaran komunikasi | 28.08 |
| | **Jumlah** | | **79.00** |

---

### 2.4 Pemasangan Litar

**Rajah 2: Pemasangan Litar**

![Pemasangan Litar](images/pemasangan-litar.png)

> *[Gambar pemasangan litar akan diletakkan di sini]*

---

### 2.5 Prosedur Pengumpulan Data

Kajian ini dijalankan di dalam kabin kenderaan sebenar dengan empat keadaan:

**Jadual 2: Keadaan Ujian**

| Keadaan | Penerangan | Tujuan |
|---------|------------|--------|
| **A: Keadaan Normal** | Tiada apa-apa di atas carseat | Sebagai kawalan untuk memastikan sistem tidak aktif apabila tiada objek/manusia. |
| **B: Baby Carseat Kosong + Tangan** | Carseat kosong, tangan di hadapan radar | Menguji pengesanan radar tanpa berat |
| **C: Beg di Atas Carseat** | Beg di atas carseat, tiada tangan | Menguji sistem membezakan objek dengan manusia |
| **D: Baby Carseat + Beg + Tangan** | Beg di atas carseat, tangan di hadapan radar | Menguji sistem dengan berat + radar |

*Setiap keadaan diulang sebanyak 5 kali.*

---

#### 2.5.1 Prosedur Ujian

**Langkah 1: Persediaan**

1. Hidupkan sistem (ESP32)
2. Sambungkan ESP32 ke komputer melalui USB
3. Buka Serial Monitor (115200 baud)

**Langkah 2: Pelaksanaan Ujian**

1. Letakkan komponen mengikut keadaan yang diuji
2. Tunggu bacaan stabil pada Serial Monitor
3. Rekod data: radar, berat, suhu, pintu, buzzer, Telegram
4. Ulang sebanyak 5 kali bagi setiap keadaan

**Langkah 3: Pengumpulan Data**

1. Rekod semua data ke dalam jadual
2. Ambil gambar paparan Serial Monitor
3. Semak notifikasi Telegram yang diterima

---

### 2.6 Carta Alir

**Rajah 3: Carta Alir Sistem**

![Carta Alir](images/carta-alir.png)

> *[Gambar carta alir akan diletakkan di sini]*

---

### 2.7 Lakaran Kedudukan Komponen dalam Kenderaan

**Rajah 4: Kedudukan Komponen dalam Kenderaan**

![Kedudukan Komponen](images/kedudukan-komponen.png)

> *[Gambar lakaran kedudukan komponen akan diletakkan di sini]*

---

## 📝 Nota untuk Gambar

| Gambar | Nama Fail | Lokasi |
|--------|-----------|--------|
| Rajah 1: Blok Sistem | `blok-sistem.png` | `images/` |
| Rajah 2: Pemasangan Litar | `pemasangan-litar.png` | `images/` |
| Rajah 3: Carta Alir | `carta-alir.png` | `images/` |
| Rajah 4: Kedudukan Komponen | `kedudukan-komponen.png` | `images/` |

---

*— Tamat —*
