## Module 9
### Pradipta Arya P. - 2206083685

#### Reflection
1. What are the key differences between unary, server streaming, and bi-directional streaming RPC (Remote Procedure Call) methods, and in what scenarios would each be most suitable? 
    - **Unary RPC**: Metode ini melibatkan satu permintaan dan satu respons. Cocok untuk operasi yang sederhana dan tidak memerlukan data yang terus-menerus atau berkelanjutan.
    - **Server Streaming RPC**: Server mengirimkan beberapa respons ke klien berdasarkan satu permintaan. RPC ini cocok untuk kasus di mana data harus dikirim sebagai aliran, seperti mengirimkan pembaruan status atau data yang berkelanjutan.
    - **Bi-directional Streaming RPC**: Klien dan server dapat saling mengirimkan data dalam bentuk aliran, memungkinkan komunikasi dua arah yang lebih dinamis. Sangat cocok untuk aplikasi real-time seperti chat atau game online. <br><br>

2. What are the potential security considerations involved in implementing a gRPC service in Rust, particularly regarding authentication, authorization, and data encryption?
<br> Pertimbangan atau konsiderasi keamanan dalam implementasi gRPC pada Rust adalah memastikan autentikasi bahwa pengguna atau sistem yang mengakses layanan adalah orang yang memiliki akses. Kemudian dalam otorisasi adalah menverifikasi bahwa pengguna memiliki hak untuk melakukan operasi-operasi yang telah ditentukan. Lalu untuk enkripsi data, menggunakan protokol untuk mengamankan data yang ditransfer melalui jaringan, menghindari akses oleh pihak yang tidak memiliki wewenang.

3. What are the potential challenges or issues that may arise when handling bidirectional streaming in Rust gRPC, especially in scenarios like chat applications?
    - Mengelola aliran pesan yang masuk dan keluar secara efektif tanpa blok atau delay.
    - Memastikan stabilitas koneksi dan pengelolaan kesalahan yang efisien.
    - Mengimplementasikan logika backpressure untuk mengatur aliran data agar tidak membanjiri salah satu pihak. <br><br>

4. What are the advantages and disadvantages of using the tokio_stream::wrappers::ReceiverStream for streaming responses in Rust gRPC services?
    - **Kelebihan:** Memudahkan integrasi aliran data asinkron ke dalam model pemrograman yang didukung oleh tokio.
    - **Kekurangan:** Mungkin memerlukan lebih banyak pengelolaan sumber daya dan penanganan kesalahan yang kompleks tergantung pada kasus penggunaan. <br><br>

5. In what ways could the Rust gRPC code be structured to facilitate code reuse and modularity, promoting maintainability and extensibility over time?
<br> Dapat menggunakan trait beserta implementasinya untuk definisi fungsi yang dapat digunakan kembali. Dapat juga memisahkan definisi dan implementasi layanan ke dalam modul atau crate yang berbeda. Dapat juga dengan menggunakan generic programming untuk meningkatkan fleksibilitas. <br><br>

6. In the MyPaymentService implementation, what additional steps might be necessary to handle more complex payment processing logic?
    - Implementasi verifikasi dan validasi pembayaran yang lebih ketat.
    - Integrasi dengan sistem eksternal seperti gateway pembayaran.
    - Penanganan berbagai mata uang atau metode pembayaran <br><br>

7. What impact does the adoption of gRPC as a communication protocol have on the overall architecture and design of distributed systems, particularly in terms of interoperability with other technologies and platforms?
    - Memperbaiki interoperabilitas antar layanan dengan menggunakan protokol dan alat yang standar.
    - Dapat meningkatkan efisiensi komunikasi melalui penggunaan HTTP/2.
    - Memerlukan desain yang lebih ketat terkait kontrak antar layanan. <br><br>

8. What are the advantages and disadvantages of using HTTP/2, the underlying protocol for gRPC, compared to HTTP/1.1 or HTTP/1.1 with WebSocket for REST APIs?
    - **Kelebihan:** Lebih efisien, mendukung multiplexing, prioritas pemberian dan manajemen aliran.
    - **Kekurangan:** Kompleksitas implementasi dan potensi kebutuhan untuk optimisasi kinerja. <br><br>

9. How does the request-response model of REST APIs contrast with the bidirectional streaming capabilities of gRPC in terms of real-time communication and responsiveness?
    - REST menggunakan model permintaan-respons yang lebih sederhana, cocok untuk banyak kasus penggunaan web.
    - gRPC mendukung komunikasi dua arah secara real-time yang lebih cocok untuk aplikasi yang membutuhkan interaksi cepat dan berkelanjutan. <br><br>

10. What are the implications of the schema-based approach of gRPC, using Protocol Buffers, compared to the more flexible, schema-less nature of JSON in REST API payloads?
    - Protocol Buffers menyediakan serialisasi yang efisien dan struktur yang ketat, memungkinkan optimasi pada transmisi dan penyimpanan data.
    - JSON lebih fleksibel dan mudah digunakan
