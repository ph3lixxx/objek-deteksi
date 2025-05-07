# Realtime object detection

## Instructions

1. `git clone https://github.com/ph3lixxx/objek-deteksi'
2. `cd objek-deteksi`
3. `pip3 install imutils`
4. `python3 real_time_object_detection.py --prototxt MobileNetSSD_deploy.prototxt.txt --model MobileNetSSD_deploy.caffemodel`
5. Keluar dari jendela `q` untuk keluar
6. `python3 people_counter.py --prototxt MobileNetSSD_deploy.prototxt.txt --model MobileNetSSD_deploy.caffemodel`


## Penjelasan

🧠 1. Model Deteksi (MobileNet SSD - prototxt & caffemodel)
Fungsi:

    Melakukan inferensi (prediksi) terhadap objek dalam gambar/video (seperti manusia, mobil, anjing, dll).

Relevansi Keamanan Siber:

    Digunakan untuk membangun sistem pendeteksi intrusi fisik (Physical Intrusion Detection System).

    Dapat mendeteksi kehadiran manusia di area terlarang, bahkan saat tidak ada alarm berbunyi.

🎥 2. VideoStream (imutils.video.VideoStream)
Fungsi:

    Mengakses input dari webcam atau kamera (bisa PiCamera atau USB cam).

Relevansi Keamanan Siber:

    Kamera pengawas (CCTV) adalah komponen penting dalam sistem keamanan fisik.

    Integrasi dengan sistem AI memungkinkan respons otomatis terhadap aktivitas mencurigakan.

🧵 3. Multiprocessing (Queue dan Process)
Fungsi:

    Membagi proses deteksi ke proses terpisah agar tidak memperlambat pengambilan gambar/video.

    inputQueue → tempat frame dikirim ke proses anak.

    outputQueue → tempat hasil deteksi dikembalikan.

Relevansi Keamanan Siber:

    Penting untuk menjaga real-time monitoring, agar sistem tidak tertunda mendeteksi aktivitas berbahaya.

    Mengurangi risiko “missed detection” akibat lag atau bottleneck.

🧍 4. Deteksi Orang (Label: person)
Fungsi:

    Mengidentifikasi dan menghitung jumlah orang yang muncul di frame.

Relevansi Keamanan Siber:

    Crowd monitoring: mendeteksi kerumunan di tempat yang seharusnya tidak ramai.

    Access control: hanya memperbolehkan satu orang dalam suatu area tertentu.

    Dapat digunakan untuk mendeteksi tailgating (orang masuk bersamaan melewati akses kontrol).

📊 5. Confidence Threshold (--confidence)
Fungsi:

    Menyaring deteksi yang lemah atau tidak akurat.

Relevansi Keamanan Siber:

    Mengurangi false positive dalam sistem pemantauan.

    Membuat sistem lebih akurat dan andal untuk keputusan keamanan otomatis (misal, mengaktifkan alarm atau merekam log).

🖥️ 6. Output Visualisasi (cv2.imshow, cv2.rectangle, cv2.putText)
Fungsi:

    Menampilkan hasil deteksi langsung dalam jendela video.

    Memvisualisasi objek terdeteksi dan key info (kelas dan confidence).

Relevansi Keamanan Siber:

    Mempermudah operator keamanan untuk memantau dan memverifikasi deteksi AI.

    Bisa digunakan untuk pembuktian visual saat investigasi pelanggaran keamanan.

⏱️ 7. FPS Counter (imutils.video.FPS)
Fungsi:

    Mengukur performa sistem (Frame Per Second).

Relevansi Keamanan Siber:

    Penting untuk memastikan sistem tidak overload, yang bisa menyebabkan keterlambatan deteksi dan menurunkan efektivitas sistem keamanan.

💡 Kesimpulan Konteks Keamanan Siber:

Fungsi utama dari script ini adalah sebagai bagian dari sistem pengawasan cerdas (smart surveillance) yang sangat relevan dalam dunia keamanan siber, khususnya dalam domain physical security, edge computing, dan automated threat detection.

Kalau kamu tertarik, sistem ini bisa dikembangkan menjadi:

    Sistem deteksi intrusi otomatis.

    Counter masuk/keluar gedung untuk audit keamanan.

    Sistem alert real-time (email, Telegram, dsb).
