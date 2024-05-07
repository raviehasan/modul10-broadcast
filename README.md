# Reflection Notes

### 2.1. Original code of broadcast chat

Server:
![alt text](image.png)

Client 1:
![alt text](image-1.png)

Client 2:
![alt text](image-2.png)

Client 3:
![alt text](image-3.png)

Client 1 setelah semua client mengirim pesan:
![alt text](image-5.png)

Client 2 setelah semua client mengirim pesan:
![alt text](image-6.png)

Client 3 setelah semua client mengirim pesan:
![alt text](image-7.png)

Server setelah semua client mengirim pesan:
![alt text](image-4.png)

How to run server? Jalankan command `cargo run --bin server` pada terminal. 
How to run 3 clients? Jalankan `cargo run --bin client` pada 3 terminal yang berbeda.
Ketika menjalankan server, server akan listening pada request ayng masuk di port 2000. Dengan demikian, setiap ada client yang connect, server akan print out "New connection from 127.0.0.1:(port)". Kemudian, di sisi client, akan print out "From server: Welcome to chat! Type a message" sebagai feedback bahwa sudah connected dengan server. Ketika salah satu client mengetikkan pesan, server akan print out "From client 127.0.0.1:61849 "Hello, from client 1"". Kemudian, pada sisi client, setiap client akan mendapatkan print out "From server: (message yang dikirimkan client)". Pada intinya, server akan keep track connection dengan setiap clientnnya, kemudian jika ada pesan dari suatu client, maka semua client yang connected juga akan mendapatkan pesan tersebut. Hal ini dapat dilihat pada screenshots yang telah saya cantumkan di atas.

Client 1 setelah semua client mengirim pesan:
![alt text](image-9.png)

Client 2 setelah semua client mengirim pesan:
![alt text](image-10.png)

Client 3 setelah semua client mengirim pesan:
![alt text](image-11.png)

Server setelah semua client mengirim pesan:
![alt text](image-8.png)

Dapat dilihat bahwa pada sisi server, printout yang muncul adalah "listening on port 8080", tidak lagi di port 2000 seperti sebelumnya. Kemudian, untuk interaksi yang muncul di terminal kurang lebih sama seperti sebelumnya, mengingat yang diubah hanya portnya. Perlu dicatat bahwa ketika port pada file server dan client berbeda, maka akan terjadi error. Hal ini terjadi karena server keep track connections dari client di suatu port, sedangkan client mengirimkan request ke port lain. Namun, pada kasus ini kedua file server dan client telah diset pada port yang sama. Dengan demikian, server dan client tetap dapat berinteraksi dengan lancar. Hence, interaksi yang terjadi sama seperti pada bagian 2.1 sebelumnya.