# Resume Finger Simulation Experiment - F1D022091


## Data Understanding

_Jelaskan mengenai data yang digunakan dalam project kalian, seperti jumlah data, jumlah kelas, serta bagaimana cara kalian mendapatkan data tersebut._

Dalam project ini, saya menggunakan kumpulan data gambar yang merupakan semulasi dari sidik jari manusia. Di project ini terdapat lima kelas utama, yang masing-masing merepresentasikan satu jenis sidik jari. Dataset didapatkan dari pengambilan gambar langsung sidik jari.

## Data Preparation

### Image Augmentation

_Jelaskan kombinasi teknik augmentasi gambar apa saja yang kalian gunakan, serta berapa gambar yang dihasilkan dari 1 gambar asli._

Kombinasi teknik augmentasi yang digunakan yaitu rotasi dan pencerminan. Langkah pertama, menerapkan rotasi pada gambar asli dengan memutarnya sebanyak 90 derajat ke kanan dan ke kiri. Selanjutnya, melakukan pencerminan horizontal dan vertikal untuk menciptakan variasi dalam orientasi gambar. Dari satu gambar asli, akan menghasilkan sejumlah banyakData * 4 gambar baru

### Preprocessing

_Dari setiap percobaan yang telah kalian lakukan, jelaskan bagaimana cara kalian menemukan preprocessing yang paling tepat. Jelaskan alasan kalian menggunakan teknik tersebut dan berikan alasan mengapa preprocessing diperlukan._

Dari percobaan yang dilakukan, preprocessing yang paling tepat ditemukan melalui eksperimen dan evaluasi menggunakan matriks seperti akurasi, presisi, dan recall. Kombinasi teknik yang diuji meliputi grayscale, normalisasi, median filter, konvolusi, dan prewitt. Teknik-teknik ini dipilih karena grayscale mengurangi kompleksitas data, normalisasi mempercepat konvergensi dan meningkatkan stabilitas pelatihan, median filter mengurangi noise tanpa mengaburkan tepi, dan konvolusi serta prewitt menonjolkan fitur penting seperti tepi dan kontur. Preprocessing diperlukan untuk meningkatkan kualitas data, memastikan konsistenti, dan mengurangi kompleksitas gambar, sehingga mempercepat proses pelatihan dan meningkatkan kinerja model.

### Feature Selection

_Jelaskan bagaimana kalian menemukan fitur yang paling tepat untuk digunakan. Jelaskan alasan kalian menggunakan fitur tersebut dan berikan alasan mengapa fitur tersebut diperlukan._

Fitur yang paling tepat dipilih melalui serangkaian eksperimen sistematis. Berbagai fitur tekstur dari matriks co-occurrence level abu-abu (GLCM) dievaluasi, termasuk kontras, dissimilarity, homogenitas, entropi, ASM, energi, dan korelasi. Setiap fitur dievaluasi berdasarkan kemampuannya untuk meningkatkan kinerja model dengan metrik seperti akurasi, presisi, dan recall. Fitur-fitur kontras dan dissimilarity digunakan untuk mendeteksi tepi dan detail, homogenitas menilai kedekatan elemen dalam GLCM, entropi mengukur ketidakteraturan dalam gambar, dan ASM serta energi menunjukkan kehalusan tekstur. Korelasi mengukur hubungan linear antara piksel untuk mengidentifikasi pola dalam gambar. Fitur-fitur ini diperlukan karena memberikan informasi mendalam tentang tekstur dan struktur gambar, yang sangat penting untuk tugas pengenalan pola dan klasifikasi.

## Modeling

_Jelaskan bagaimana kalian melakukan hyperparameter tuning pada model tersebut._

Dalam melakukan hyperparameter tuning, digunakan metode grid search cross-validation, dengan menentukan rentang nilai untuk setiap hyperparameter, kemudian menggunakan GridSearchCV untuk mencari kombinasi terbaik dari hyperparamater tersebut. Model terbaik yang dihasilkan digunakan untuk melakukan prediksi pada data uji.

## Evaluation
 
_Jelaskan bagaimana peningkatan performa model dari metrics yang kalian gunakan pada berbagai percobaan yang telah kalian lakukan._

Dalam melihat peningkatan performa model dari metrics yang digunakan pada berbagai percobaan, perubahan dalam classification report dan confusion matrix dari setiap model, termasuk KNN, SVM, dan Random Forest, menjadi fokus utama. Peningkatan nilai precision, recall, dan f1-score dalam classification report, serta peningkatan jumlah true positives dan penurunan false positives dan false negatives dalam confusion matrix, menunjukkan kemajuan model. Dengan memantau perubahan ini, dapat diidentifikasi faktor-faktor yang memengaruhi performa model dan membuat penyesuaian yang diperlukan untuk meningkatkan kinerja keseluruhan.

_Catatan:_

- _Tutorial mengenai penggunaan Markdown dapat dibaca [di sini](https://guides.github.com/features/mastering-markdown/)_
- _Kalian dapat melakukan copy untuk file `percobaan_n.ipynb` (ganti `n` dengan nomor percobaan) untuk setiap percobaan yang kalian lakukan._