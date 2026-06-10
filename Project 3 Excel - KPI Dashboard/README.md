# Dashboard KPI Keuangan Bulanan dengan Excel

## Deskripsi Project

Project ini merupakan dashboard interaktif berbasis Microsoft Excel yang digunakan untuk memonitor KPI keuangan bulanan, khususnya pada aspek revenue, cost/COGS, gross profit, dan profit margin. Dashboard ini dibuat untuk membantu proses monitoring performa keuangan secara lebih ringkas, visual, dan mudah dipahami.

Data transaksi harian diolah menggunakan Pivot Table untuk menghasilkan ringkasan bulanan dan kategori. Hasil agregasi tersebut kemudian divisualisasikan dalam bentuk KPI Card, line chart, bar chart, dropdown filter bulan, serta conditional formatting untuk menandai performa profit margin yang berada di bawah target.

## Tujuan Project

Tujuan utama dari project ini adalah membangun dashboard Excel yang dapat digunakan untuk:

1. Memonitor total revenue, cost, gross profit, dan profit margin setiap bulan.
2. Membandingkan performa keuangan berdasarkan kategori transaksi.
3. Mengetahui tren revenue, cost, dan profit dari waktu ke waktu.
4. Mengidentifikasi bulan dengan profit margin di bawah target.
5. Menyajikan data keuangan dalam bentuk dashboard yang mudah dibaca dan interaktif.

## Tools yang Digunakan

- Microsoft Excel
- Pivot Table
- Pivot Chart
- XLOOKUP / VLOOKUP
- IF / IFS Formula
- Data Validation
- Conditional Formatting
- Dynamic Chart

## Kompetensi yang Dibuktikan

| Kompetensi | Implementasi |
|---|---|
| Pivot Table | Mengagregasi data transaksi harian menjadi ringkasan bulanan dan kategori |
| XLOOKUP / VLOOKUP | Mengambil target margin berdasarkan kategori transaksi |
| IF / IFS | Menentukan status pencapaian KPI berdasarkan profit margin |
| Conditional Formatting | Menandai profit margin yang berada di bawah target |
| Chart Dinamis | Membuat visualisasi tren dan perbandingan kategori |
| Data Validation | Membuat dropdown filter bulan pada dashboard |
| Dashboarding | Menyusun KPI Card, chart, dan insight dalam satu tampilan dashboard |

## Struktur Workbook Excel

| Sheet | Deskripsi |
|---|---|
| Raw Data | Berisi data transaksi harian seperti tanggal, bulan, kategori, revenue, COGS, dan gross profit |
| Pivot Summary | Berisi hasil agregasi data menggunakan Pivot Table |
| Target KPI | Berisi target profit margin berdasarkan kategori |
| Dashboard | Berisi visualisasi KPI keuangan dalam bentuk KPI Card, chart, dan filter bulan |

## Struktur Data

Dataset pada sheet `Raw Data` memiliki beberapa kolom utama sebagai berikut:

| Kolom | Deskripsi |
|---|---|
| Tanggal | Tanggal transaksi |
| Bulan | Periode bulan transaksi |
| Kategori | Kategori produk atau layanan |
| Revenue | Total pendapatan dari transaksi |
| COGS | Cost of Goods Sold atau biaya pokok |
| Gross_Profit | Selisih antara revenue dan COGS |
| Profit_Margin | Persentase keuntungan terhadap revenue |
| Target_Margin | Target margin berdasarkan kategori |
| Status_KPI | Status pencapaian margin terhadap target |

## Formula yang Digunakan

### 1. Menghitung Gross Profit

```excel
=[@Revenue]-[@COGS]
```

Formula ini digunakan untuk menghitung keuntungan kotor dari setiap transaksi.

### 2. Menghitung Profit Margin

```excel
=IFERROR(([@Revenue]-[@COGS]) / [@Revenue], 0)
```

Formula ini digunakan untuk menghitung persentase keuntungan terhadap revenue. Fungsi `IFERROR` digunakan agar hasil tidak error ketika nilai revenue kosong atau bernilai nol.

### 3. Mengambil Target Margin Menggunakan XLOOKUP

```excel
=XLOOKUP([@Kategori], tbl_target[Kategori], tbl_target[Target_Margin], 0)
```

Formula ini digunakan untuk mengambil target profit margin berdasarkan kategori transaksi.

### 4. Alternatif Menggunakan VLOOKUP

```excel
=VLOOKUP([@Kategori], 'Target KPI'!$A$2:$B$4, 2, FALSE)
```

Formula ini dapat digunakan sebagai alternatif apabila versi Excel belum mendukung XLOOKUP.

### 5. Menentukan Status KPI

```excel
=IF([@Profit_Margin]>=[@Target_Margin], "Achieved", "Below Target")
```

Formula ini digunakan untuk menentukan apakah profit margin sudah mencapai target atau masih berada di bawah target.

### 6. Menampilkan KPI Card Berdasarkan Filter Bulan

Contoh formula untuk menampilkan Total Revenue berdasarkan bulan yang dipilih pada dropdown:

```excel
=XLOOKUP($L$4, 'Pivot Summary'!$A$9:$A$44, 'Pivot Summary'!$B$9:$B$44, 0)
```

Formula ini digunakan agar nilai KPI Card berubah secara otomatis sesuai bulan yang dipilih pada dropdown filter.

## Fitur Dashboard

### 1. KPI Card

KPI Card digunakan untuk menampilkan ringkasan angka utama dalam dashboard, yaitu:

| KPI | Deskripsi |
|---|---|
| Total Revenue | Total pendapatan pada bulan yang dipilih |
| Total COGS | Total biaya pada bulan yang dipilih |
| Gross Profit | Total keuntungan kotor pada bulan yang dipilih |
| Profit Margin | Persentase keuntungan terhadap revenue |

### 2. Line Chart Tren Bulanan

Line chart digunakan untuk menampilkan tren bulanan dari total revenue, total cost/COGS, dan gross profit. Visualisasi ini membantu melihat pola kenaikan atau penurunan performa keuangan dari waktu ke waktu.

### 3. Bar Chart Perbandingan Kategori

Bar chart digunakan untuk membandingkan performa revenue, cost, dan gross profit berdasarkan kategori. Chart ini membantu mengidentifikasi kategori yang memberikan kontribusi terbesar terhadap pendapatan dan profit.

### 4. Dropdown Filter Bulan

Dropdown filter dibuat menggunakan fitur Data Validation. Filter ini memungkinkan pengguna memilih bulan tertentu, sehingga KPI Card dapat menampilkan angka sesuai periode yang dipilih.

### 5. Conditional Formatting

Conditional formatting digunakan untuk memberikan penanda visual pada profit margin yang berada di bawah target. Dengan fitur ini, bulan atau kategori dengan performa kurang baik dapat lebih cepat teridentifikasi.

## Preview Dashboard

![Dashboard Preview](https://github.com/Rhalasya/Data-Analyst-Portofolio/blob/main/Project%203%20Excel%20-%20KPI%20Dashboard/preview%20dashboard.png)

## Business Insight

Berdasarkan dashboard yang dibuat, performa keuangan dapat dianalisis secara lebih cepat melalui ringkasan KPI dan visualisasi. Revenue, cost, dan gross profit dapat dipantau setiap bulan untuk melihat tren pertumbuhan maupun penurunan performa.

Dashboard juga membantu membandingkan kontribusi setiap kategori terhadap revenue dan gross profit. Dengan adanya profit margin dan target margin, pengguna dapat mengetahui apakah performa keuangan sudah sesuai target atau masih perlu dilakukan evaluasi.

Jika profit margin berada di bawah target, maka perusahaan perlu meninjau kembali struktur biaya, efisiensi operasional, harga jual, atau kontribusi masing-masing kategori terhadap profit. Dengan demikian, dashboard ini dapat menjadi alat bantu sederhana untuk mendukung proses monitoring dan pengambilan keputusan berbasis data.

## Kesimpulan

Project ini menunjukkan kemampuan dalam mengolah data transaksi menggunakan Microsoft Excel, membuat agregasi data menggunakan Pivot Table, menerapkan formula analitis, serta membangun dashboard interaktif untuk monitoring KPI keuangan bulanan.

Dashboard ini dapat digunakan sebagai portofolio Data Analyst karena mencakup proses data preparation, data aggregation, KPI calculation, data visualization, dan business insight dalam satu workbook Excel.

## File dalam Repository

| File/Folder | Deskripsi |
|---|---|
| `README.md` | Dokumentasi project |
| `project3_excel_kpi_dashboard.xlsx` | File dashboard Excel |
| `dashboard-preview.png` | Screenshot tampilan dashboard |
