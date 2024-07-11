# PA-PC_202231096_Farrel-Laogi-Murjitama_D

A. Pendahuluan

Citra (image) atau istilah lain untuk gambar sebagai salah satu komponen multimedia memegang peranan sangat penting sebagai bentuk informasi visual. Meskipun sebuah citra kaya akan informasi, namun sering kali citra yang dimiliki mengalami penurunan mutu, misalnya mengandung cacat atau noise. Tentu saja citra semacam ini menjadi lebih sulit untuk diinterpretasikan karena informasi yang disampaikan oleh citra tersebut menjadi berkurang.

Untuk mengatasi noise tersebut perlu dilakukan usaha untuk memperbaiki kualitas citra itu. Salah satunya adalah dengan filtering citra baik secara linear maupun secara non-linear. Mean filter merupakan salah satu filtering linear yang berfungsi untuk memperhalus dan menghilangkan noise pada suatu citra yang bekerja dengan menggantikan intensitas nilai pixel dengan rata-rata dari nilai pixel tersebut dengan nilai pixel-pixel tetangganya.

Median filter adalah salah satu filtering non-linear yang mengurutkan nilai intensitas sekelompok pixel, kemudian mengganti nilai pixel yang diproses dengan nilai mediannya. Median filter telah digunakan secara luas untuk memperhalus dan mengembalikan bagian dari citra yang mengandung noise yang berbentuk bintik putih.

B. Landasan Teori

1. Perbaikan Kualitas Citra
Perbaikan kualitas citra merupakan suatu proses yang dilakukan untuk mendapatkan kondisi tertentu pada citra. Proses tersebut dilakukan dengan menggunakan berbagai macam metode tergantung pada kondisi yang diharapkan pada citra, seperti mempertajam bagian tertentu pada citra, menghilangkan noise atau gangguan, manipulasi kontras dan skala keabuan, dan sebagainya. Secara umum metode-metode yang digunakan dapat digolongkan kedalam dua kelompok yaitu metode domain frekuensi dan metode domain spasial.

Pada metode domain frekuensi, teknik pemrosesannya berdasarkan pada transformasi Fourier terhadap nilai pixel. Sedangkan pada metode domain spasial prosesnya dioperasikan langsung terhadap pixel, dimana untuk memproses sebuah pixel harus mengikut sertakan pixel-pixel tetangganya. Fungsi matematis dari metode domain spasial adalah sebagai berikut :
g (x,y) = T [f (x,y)]
f (x,y) adalah fungsi citra masukan, g (x,y) adalah citra hasil atau keluaran, sedangkan T adalah operator atas f, yang didefinisikan terhadap kumpulan tetangga-tetangga (x,y). Contoh dari metode ini adalah operasi filtering citra yaitu penghalusan citra dengan cara menghilangkan noise pada citra.

2. Metode Mean Filter
Metode mean filter adalah satu teknik filtering yang bekerja dengan cara menggantikan intensitas suatu pixel dengan rata-rata nilai pixel dari pixel-pixel tetangganya. Jika suatu citra f(x,y) yang berukuran M x N dilakukan proses filtering dengan penapis h(x,y) maka akan menghasilkan citra g(x,y), dimana penapis h(x,y) merupakan matrik yang berisi nilai 1/ukuran penapis. Secara matematis proses tersebut dapat dinyatakan sebagai berikut:

g(x,y) = f(x,y) * h(x,y)

Operasi diatas dipandang sebagai konvolusi antara citra f(x,y) dengan penapis h(x,y), dimana * menyatakan operator konvolusi dan prosesnya dilakukan dengan menggeser penapis konvolusi pixel per pixel.

3. Metode Median Filter

Metode median filter merupakan filter non-linear yang dikembangkan Tukey, yang berfungsi untuk menghaluskan dan mengurangi noise atau gangguan pada citra. Dikatakan nonlinear karena cara kerja penapis ini tidak termasuk kedalam kategori operasi konvolusi. Operasi nonlinear dihitung dengan mengurutkan nilai intensitas sekelompok pixel, kemudian menggantikan nilai pixel yang diproses dengan nilai tertentu.

Pada median filter suatu window atau penapis yang memuat sejumlah pixel ganjil digeser titik per titik pada seluruh daerah citra. Nilai-nilai yang berada pada window diurutkan secara ascending untuk kemudian dihitung nilai mediannya. Nilai tersebut akan menggantikan nilai yang berada pada pusat bidang window.
Jika suatu window ditempatkan pada suatu bidang citra, maka nilai pixel pada pusat bidang window dapat dihitung dengan mencari nilai median dari nilai intensitas sekelompok pixel yang telah diurutkan. Secara matematis dapat dirumuskan sebagai berikut:

- g(x,y)= Median {f(x-i,y-j).(i,j) E w}

dimana g(x,y) merupakan citra yang dihasilkan dari citra f(x,y) dengan w sebagai window yang ditempatkan pada bidang citra dan (i,j) elemen dari window tersebut.

4. Penilaian Kualitas Citra

Penilaian kualitas citra dilakukan dengan cara penilaian secara objektif dengan menggunakan besaran MSE dan PSNR kedua besaran tersebut membandingkan pixel-pixel pada posisi yang sama dari dua citra yang berlainan.

C. Tahapan penyelesaian proyek
Untuk menyelesaikan proyek pengolahan citra menggunakan filter median dan mean, dapat mengikuti tahapan-tahapan berikut secara rinci:

1. Persiapan Lingkungan Pengembangan
Instalasi Perpustakaan yang Diperlukan, dengan menginstal semua perpustakaan yang diperlukan untuk pengolahan citra, yaitu OpenCV, NumPy, dan Matplotlib. Bila belum menginstalnya, dapat menginstalnya dengan menajalankan kode pip:
pip install opencv-python numpy matplotlib
setelah diinstal dapat memanggil gambar dengan memasukkan kode dari section pada file program IPYNB terlampir:
- Import library

2. Memuat dan Menampilkan Gambar Asli
Langkah pertama adalah memuat gambar yang akan diolah dan menampilkannya. Untuk penerapan dapat menggunakan program dengan judul (section):
- Panggil (import) gambar

3. Penerapan Filter Median Menggunakan OpenCV
Filter median digunakan untuk mengurangi derau salt-and-pepper. OpenCV menyediakan fungsi 'cv2.medianBlur' untuk melakukan filter median. Untuk variabel median dapat menggunakan section:
- Filter median

4. Penerapan Filter Mean Secara Manual
Filter mean diterapkan dengan menghitung rata-rata nilai piksel di sekitar piksel target. Berikut adalah langkah-langkah untuk menerapkan filter mean secara manual:
a.Tentukan ukuran jendela filter (kernel).
b.Buat padding pada gambar untuk memastikan bahwa jendela filter dapat melampaui batas gambar asli.
c.Hitung rata-rata nilai piksel di dalam jendela filter.
d.Gantikan nilai piksel asli dengan nilai rata-rata yang telah dihitung.
Untuk program filter manual dapat meninjau section:
- Filter rata-rata (mean) manual
- Filter rata-rata dalam skala keabuan (grayscale)

5. Menampilkan Hasil Filter Median dan Mean
Setelah menerapkan filter median dan mean, langkah selanjutnya adalah menampilkan gambar asli, gambar setelah filter median, dan gambar setelah filter mean. Untuk penerapan dapat meninjau section:
- Menampilkan citra tergabung (sesuai soal)

6. Kesimpulan dan Analisis
Pada tahap akhir, lakukan analisis hasil pengolahan citra. Bandingkan gambar asli dengan gambar hasil filter median dan mean untuk mengevaluasi efektivitas masing-masing filter dalam mengurangi derau dan mempertahankan detail gambar.
Poin Analisis:
- Efektivitas Penghilangan Derau: Bandingkan seberapa baik filter median dan mean dalam mengurangi derau pada gambar.
- Ketajaman Tepi: Perhatikan apakah filter mean mengaburkan tepi gambar lebih dibandingkan dengan filter median.
- Aplikasi Potensial: Tentukan aplikasi potensial di mana setiap filter dapat digunakan berdasarkan hasil pengolahan citra.

D. Kesimpulan

Baik filter median maupun filter mean memiliki aplikasi dan keunggulan masing-masing dalam pengolahan citra. Filter median lebih unggul dalam menghilangkan derau impuls tanpa mengaburkan tepi, menjadikannya ideal untuk aplikasi di mana ketajaman tepi sangat penting. Di sisi lain, filter mean berguna untuk menghaluskan gambar secara umum dan mengurangi derau acak, meskipun dengan risiko mengaburkan tepi gambar.

Pemilihan filter yang tepat sangat bergantung pada jenis derau yang ada pada gambar dan tujuan akhir dari pengolahan citra tersebut. Memahami teori dan implementasi kedua filter ini dapat membantu dalam meningkatkan kualitas gambar sesuai dengan kebutuhan aplikasi pengolahan citra tertentu.

Filter median dan mean merupakan alat penting dalam toolkit pengolahan citra dan digunakan dalam berbagai aplikasi mulai dari medis hingga pengenalan pola dan visi komputer. Kekurangan dari kedua metode filtering yang digunakan adalah tidak dapat mempertahankan kualitas citra yang dihasilkan, jika ukuran penapis (mask) diperbesar.

E. Referensi

- Syarifuddi, S.N (2018). ANALISIS FILTERING CITRA DENGAN METODE MEAN FILTER DAN MEDIAN FILTER. Artikel Pengolahan Citra, https://elib.unikom.ac.id/download.php?id=6964
- Tarigan, I.J (2018). Teknik Filter Mean dan Median untuk Perbaikan Citra. Jurnal Armada Informatika, Vol.2, No.1, Juni 2018, pp. 30-36, 
https://jurnal.stmikmethodistbinjai.ac.id/
