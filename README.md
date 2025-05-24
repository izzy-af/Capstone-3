# Capstone-3 Bank Marketing
This repository is served as Purwadhika's 3rd capstone project created by Izzudin (JCDSOL-018) 

Analisis Machine Learning - Marketing Deposito Bank
Busisnees problem: 
Divisi Marketing Bank menghadapi tantangan dalam mengoptimalkan kampanye marketing untuk produk deposito berjangka.
iindikasi:
•	Pemborosan Biaya Marketing: Menghubungi prospek dengan probabilitas konversi rendah

•	Kehilangan Peluang Pendapatan: Melewatkan nasabah potensial yang sebenarnya berminat melakukan deposito

•	Inefisen Waktu dan Tenaga Kerja 

Masalah ini kritis karena berdampak langsung pada:

•	ROI: Model optimal (threshold 0.48) dapat meningkatkan ROI 600% dibanding pendekatan manual

•	Efisiensi cost: Targeting yang tepat mengurangi biaya kontak hingga 56.18%

•	Kepuasan Nasabah meningkat: Mengurangi gangguan terhadap nasabah yang tidak berminat, meningkatkan brand perception

Pendekatan Analisis yang Digunakan
Klasifikasi Biner dengan tujuan memprediksi apakah nasabah akan melakukan deposito ('yes') atau tidak ('no').
Model yang Dievaluasi:
•	Random Forest (Terpilih sebagai model terbaik)

•	XGBoost

•	LightGBM

Metrik Evaluasi yang Difokuskan pada Masalah Bisnis
Metrik Teknis:
•	F1 Score: Metrik utama untuk mengoptimalkan keseimbangan Precision-Recall

•	Precision: Mengurangi biaya False Positives (kontak sia-sia)

•	Recall: Memaksimalkan penangkapan True Positives (peluang konversi)

•	ROC-AUC: Mengukur kemampuan diskriminasi model

Metrik Bisnis:
•	Net Profit: Dampak finansial langsung dari model

•	ROI (Return on Investment): Efisiensi biaya kampanye

•	Cost per Conversion: Efektivitas biaya marketing

Kesimpulan dan Rekomendasi

Kesimpulan:
Pengembangan model prediksi yang dapat meningkatkan efektivitas kampanye marketing secara signifikan. Random Forest dengan threshold 0.48 terbukti memberikan performa terbaik dengan F1 Score 0.7077, mampu menangkap 67.8% dari nasabah potensial dengan precision 74.0%. Secara finansial, model ini menghasilkan net profit $43,760 dengan ROI 639.8% sambil mengurangi jumlah kontak hingga 56.2%.

Rekomendasi Strategis:
1. Implementasi Model
•	Gunakan Random Forest dengan threshold 0.48 untuk scoring nasabah

•	Target 684 nasabah (43.8% dari database) per kampanye untuk hasil optimal

•	Implementasikan sistem scoring real-time untuk segmentasi dinamis

2. Strategi Marketing Berbasis Feature Importance
Prioritaskan nasabah dengan karakteristik:
•	Balance tinggi (balance_clipped) - fitur paling penting

•	Usia mature (age) - segmen usia produktif

•	Riwayat sukses sebelumnya (previous_success) - loyalitas tinggi

•	Memiliki housing loan - indikator stabilitas finansial

3. Strategi Operasional berbasis feature importance
•	Budget Allocation: Alokasikan $6,840 per kampanye untuk mencapai 506 konversi

•	Timing: Fokus pada bulan-bulan tertentu berdasarkan month features

•	Channel: Prioritaskan cellular contact untuk efektivitas lebih tinggi

4. Strategi Maintenance dan monitoring
•	Lakukan model retraining dengan data terbaru

•	Monitoring F1 score dan business metrics secara berkala

•	Personalisasi konten marketing: Buat pesan marketing berbasis feature importance

•	Membuat fallback strategy jika perforama model menurun secara signifikan

Dampak Positif terhadap Bisnis:

•	Peningkatan Conversion Rate: Dari ~31% menjadi ~74% pada targeted segment

•	Efisiensi Biaya: Pengurangan 56.2% volume kontak dengan hasil lebih baik

•	Customer Experience: Mengurangi gangguan pada nasabah non-target

Akurasi Model Berdasarkan Jenis Data
Data dengan Akurasi TINGGI (Model Dapat Dipercaya):
•	Nasabah Existing dengan Histori Lengkap: previous_success/failure tersedia

•	Segmen Usia 25-65 tahun: Mayoritas data training berada di range ini

•	Balance dalam Range Normal: $0 - $50,000 (setelah clipping)

•	Contact Method Cellular: Feature dengan importance tinggi dan data lengkap

•	Bulan-bulan Peak Season: Mei, Juni, Agustus (data training abundant)

Data dengan Akurasi RENDAH (Model Kurang Dapat Dipercaya):
•	New Customers: Tanpa riwayat campaign sebelumnya

•	Extreme Age Groups: < 18 atau > 80 tahun

•	Very High Balance: > $50,000

•	Rare Job Categories: Job types dengan frequency < 1% dalam training

•	Unknown Contact History: Nasabah dengan informasi kontak tidak lengkap

Hubungan Evaluation Metrics dengan Aspek Bisnis Marketing Bank
Precision → Cost Efficiency
•	High Precision (74.0%): Dari 684 kontak, 506 akan convert

•	Business Impact: Biaya per conversion = $13.51 vs $32.47 pada random targeting

•	Marketing Implication: Budget marketing lebih efisien, ROI meningkat

Recall → Revenue Capture
•	Moderate Recall (67.8%): Menangkap 506 dari 746 potensi conversions

•	Business Impact: Potensi revenue loss $24,000 dari 240 missed opportunities

•	Marketing Implication: Trade-off antara efisiensi dan coverage maksimal

F1 Score → Balanced Strategy
•	Optimal F1 (0.7077): Keseimbangan terbaik cost-efficiency vs revenue-capture

•	Business Impact: Memberikan framework untuk decision making threshold

•	Marketing Implication: KPI utama untuk mengukur kesuksesan campaign

ROC-AUC → Model Reliability
•	Good AUC (0.7802): Model dapat membedakan prospek dengan baik

•	Business Impact: Confidence level tinggi untuk implementasi

•	Marketing Implication: Foundasi yang kuat untuk customer segmentation

Batasan Project:
•	Tidak ada digital footprint atau transaction history

• Tidak ada data faktor eksternal

•	Tidak ada data income, education, family status

•	Tidak ada informasi produk bank lainnya yang dimiliki nasabah

•	Data preferensi komunikasi terbatas

•	Static Model: Tidak ada learning adaptif atau online learning

•	Feature Engineering Masih manual
