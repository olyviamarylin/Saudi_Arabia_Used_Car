# Saudi_Arabia_Used_Car
**LATAR BELAKANG**

Pasar jual-beli mobil bekas di Arab Saudi berkembang pesat, terutama dengan meningkatnya permintaan pelanggan di berbagai wilayah. Salah satu platform jual-beli mobil bekas di Saudi Arabia berfungsi sebagai penghubung antara penjual dan pembeli. Platform ini menyediakan ruang bagi penjual untuk memasarkan mobil mereka dan memungkinkan calon pembeli untuk membandingkan berbagai pilihan berdasarkan tipe, merek, jarak tempuh, dan harga. Namun, dengan banyaknya daftar mobil yang tersedia, menetapkan harga yang optimal menjadi tantangan tersendiri. 
Penjual harus dapat menentukan harga yang cukup kompetitif untuk menarik calon pembeli tanpa mengorbankan keuntungan mereka. Jika harga yang ditetapkan terlalu tinggi, pembeli cenderung akan berpaling, sementara harga yang terlalu rendah berisiko merugikan penjual. Proses penetapan harga mobil bekas melibatkan banyak variabel yang saling memengaruhi, sehingga memerlukan pendekatan yang lebih sistematis untuk efisiensi cost pada analisis Harga mobil bekas yang akan di jual.

**PERMASALAHAN**

Platform tersebut dihadapkan pada tantangan besar dalam membantu penjual menetapkan harga yang tepat, harga yang tidak hanya menarik bagi calon pembeli tetapi juga memastikan keuntungan yang memadai bagi penjual. Banyak penjual sering kali menghadapi kesulitan dalam menentukan harga yang sesuai, meskipun mereka dapat membandingkan harga kendaraan yang serupa di platform tersebut. 

**TUJUAN**

Berdasarkan permasalahan yang dimiliki membutuhkan sebuah alat analisis prediktif yang dapat membantu penjual menentukan harga jual mobil bekas yang lebih akurat. Fitur-fitur penting seperti merek, tahun produksi, jarak tempuh, ukuran mesin, dan lokasi penjualan harus dianalisis untuk mendapatkan estimasi harga yang lebih presisi. Dengan prediksi harga yang lebih akurat, penjual dapat menawarkan harga yang kompetitif, menarik lebih banyak pembeli, dan tetap memperoleh keuntungan yang optimal. Selain itu, keakuratan prediksi harga dapat meningkatkan tingkat keberhasilan transaksi di platform, yang pada akhirnya akan mendorong peningkatan volume penjualan, mempercepat pertumbuhan bisnis mobil bekas, dan memberikan kontribusi positif terhadap pendapatan platform melalui komisi penjualan.

**ALGORITMA/PERMODELAN**

Dalam membantu menganalisa dataset yang dimiliki, Model yang digunakan adalah Regresi linear. Fungsi utama algoritma ini adalah menemukan parameter optimal yang meminimalkan error dalam prediksi. karna hubungan Linear Antar Variabel seperti Harga mobil bekas umumnya memiliki hubungan linear dengan faktor-faktor seperti tahun produksi, jarak tempuh (mileage), merek, kondisi mesin, dan fitur lainnya. Dalam dataset dengan pola yang relatif sederhana dan fitur yang saling berhubungan secara linear, regresi linear dapat memberikan performa yang konsisten.

**Matriks Evaluasi (RMSE, MAE, MAPE)**

Selain melakukan permodelan, matriks Evaluasi (RMSE, MAE, MAPE) juga digunakan untuk memahami performa model dari berbagai perspektif, yaitu:
RMSE (Root Mean Squared Error)
Mengukur rata-rata akar kuadrat dari error antara nilai aktual dan prediksi. Semakin kecil RMSE, semakin baik model memprediksi data.
MAE (Mean Absolute Error)
Rata-rata dari selisih absolut antara nilai aktual dan prediksi. Memberikan gambaran yang jelas tentang error rata-rata dalam unit aslinya (misalnya, Riyal Saudi).
MAPE (Mean Absolute Percentage Error)
Rata-rata dari persentase error absolut antara prediksi dan nilai aktual. Berguna untuk memahami seberapa besar error dalam bentuk persentase.

**KETERANGAN DATASET**
Type: Tipe mobil bekas.  
Region: Wilayah tempat mobil bekas ditawarkan untuk dijual.  
Make: Nama perusahaan pembuat mobil.  
Gear_Type: Tipe ukuran transmisi mobil bekas.  
Origin: Asal mobil bekas.  
Options: Opsi atau fitur mobil bekas.  
Year: Tahun pembuatan.  
Engine_Size: Ukuran mesin mobil bekas.  
Mileage: Jarak tempuh mobil bekas.  
Negotiable: Bernilai True jika harga adalah 0, artinya harga bisa dinegosiasikan.  
Price: Harga mobil bekas. 

**Deskripsi Tentang XGBRegressor**

XGBoost (Extreme Gradient Boosting) adalah algoritma ensemble learning yang menggabungkan beberapa model decision tree untuk memaksimalkan akurasi prediksi.
Keunggulan XGBRegressor:
Dapat menangani data dengan hubungan non-linear yang kompleks.
Memiliki mekanisme regularization (L1 dan L2) untuk mencegah overfitting.
Optimal dalam menangani data dengan banyak fitur dan outlier.
Menggunakan teknik Gradient Boosting untuk memperbaiki error di setiap iterasi.
Maka dari itu Penggunaan XGBoost Pada Saudi Arabia Used Car bertujuan untuk Meningkatkan akurasi prediksi harga mobil bekas, Menangani pola yang lebih kompleks dan non-linear dalam dataset dan Memberikan model yang lebih stabil dan lebih dapat diandalkan dalam berbagai skenario. 

**KESIMPULAN**

Berdasarkan hasil benchmarking model, diperoleh XGBRegressor dengan nilai MAPE -19.3% sebagai model terbaik dibandingkan dengan model lainnya. Model ini menunjukkan kinerja yang stabil setelah dilakukan proses hyperparameter tuning, di mana terjadi penurunan error yang signifikan.  Setelah model diuji pada Test Set, hasilnya menunjukkan performa yang lebih baik dengan MAPE sekitar 18.8%. Hal ini menunjukkan bahwa model yang dipilih mampu memprediksi data di luar data pelatihan dengan cukup baik dan stabil saat digunakan untuk memprediksi data baru di masa mendatang.  Rentang data pelatihan mencakup harga mobil dari 11,000 SAR hingga 575,000 SAR Ini berarti model bekerja dengan baik dalam rentang ini, tetapi mungkin menjadi kurang akurat jika memprediksi di luar rentang tersebut. Namun, kesalahan prediksi cenderung lebih besar pada harga mobil yang lebih rendah. Misalnya, jika harga mobil sebenarnya adalah 10,000 SAR, prediksi bisa saja berada di sekitar 12,100 SAR (kesalahan cukup signifikan dalam persentase). 
Jika dilihat dari feature importance, fitur yang paling berpengaruh dalam memprediksi harga mobil bekas adalah:  
Tahun produksi (Year)
Perusahaan Produksi Mobil (Make)
Ukuran mesin (Engine Size)
Fitur-fitur ini memberikan kontribusi signifikan dalam menentukan harga mobil bekas, di mana mobil dengan tahun produksi yang lebih baru, opsi fitur yang lebih lengkap, dan ukuran mesin yang lebih besar cenderung memiliki harga yang lebih tinggi. Selain itu, model ini dapat membantu Tim Strategi Bisnis Penjualan Mobil Bekas dalam membuat proyeksi harga yang lebih akurat di masa mendatang. Tren dari fitur-fitur tersebut juga mengindikasikan bahwa pasar mobil bekas di tahun-tahun mendatang kemungkinan besar akan mengalami peningkatan harga seiring dengan tren permintaan dan karakteristik mobil yang tersedia.  
Meskipun demikian, terdapat keterbatasan pada fitur yang digunakan dalam model ini. Variabel penting seperti kondisi fisik kendaraan dan riwayat kecelakaan belum dimasukkan, yang kemungkinan besar dapat meningkatkan performa model secara signifikan karna dengan adanya feature tambahan tersebut membuat semakin besar rentang variasinya Secara keseluruhan, model XGBRegressor yang telah di-tuning memberikan hasil yang memuaskan dan dapat digunakan untuk memprediksi harga mobil bekas di rentang data yang telah disediakan. Namun, untuk meminimalkan kesalahan lebih lanjut, diperlukan peningkatan pada fitur yang lebih representatif dan eksplorasi lebih lanjut terhadap fitur yang memiliki potensi tinggi dalam memengaruhi harga mobil bekas.

**REKOMENDASI**

Berikut adalah beberapa rekomendasi berdasarkan pemilihan model yang telah dilakukan:
Karena kita mengetahui bahwa prediksi untuk harga mobil dengan rentang yang lebih tinggi memiliki akurasi yang lebih baik dibandingkan dengan rentang harga yang lebih rendah, perlu dilakukan analisis lebih lanjut mengenai penyebab rendahnya akurasi pada harga yang lebih rendah. Fitur-fitur dalam regresi ini sebagian besar bersifat kategorikal yang dapat membentuk pola tertentu. Akurasi yang rendah pada harga rendah kemungkinan disebabkan oleh adanya pola yang membingungkan di antara fitur-fitur tersebut. Dengan memahami fitur mana yang menyebabkan kebingungan dalam proses pembelajaran, kita dapat melakukan rekayasa fitur (feature engineering) yang lebih mendalam pada fitur tersebut.
Berdasarkan dataset awal, kita dapat melihat bahwa fitur yang digunakan masih terbatas. Sebagian besar fitur yang digunakan berfokus pada karakteristik umum kendaraan seperti merek, model, tahun, ukuran mesin, dan opsi fitur. Namun, fitur penting lainnya yang dapat memengaruhi harga mobil bekas, seperti kondisi fisik kendaraan (misalnya tanpa kerusakan, goresan ringan, kerusakan sedang, kerusakan parah) dan riwayat kecelakaan (misalnya, 0 untuk tanpa kecelakaan, 1 untuk satu kali kecelakaan, dan seterusnya) masih belum dimasukkan. Dengan menambahkan variabel tersebut, model akan mampu memprediksi harga mobil dengan lebih akurat. Hal ini memungkinkan kita untuk membangun model yang lebih spesifik untuk setiap kategori, yang pada akhirnya akan meningkatkan akurasi prediksi secara keseluruhan.
Dengan menerapkan rekomendasi ini, diharapkan model dapat memberikan prediksi harga mobil bekas yang lebih akurat dan mendukung pengambilan keputusan strategis dalam bisnis.
