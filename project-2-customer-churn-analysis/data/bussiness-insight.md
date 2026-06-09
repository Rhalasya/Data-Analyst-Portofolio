# Business Insight Summary  
# Customer Churn Analysis Using MySQL

## 1. Project Objective

Project ini bertujuan untuk menganalisis churn pelanggan berdasarkan data subscription dan aktivitas transaksi pelanggan. Analisis dilakukan untuk mengetahui jumlah pelanggan yang berhenti berlangganan, churn rate, churn berdasarkan plan, churn berdasarkan provinsi, pola churn bulanan, segmentasi pelanggan churned berdasarkan nilai transaksi, serta pelanggan aktif yang mulai berisiko churn.

Analisis ini menggunakan tanggal referensi:

```sql
'2024-01-31'
```

Customer dikategorikan sebagai **churned** apabila status subscription-nya adalah `Churned`. Selain itu, pelanggan aktif juga dianalisis berdasarkan jumlah hari sejak transaksi terakhir untuk mendeteksi potensi churn lebih awal.

---

## 2. Overall Churn Summary

### Query Result

| total_pelanggan | total_churned | total_aktif | churn_rate_pct |
|---:|---:|---:|---:|
| 200 | 64 | 136 | 32.00% |

### Insight

Dari total **200 pelanggan**, terdapat **64 pelanggan churned** dan **136 pelanggan aktif**. Churn rate keseluruhan sebesar **32.00%**, yang berarti sekitar sepertiga pelanggan dalam dataset sudah berhenti berlangganan.

Angka churn ini cukup signifikan karena menunjukkan bahwa perusahaan kehilangan sebagian besar pelanggan dari total basis pelanggan yang dimiliki. Jika churn tidak dimonitor secara berkala, perusahaan berpotensi kehilangan recurring revenue dari pelanggan yang sebelumnya sudah pernah melakukan transaksi.

### Recommendation

Perusahaan perlu membuat strategi retensi pelanggan dengan memantau pelanggan aktif yang mulai tidak melakukan transaksi. Selain itu, pelanggan churned dengan total spending tinggi perlu menjadi prioritas dalam program win-back campaign karena mereka memiliki potensi kontribusi revenue yang besar jika berhasil diaktifkan kembali.

---

## 3. Churn Rate by Subscription Plan

### Query Result

| plan | total | aktif | churned | churn_rate_pct | monthly_revenue_lost | avg_monthly_fee |
|---|---:|---:|---:|---:|---:|---:|
| Standard | 77 | 51 | 26 | 33.77% | Rp5.524.000 | Rp224.974 |
| Basic | 64 | 43 | 21 | 32.81% | Rp3.779.000 | Rp216.188 |
| Premium | 59 | 42 | 17 | 28.81% | Rp3.183.000 | Rp213.407 |

### Insight

Plan **Standard** memiliki churn rate tertinggi yaitu **33.77%**, dengan total **26 pelanggan churned**. Plan ini juga memiliki potensi kehilangan revenue bulanan terbesar, yaitu **Rp5.524.000**.

Plan **Basic** memiliki churn rate sebesar **32.81%**, tidak jauh berbeda dari Standard. Sementara itu, plan **Premium** memiliki churn rate paling rendah yaitu **28.81%**.

Hal ini menunjukkan bahwa pelanggan pada plan Standard dan Basic memiliki risiko churn yang lebih tinggi dibanding pelanggan Premium. Kemungkinan penyebabnya dapat berkaitan dengan persepsi manfaat layanan, harga, atau kurangnya engagement pelanggan terhadap fitur yang tersedia.

### Recommendation

Perusahaan perlu mengevaluasi value proposition pada plan **Standard** dan **Basic**. Jika churn tinggi terjadi karena pelanggan merasa manfaat yang diterima belum sebanding dengan biaya langganan, perusahaan dapat menawarkan benefit tambahan, loyalty reward, atau promo retensi khusus untuk pelanggan pada dua plan tersebut.

---

## 4. Churn Rate by Province

### Query Result

| province | total | churned | aktif | churn_rate_pct |
|---|---:|---:|---:|---:|
| DKI Jakarta | 10 | 6 | 4 | 60.00% |
| Yogyakarta | 13 | 7 | 6 | 53.85% |
| Sumatera Selatan | 19 | 9 | 10 | 47.37% |
| Jawa Timur | 13 | 6 | 7 | 46.15% |
| Jawa Barat | 15 | 6 | 9 | 40.00% |
| Riau | 16 | 6 | 10 | 37.50% |
| Jawa Tengah | 9 | 3 | 6 | 33.33% |
| Sumatera Utara | 12 | 4 | 8 | 33.33% |
| Bali | 21 | 6 | 15 | 28.57% |
| Sulawesi Selatan | 15 | 3 | 12 | 20.00% |

### Insight

Provinsi dengan churn rate tertinggi adalah **DKI Jakarta** dengan churn rate sebesar **60.00%**, diikuti oleh **Yogyakarta** sebesar **53.85%** dan **Sumatera Selatan** sebesar **47.37%**.

Meskipun jumlah pelanggan di DKI Jakarta tidak sebanyak beberapa provinsi lain, tingkat churn yang tinggi menunjukkan adanya risiko retensi di wilayah tersebut. Provinsi seperti Yogyakarta dan Sumatera Selatan juga perlu diperhatikan karena lebih dari 45% pelanggan di wilayah tersebut sudah churned.

### Recommendation

Perusahaan dapat melakukan campaign retensi berbasis wilayah, terutama untuk provinsi dengan churn rate tinggi. Strategi yang dapat dilakukan antara lain promo lokal, komunikasi ulang kepada pelanggan lama, survei kepuasan pelanggan, atau penawaran khusus berdasarkan karakteristik pelanggan di wilayah tersebut.

---

## 5. Monthly Churn Trend

### Query Result: Highest Monthly Churn

| bulan_churn | jumlah_churn | revenue_lost | cumulative_churn |
|---|---:|---:|---:|
| 2022-12 | 5 | Rp1.045.000 | 41 |
| 2022-09 | 4 | Rp696.000 | 32 |
| 2022-03 | 4 | Rp596.000 | 17 |
| 2023-04 | 3 | Rp797.000 | 50 |
| 2023-06 | 3 | Rp797.000 | 53 |
| 2022-05 | 3 | Rp747.000 | 21 |
| 2022-07 | 3 | Rp647.000 | 26 |
| 2023-08 | 3 | Rp647.000 | 57 |
| 2023-03 | 3 | Rp547.000 | 47 |
| 2022-01 | 3 | Rp397.000 | 12 |

### Insight

Bulan dengan jumlah churn tertinggi adalah **Desember 2022**, dengan **5 pelanggan churned** dan potensi kehilangan revenue bulanan sebesar **Rp1.045.000**. Beberapa bulan lain seperti **September 2022** dan **Maret 2022** juga menunjukkan jumlah churn yang relatif tinggi.

Pola churn bulanan ini penting karena dapat menunjukkan periode tertentu ketika pelanggan lebih banyak berhenti berlangganan. Jika churn meningkat pada periode tertentu, perusahaan perlu mengevaluasi apakah ada faktor eksternal atau internal yang memengaruhi keputusan pelanggan untuk berhenti.

### Recommendation

Perusahaan perlu membuat monitoring churn bulanan agar peningkatan churn dapat terdeteksi lebih cepat. Bulan dengan churn tinggi perlu dianalisis lebih lanjut, misalnya dari sisi perubahan harga, penurunan engagement, kualitas layanan, atau berakhirnya masa promosi.

---

## 6. Churned Customer Segmentation by Value

### Query Result

| value_segment | jumlah | avg_spent | avg_tenure_hari | avg_monthly_fee |
|---|---:|---:|---:|---:|
| High Value | 38 | Rp3.611.354 | 228 | Rp189.789 |
| Mid Value | 20 | Rp1.442.463 | 200 | Rp201.500 |
| Low Value | 6 | Rp447.305 | 216 | Rp207.333 |

### Insight

Sebagian besar pelanggan churned berada pada segmen **High Value**, yaitu sebanyak **38 pelanggan**. Segmen ini memiliki rata-rata total spending sebesar **Rp3.611.354**, jauh lebih tinggi dibanding segmen Mid Value dan Low Value.

Temuan ini penting karena churn tidak hanya terjadi pada pelanggan bernilai rendah, tetapi juga pada pelanggan dengan kontribusi transaksi yang besar. Artinya, perusahaan kehilangan pelanggan yang sebenarnya memiliki nilai ekonomi tinggi.

### Recommendation

High-value churned customers perlu menjadi prioritas utama untuk win-back campaign. Perusahaan dapat memberikan penawaran personal, diskon khusus, voucher reaktivasi, layanan prioritas, atau benefit tambahan agar pelanggan bernilai tinggi tertarik untuk kembali aktif.

---

## 7. At-Risk Active Customers

### Query Result: Top 10 At-Risk Customers

| customer_id | name | city | province | plan | monthly_fee | last_transaction_date | days_since_last_tx | risk_level |
|---|---|---|---|---|---:|---|---:|---|
| CUST0035 | Qori Wahyuni | Bandar Lampung | Lampung | Premium | Rp349.000 | 2023-10-01 | 122 | High Risk |
| CUST0089 | Xena Fitria | Metro | Lampung | Standard | Rp349.000 | 2023-10-03 | 120 | High Risk |
| CUST0075 | Andi Pratama | Magelang | Jawa Tengah | Basic | Rp349.000 | 2023-10-04 | 119 | High Risk |
| CUST0151 | Sinta Dewi | Balikpapan | Kalimantan Timur | Standard | Rp199.000 | 2023-10-04 | 119 | High Risk |
| CUST0014 | Qori Wahyuni | Metro | Lampung | Standard | Rp349.000 | 2023-10-05 | 118 | High Risk |
| CUST0168 | Panji Nugroho | Sidoarjo | Jawa Timur | Premium | Rp199.000 | 2023-10-05 | 118 | High Risk |
| CUST0020 | Gilang Permana | Samarinda | Kalimantan Timur | Basic | Rp349.000 | 2023-10-06 | 117 | High Risk |
| CUST0064 | Lukman Hakim | Palembang | Sumatera Selatan | Premium | Rp199.000 | 2023-10-06 | 117 | High Risk |
| CUST0097 | Hendra Gunawan | Lubuklinggau | Sumatera Selatan | Basic | Rp349.000 | 2023-10-09 | 114 | High Risk |
| CUST0162 | Hendra Gunawan | Dumai | Riau | Premium | Rp349.000 | 2023-10-09 | 114 | High Risk |

### Risk Level Summary

| risk_level | total_customers |
|---|---:|
| High Risk | 38 |
| Medium Risk | 36 |
| Low Risk | 31 |

### Insight

Terdapat **105 pelanggan aktif** yang sudah tidak melakukan transaksi minimal 30 hari. Dari jumlah tersebut, **38 pelanggan** masuk kategori **High Risk** karena tidak melakukan transaksi selama 90 hari atau lebih.

Ini menunjukkan bahwa sebagian pelanggan aktif sebenarnya sudah menunjukkan tanda-tanda akan churn. Jika pelanggan high risk tidak segera ditangani, mereka berpotensi berubah menjadi pelanggan churned.

### Recommendation

Perusahaan perlu membuat early warning system untuk pelanggan aktif yang mulai tidak bertransaksi. Pelanggan dengan status High Risk perlu menjadi prioritas campaign retensi, sedangkan pelanggan Medium Risk dapat diberikan reminder, voucher ringan, atau personalized offer sebelum mereka menjadi churned.

---

## 8. High-Value Churned Customers

### Query Result: Top 10 High-Value Churned Customers

| name | province | plan | total_spent | monthly_fee | tenure_hari |
|---|---|---|---:|---:|---:|
| Zainal Abidin | Yogyakarta | Premium | Rp4.989.965 | Rp99.000 | 183 |
| Doni Kurniawan | Bali | Basic | Rp4.785.088 | Rp199.000 | 75 |
| Victor Chandra | Jawa Barat | Basic | Rp4.749.719 | Rp99.000 | 72 |
| Uci Rahayu | Yogyakarta | Premium | Rp4.656.603 | Rp99.000 | 87 |
| Zainal Abidin | Yogyakarta | Standard | Rp4.649.313 | Rp199.000 | 187 |
| Panji Nugroho | Jawa Tengah | Basic | Rp4.583.531 | Rp99.000 | 127 |
| Nadia Sari | Riau | Basic | Rp4.577.001 | Rp99.000 | 48 |
| Putri Anggraini | Sumatera Utara | Standard | Rp4.519.263 | Rp99.000 | 392 |
| Clara Indah | Sumatera Utara | Premium | Rp4.247.986 | Rp199.000 | 400 |
| Victor Chandra | Sumatera Utara | Premium | Rp4.203.734 | Rp349.000 | 146 |

### Insight

Daftar ini menunjukkan pelanggan churned yang memiliki total spending tinggi. Pelanggan seperti **Zainal Abidin**, **Doni Kurniawan**, dan **Victor Chandra** memiliki nilai transaksi historis yang besar, tetapi sudah berhenti berlangganan.

High-value churned customers seperti ini penting karena mereka menunjukkan bahwa pelanggan yang sebelumnya bernilai tinggi tetap memiliki risiko berhenti menggunakan layanan.

### Recommendation

Tim bisnis dapat memprioritaskan pelanggan pada daftar ini untuk program reactivation campaign. Strategi yang dapat digunakan adalah penawaran khusus, voucher personal, paket bundling, atau komunikasi langsung melalui customer success team.

---

## 9. Spending Comparison: Active vs Churned

### Query Result

| status | jumlah | avg_total_spent | min_spent | max_spent | avg_monthly_fee |
|---|---:|---:|---:|---:|---:|
| Active | 136 | Rp2.567.236 | Rp301.222 | Rp4.992.523 | Rp229.882 |
| Churned | 64 | Rp2.636.946 | Rp254.670 | Rp4.989.965 | Rp195.094 |

### Insight

Rata-rata total spending pelanggan churned adalah **Rp2.636.946**, sedangkan pelanggan aktif memiliki rata-rata total spending sebesar **Rp2.567.236**. Rata-rata spending pelanggan churned sedikit lebih tinggi dibanding pelanggan aktif.

Hal ini menunjukkan bahwa pelanggan yang berhenti berlangganan bukan hanya pelanggan bernilai rendah. Beberapa pelanggan churned justru memiliki nilai transaksi historis yang tinggi, sehingga kehilangan mereka dapat berdampak pada potensi pendapatan perusahaan.

### Recommendation

Strategi retensi sebaiknya tidak hanya berfokus pada pelanggan aktif, tetapi juga menyasar pelanggan churned dengan histori transaksi tinggi. Perusahaan dapat membuat daftar prioritas pelanggan churned berdasarkan total_spent untuk menentukan target win-back campaign.

---

## 10. Overall Business Insights

Berdasarkan hasil analisis, terdapat beberapa temuan utama:

1. **Churn rate keseluruhan sebesar 32.00%.**  
   Artinya, sekitar sepertiga pelanggan dalam dataset sudah berhenti berlangganan.

2. **Plan Standard memiliki churn rate tertinggi.**  
   Plan Standard memiliki churn rate sebesar 33.77% dan potensi monthly revenue lost terbesar sebesar Rp5.524.000.

3. **Churn rate tertinggi terjadi di DKI Jakarta.**  
   DKI Jakarta memiliki churn rate sebesar 60.00%, sehingga perlu menjadi perhatian dalam strategi retensi berbasis wilayah.

4. **Sebagian besar pelanggan churned berasal dari segmen High Value.**  
   Terdapat 38 pelanggan churned yang masuk kategori High Value, sehingga perusahaan kehilangan pelanggan dengan nilai transaksi tinggi.

5. **Terdapat banyak pelanggan aktif yang sudah berisiko churn.**  
   Sebanyak 38 pelanggan aktif masuk kategori High Risk karena tidak bertransaksi selama 90 hari atau lebih.

6. **Pelanggan churned memiliki rata-rata spending yang sedikit lebih tinggi dibanding pelanggan aktif.**  
   Ini menunjukkan bahwa churn juga terjadi pada pelanggan bernilai tinggi, bukan hanya pelanggan dengan kontribusi rendah.

---

## 11. Business Recommendations

Berdasarkan hasil analisis, rekomendasi bisnis yang dapat diberikan adalah:

1. **Prioritaskan win-back campaign untuk high-value churned customers.**  
   Pelanggan churned dengan total spending tinggi perlu menjadi target utama karena memiliki potensi revenue yang besar jika berhasil diaktifkan kembali.

2. **Buat early warning system untuk pelanggan aktif yang mulai tidak transaksi.**  
   Pelanggan yang tidak bertransaksi selama 60–90 hari perlu diberikan reminder, voucher, atau personalized offer sebelum masuk kategori churned.

3. **Evaluasi plan Standard dan Basic.**  
   Kedua plan ini memiliki churn rate yang lebih tinggi dibanding Premium. Perusahaan perlu mengevaluasi manfaat, harga, dan pengalaman pelanggan pada plan tersebut.

4. **Lakukan retensi berbasis wilayah.**  
   Provinsi dengan churn rate tinggi seperti DKI Jakarta, Yogyakarta, dan Sumatera Selatan dapat menjadi target campaign khusus.

5. **Gunakan SQL view untuk monitoring rutin.**  
   View seperti `v_churn_monthly`, `v_at_risk_customers`, dan `v_churn_summary` dapat digunakan untuk mempercepat monitoring churn tanpa harus menulis ulang query dari awal.

6. **Pantau monthly revenue lost dari pelanggan churned.**  
   Revenue lost dari churned customers perlu dipantau agar perusahaan dapat mengukur dampak churn terhadap pendapatan bulanan.

---

## 12. Conclusion

Project ini menunjukkan bahwa MySQL dapat digunakan untuk menganalisis churn pelanggan secara terstruktur. Dengan memanfaatkan `CASE WHEN`, date functions, CTE, subquery, self join, aggregate function, dan view, data subscription dapat diubah menjadi insight bisnis yang berguna untuk strategi retensi pelanggan.

Analisis ini tidak hanya menghitung jumlah pelanggan churned, tetapi juga membantu perusahaan memahami pelanggan mana yang perlu diprioritaskan, plan mana yang perlu dievaluasi, wilayah mana yang memiliki churn tinggi, serta pelanggan aktif mana yang sudah mulai berisiko churn.
