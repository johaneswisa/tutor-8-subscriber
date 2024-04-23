# Tutorial 8 
Johanes Wisanggeni - 2206032425 - Adpro A

a. what is amqp?
AMQP (Advanced Message Queuing Protocol) adalah protokol lapisan aplikasi standar terbuka untuk middleware berorientasi pesan, yang dirancang untuk antrian pesan, routing, dan pengiriman yang andal dan efisien. Umumnya digunakan dalam sistem terdistribusi untuk komunikasi antara aplikasi atau layanan.

b. what it means? guest:guest@localhost:5672 , what is the first quest, and what is
the second guest, and what is localhost:5672 is for? 

-"guest" adalah nama pengguna yang digunakan untuk otentikasi ke broker/server AMQP.

-"guest" pertama adalah nama pengguna.

-"localhost:5672" menentukan nama host dan nomor port dari broker/server AMQP.

-"localhost" menunjukkan bahwa broker/server berjalan di mesin lokal.

-"5672" adalah nomor port default untuk komunikasi AMQP.

Jadi, "guest:guest@localhost:5672" menunjukkan bahwa nama pengguna untuk otentikasi adalah "guest", kata sandinya juga "guest", dan broker/server AMQP berjalan di mesin lokal pada port 5672.

Karena program subscriber berjalan lebih lambat dari sebelumnya (code thread sleep) maka akan terjadi antrean messages sebelum akhirnya diterima oleh subscriber. Saya mendapatkan queued messages bernilai 10 yang menunjukan terdapat 10 messages yang ada pada antrian sebelum diterima oleh subsriber.
![alt text](<Screenshot (528).png>)

Setiap subscriber menerima pesan yang berbeda-beda. Ketiga subscriber berjalan secara paralel sehingga data publisher yang sudah diterima oleh satu subscriber tidak diterima dan tidak diproses oleh subscriber yang lain. Oleh karena itu, grafik chart queued messages mengalami penurunan yang lebih cepat dibandingkan saat hanya menjalankan satu subscriber. Yang bisa di-improve dari code adalah menggunakan enivronment variables untuk mengkonfigurasi URL (atau parameter lainnya) untuk meningkatkan portabilitas, keamanan, dan fleksibilitas aplikasi.
![alt text](<Screenshot (531).png>)
![alt text](<Screenshot (530).png>)
