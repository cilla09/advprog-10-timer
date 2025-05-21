# Advprog Tutorial 10 - Timer
## Priscilla Natanael Surjanto - 2306152153

### 1.2 Understanding how it works
![image](images/image1.png)
Fungsi utama `main()` pertama-tama membuat eksekutor dan spawner, kemudian menggunakan `spawner.spawn` untuk mengeksekusi tugas asinkron yang mencetak "howdy!", menunggu selama 2 detik menggunakan `TimerFuture::new(Duration::new(2, 0))`, dan setelah itu mencetak "done!". Sementara itu, program akan langsung mencetak "hey hey" karena berada di luar tugas yang dipanggil oleh `spawn`. `TimerFuture` bekerja dengan cara menjalankan thread terpisah yang tidur selama durasi yang ditentukan dan kemudian mengubah status internalnya menjadi "completed". Begitu selesai, thread tersebut memberi tahu tugas untuk melanjutkan eksekusinya melalui `waker`. Output yang dihasilkan seperti ini karena sifat asinkron dari eksekusi tugas, di mana tugas utama tidak terblokir dan bisa menjalankan kode lainnya, sementara tugas yang dipanggil dengan `spawn` berjalan secara bersamaan dan menyelesaikan tugas setelah 2 detik, yang akhirnya mencetak "done!".








