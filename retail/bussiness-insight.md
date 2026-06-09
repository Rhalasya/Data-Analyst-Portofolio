# Business Insight Summary  
# Retail Sales Analysis Using MySQL

## 1. Project Overview

Project ini menganalisis data transaksi penjualan toko retail menggunakan MySQL. Analisis dilakukan berdasarkan output query yang mencakup revenue bulanan, performa kategori produk, produk terlaris, performa penjualan per provinsi, dan customer dengan total belanja tertinggi.

Tujuan utama analisis ini adalah untuk mengetahui:
- tren pendapatan dari bulan ke bulan,
- kategori produk dengan kontribusi revenue terbesar,
- produk yang paling berpengaruh terhadap penjualan,
- provinsi dengan performa penjualan tertinggi,
- pelanggan dengan kontribusi belanja terbesar.


## 2. Overall Sales Performance

### Query Result Summary

| Metric | Value |
|:---|:---|
| Total Revenue | Rp3.445.534.000 |
| Total Cost | Rp1.889.937.223 |
| Gross Profit | Rp1.555.596.777 |
| Gross Margin | 45,15% |
| Total Order | 901 |
| Average Order Value | Rp3.824.122 |
| Average Monthly Revenue | Rp137.821.360 |

### Insight

Secara keseluruhan, toko menghasilkan total revenue sebesar **Rp3,45 miliar** dengan gross profit sebesar **Rp1,56 miliar**. Gross margin sebesar **45,15%** menunjukkan bahwa bisnis memiliki tingkat keuntungan kotor yang cukup baik dari setiap penjualan.

Average order value sebesar **Rp3,82 juta** menunjukkan bahwa setiap transaksi memiliki nilai belanja yang relatif tinggi. Hal ini dapat terjadi karena terdapat produk dengan harga tinggi, khususnya dari kategori Elektronik.

### Recommendation

Perusahaan perlu mempertahankan margin keuntungan dengan mengelola harga jual, biaya produk, dan strategi diskon. Karena average order value cukup tinggi, strategi upselling dan bundling produk dapat digunakan untuk meningkatkan nilai transaksi lebih lanjut.


## 3. Monthly Revenue Trend

### Top 5 Months by Revenue

| Month | Total Orders | Unique Customers | Total Revenue | Gross Profit | Margin |
|:---|---:|---:|:---|:---|:---|
| 2023-08 | 53 | 50 | Rp258.110.900 | Rp118.873.258 | 46,06% |
| 2022-11 | 42 | 40 | Rp238.265.400 | Rp104.281.864 | 43,77% |
| 2022-01 | 38 | 32 | Rp207.207.950 | Rp96.410.946 | 46,53% |
| 2023-04 | 51 | 44 | Rp193.849.900 | Rp90.058.787 | 46,46% |
| 2023-01 | 43 | 38 | Rp189.509.100 | Rp83.516.155 | 44,07% |

### Highest Month-over-Month Growth

| Month | Revenue | Growth |
|:---|:---|:---|
| 2022-07 | Rp118.760.500 | 138,55% |
| 2022-11 | Rp238.265.400 | 119,74% |
| 2023-11 | Rp184.260.250 | 95,85% |
| 2023-01 | Rp189.509.100 | 94,54% |
| 2023-06 | Rp154.203.800 | 92,82% |

### Lowest Month-over-Month Growth

| Month | Revenue | Growth |
|:---|:---|:---|
| 2022-12 | Rp97.412.200 | -59,12% |
| 2023-05 | Rp79.974.450 | -58,74% |
| 2022-05 | Rp64.031.950 | -55,76% |
| 2022-02 | Rp101.832.250 | -50,86% |
| 2023-09 | Rp142.821.300 | -44,67% |

### Insight

Revenue tertinggi terjadi pada **Agustus 2023** dengan total revenue sebesar **Rp258,11 juta** dan gross profit sebesar **Rp118,87 juta**. Bulan ini juga memiliki jumlah unique customers tertinggi yaitu **50 pelanggan**, sehingga peningkatan revenue tidak hanya disebabkan oleh nilai transaksi besar, tetapi juga oleh jumlah pelanggan yang lebih banyak.

Namun, revenue bulanan terlihat cukup fluktuatif. Beberapa bulan mengalami pertumbuhan sangat tinggi, seperti **Juli 2022 naik 138,55%** dan **November 2022 naik 119,74%**, tetapi ada juga penurunan besar seperti **Desember 2022 turun 59,12%** dan **Mei 2023 turun 58,74%**.

### Recommendation

Perusahaan perlu mengevaluasi faktor yang menyebabkan lonjakan dan penurunan revenue, seperti promosi, ketersediaan stok, musim belanja, atau perubahan permintaan pelanggan. Bulan dengan pertumbuhan tinggi dapat dijadikan acuan untuk strategi promosi berikutnya, sedangkan bulan dengan penurunan tinggi perlu dianalisis lebih lanjut agar penurunan tidak berulang.


## 4. Revenue by Category

### Query Result

| Category | Order Items | Total Qty | Revenue | Gross Profit | Margin | Revenue Share |
|:---|---:|---:|:---|:---|:---|:---|
| Elektronik | 245 | 818 | Rp2.412.034.000 | Rp1.123.231.625 | 46,57% | 70,00% |
| Olahraga | 254 | 891 | Rp317.405.500 | Rp134.702.173 | 42,44% | 9,21% |
| Fashion | 276 | 962 | Rp267.888.000 | Rp113.202.301 | 42,26% | 7,77% |
| Otomotif | 251 | 835 | Rp179.268.500 | Rp79.631.955 | 44,42% | 5,20% |
| Perabot Rumah | 239 | 821 | Rp104.850.750 | Rp37.342.382 | 35,61% | 3,04% |
| Kesehatan | 250 | 861 | Rp67.634.750 | Rp24.989.520 | 36,95% | 1,96% |
| Buku & Alat Tulis | 258 | 805 | Rp55.030.650 | Rp24.325.923 | 44,20% | 1,60% |
| Makanan & Minuman | 240 | 793 | Rp41.421.850 | Rp18.170.898 | 43,87% | 1,20% |

### Insight

Kategori **Elektronik** menjadi kontributor revenue terbesar dengan total revenue sebesar **Rp2,41 miliar** atau sekitar **70% dari total revenue**. Kategori ini juga menghasilkan gross profit terbesar yaitu **Rp1,12 miliar** dengan margin **46,57%**.

Namun, tingginya kontribusi Elektronik juga menunjukkan adanya ketergantungan bisnis pada satu kategori utama. Jika penjualan kategori Elektronik menurun, total revenue perusahaan berpotensi ikut turun secara signifikan.

Kategori **Perabot Rumah** memiliki margin terendah yaitu **35,61%**, sehingga kategori ini perlu dievaluasi dari sisi harga jual, biaya produk, atau strategi diskon.

### Recommendation

Perusahaan perlu mempertahankan performa kategori Elektronik karena kategori ini menjadi sumber utama pendapatan. Namun, perusahaan juga sebaiknya mulai meningkatkan kontribusi kategori lain seperti Olahraga dan Fashion agar revenue lebih seimbang dan tidak terlalu bergantung pada satu kategori.


## 5. Top Products Performance

### Top 10 Products by Revenue

| Rank | Product | Category | Qty Sold | Revenue | Revenue Share |
|---:|:---|:---|---:|:---|:---|
| 1 | Laptop ASUS VivoBook | Elektronik | 190 | Rp1.331.625.000 | 38,65% |
| 2 | Smart TV 43" | Elektronik | 170 | Rp714.825.000 | 20,75% |
| 3 | Smartphone Samsung A54 | Elektronik | 116 | Rp267.500.000 | 7,76% |
| 4 | Sepatu Lari Nike | Olahraga | 186 | Rp150.067.500 | 4,36% |
| 5 | Sepatu Sneakers | Fashion | 193 | Rp80.842.500 | 2,35% |
| 6 | Helm Full Face | Otomotif | 113 | Rp78.975.000 | 2,29% |
| 7 | Rak Buku 5 Susun | Perabot Rumah | 168 | Rp70.245.000 | 2,04% |
| 8 | Raket Badminton | Olahraga | 165 | Rp65.394.000 | 1,90% |
| 9 | Tas Ransel | Fashion | 186 | Rp64.942.000 | 1,88% |
| 10 | Jaket Hoodie | Fashion | 213 | Rp63.632.000 | 1,85% |

### Insight

Produk dengan revenue tertinggi adalah **Laptop ASUS VivoBook** dengan total revenue sebesar **Rp1,33 miliar**, berkontribusi sekitar **38,65% dari total revenue**. Tiga produk teratas seluruhnya berasal dari kategori Elektronik dan berkontribusi sekitar **67,16% dari total revenue**.

Hal ini menunjukkan bahwa produk Elektronik menjadi penggerak utama pendapatan toko. Namun, konsentrasi revenue yang terlalu besar pada sedikit produk juga menjadi risiko bisnis apabila stok habis, harga berubah, atau permintaan produk tersebut menurun.

Menariknya, **Jaket Hoodie** memiliki quantity sold tertinggi di antara top 10, yaitu **213 unit**, tetapi revenue-nya lebih kecil dibanding produk Elektronik karena harga satuannya lebih rendah.

### Recommendation

Perusahaan perlu menjaga ketersediaan stok produk utama seperti Laptop ASUS VivoBook, Smart TV 43", dan Smartphone Samsung A54. Selain itu, produk dengan quantity tinggi seperti Jaket Hoodie, Sepatu Sneakers, dan Sepatu Lari Nike dapat digunakan untuk strategi volume-based promotion atau bundling dengan produk lain.


## 6. Sales Performance by Province

### Top 10 Provinces by Revenue

| Province | Orders | Customers | Revenue | AOV | Revenue Share |
|:---|---:|---:|:---|:---|:---|
| Riau | 88 | 16 | Rp406.352.100 | Rp1.714.566 | 11,79% |
| Bali | 82 | 20 | Rp350.824.100 | Rp1.639.365 | 10,18% |
| Kalimantan Timur | 82 | 16 | Rp319.150.500 | Rp1.512.562 | 9,26% |
| Jawa Timur | 59 | 12 | Rp307.517.900 | Rp2.120.813 | 8,93% |
| Sumatera Selatan | 83 | 18 | Rp305.013.500 | Rp1.525.068 | 8,85% |
| Jawa Barat | 64 | 15 | Rp238.208.850 | Rp1.609.519 | 6,91% |
| Yogyakarta | 59 | 13 | Rp219.978.900 | Rp1.383.515 | 6,38% |
| Sumatera Utara | 59 | 12 | Rp219.796.500 | Rp1.537.038 | 6,38% |
| Sulawesi Selatan | 55 | 15 | Rp210.820.000 | Rp1.453.931 | 6,12% |
| Lampung | 57 | 13 | Rp203.859.200 | Rp1.544.388 | 5,92% |

### Insight

Provinsi dengan revenue tertinggi adalah **Riau** dengan total revenue sebesar **Rp406,35 juta**, diikuti oleh **Bali** sebesar **Rp350,82 juta** dan **Kalimantan Timur** sebesar **Rp319,15 juta**. Lima provinsi teratas berkontribusi sekitar **49,02% dari total revenue**, sehingga hampir setengah pendapatan berasal dari wilayah tersebut.

**Jawa Timur** menarik untuk diperhatikan karena meskipun jumlah order-nya hanya **59**, average order value-nya paling tinggi yaitu **Rp2,12 juta**. Ini menunjukkan bahwa pelanggan dari Jawa Timur cenderung melakukan transaksi dengan nilai belanja lebih besar.

### Recommendation

Perusahaan dapat memprioritaskan strategi pemasaran di provinsi dengan revenue tinggi seperti Riau, Bali, Kalimantan Timur, Jawa Timur, dan Sumatera Selatan. Untuk wilayah dengan AOV tinggi seperti Jawa Timur, strategi premium product promotion dapat digunakan. Sementara itu, wilayah dengan revenue lebih rendah dapat dievaluasi melalui promosi lokal, peningkatan channel penjualan, atau campaign berbasis wilayah.


## 7. Top Customer Spending

### Top 10 Customers by Total Spending

| Customer ID | Name | Province | Orders | Total Spending | AOV | Revenue Share |
|:---|:---|:---|---:|:---|:---|:---|
| CUST0032 | Bagas Prakoso | Sumatera Selatan | 10 | Rp70.735.550 | Rp7.073.555 | 2,05% |
| CUST0181 | Hendra Gunawan | Kalimantan Timur | 5 | Rp60.047.800 | Rp12.009.560 | 1,74% |
| CUST0158 | Xavier Tan | Riau | 7 | Rp56.418.750 | Rp8.059.821 | 1,64% |
| CUST0168 | Panji Nugroho | Jawa Timur | 9 | Rp56.386.000 | Rp6.265.111 | 1,64% |
| CUST0076 | Erika Susanti | Jawa Tengah | 5 | Rp55.991.000 | Rp11.198.200 | 1,63% |
| CUST0116 | Nanda Putra | Kalimantan Timur | 7 | Rp54.751.500 | Rp7.821.643 | 1,59% |
| CUST0153 | Rizky Firmansyah | Lampung | 6 | Rp54.455.000 | Rp9.075.833 | 1,58% |
| CUST0122 | Hani Safitri | Riau | 9 | Rp54.187.500 | Rp6.020.833 | 1,57% |
| CUST0039 | Maya Anggraeni | Banten | 7 | Rp50.292.500 | Rp7.184.643 | 1,46% |
| CUST0068 | Wawan Hermawan | Sumatera Selatan | 7 | Rp49.002.250 | Rp7.000.321 | 1,42% |

### Insight

Customer dengan total belanja tertinggi adalah **Bagas Prakoso** dengan total spending sebesar **Rp70,74 juta** dari **10 order**. Sementara itu, **Hendra Gunawan** memiliki average order value tertinggi di antara 10 pelanggan teratas, yaitu **Rp12,01 juta** per order.

Top 10 customer menyumbang sekitar **16,32% dari total revenue**, sedangkan top 20 customer menyumbang sekitar **29,54% dari total revenue**. Hal ini menunjukkan bahwa sebagian pelanggan memiliki kontribusi cukup besar terhadap pendapatan toko.

### Recommendation

Perusahaan dapat membuat program loyalitas untuk high-value customer, seperti voucher khusus, membership, early access produk baru, atau layanan prioritas. Customer dengan AOV tinggi juga dapat menjadi target promosi untuk produk premium, khususnya produk dari kategori Elektronik.


## 8. Overall Business Insights

Berdasarkan hasil analisis, terdapat beberapa temuan utama:

1. **Revenue terbesar berasal dari kategori Elektronik.**  
   Elektronik menyumbang sekitar 70% dari total revenue dan menjadi kategori paling dominan.

2. **Produk utama sangat memengaruhi total pendapatan.**  
   Tiga produk teratas, yaitu Laptop ASUS VivoBook, Smart TV 43", dan Smartphone Samsung A54, berkontribusi sekitar 67,16% dari total revenue.

3. **Revenue bulanan cukup fluktuatif.**  
   Beberapa bulan mengalami pertumbuhan tinggi, tetapi beberapa bulan lain mengalami penurunan tajam. Hal ini menunjukkan perlunya monitoring performa bulanan secara rutin.

4. **Riau menjadi provinsi dengan revenue tertinggi.**  
   Riau menghasilkan revenue sebesar Rp406,35 juta, sedangkan Jawa Timur memiliki average order value tertinggi.

5. **High-value customers perlu dipertahankan.**  
   Top 10 customers berkontribusi 16,32% terhadap total revenue, sehingga strategi retensi pelanggan penting untuk menjaga pendapatan.


## 9. Business Recommendations

Berdasarkan hasil analisis, rekomendasi bisnis yang dapat diberikan adalah:

1. **Prioritaskan stok produk Elektronik.**  
   Produk seperti Laptop ASUS VivoBook, Smart TV 43", dan Smartphone Samsung A54 harus dijaga ketersediaannya karena memiliki kontribusi revenue terbesar.

2. **Kurangi ketergantungan pada satu kategori.**  
   Karena Elektronik menyumbang 70% revenue, perusahaan perlu meningkatkan penjualan kategori lain seperti Olahraga dan Fashion agar risiko bisnis lebih seimbang.

3. **Gunakan strategi bundling.**  
   Produk dengan quantity tinggi tetapi revenue lebih rendah dapat dibundling dengan produk premium untuk meningkatkan average order value.

4. **Fokuskan campaign pada wilayah potensial.**  
   Riau, Bali, Kalimantan Timur, Jawa Timur, dan Sumatera Selatan dapat menjadi prioritas campaign karena berkontribusi besar terhadap revenue.

5. **Buat loyalty program untuk high-value customers.**  
   Customer dengan total spending tinggi perlu dipertahankan melalui promo khusus, membership, atau personalized offer.

6. **Pantau monthly revenue secara berkala.**  
   Karena revenue bulanan fluktuatif, perusahaan perlu membuat dashboard monitoring bulanan agar penurunan performa bisa terdeteksi lebih cepat.

## 10. Conclusion

Project ini menunjukkan bahwa data transaksi retail dapat diolah menggunakan MySQL untuk menghasilkan insight bisnis yang berguna. Melalui analisis revenue bulanan, kategori produk, produk terlaris, performa provinsi, dan customer spending, perusahaan dapat memahami area bisnis yang paling menguntungkan serta menentukan strategi penjualan yang lebih tepat.

Project ini membuktikan kompetensi dalam:
- SQL aggregation,
- multi-table JOIN,
- window function,
- revenue analysis,
- customer analysis,
- product performance analysis,
- business insight generation.
