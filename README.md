2.1. Original code of broadcast chat.
![Screenshot 2.1](static/images/2.1.png)

Untuk menjalankan server, saya membuka 1 terminal dengan menjalankan perintah `cargo run --bin server`. Kemudian, untuk menjalankan 3 client, saya membuka 3 terminal dan menjalankan perintah `cargo run --bin client` pada ke 3 terminal tersebut. Masing-masing client terhubung ke 1 server, dimana jika salah satu client mengirimkan pesan ke server, semua client lainnya juga akan menerima response hasil pesan yang dikirim. 