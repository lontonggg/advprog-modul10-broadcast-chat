# Advanced Programming - Module 10
#### Reyhan Zada Virgiwibowo - 2206081723 - Advanced Programming C

## 2.1. Original code of broadcast chat.
![Screenshot 2.1](static/images/2.1.png)

Untuk menjalankan server, saya membuka 1 terminal dengan menjalankan perintah `cargo run --bin server`. Kemudian, untuk menjalankan 3 client, saya membuka 3 terminal dan menjalankan perintah `cargo run --bin client` pada ke 3 terminal tersebut. Masing-masing client terhubung ke 1 server, dimana jika salah satu client mengirimkan pesan ke server, semua client lainnya juga akan menerima response hasil pesan yang dikirim. 

## 2.2. Modifying the websocket port

![Screenshot 2.2](static/images/2.2.png)

Untuk mengubah websocket pada client, kode yang harus dirubah adalah:

```rust
    let (mut ws_stream, _) =
    ClientBuilder::from_uri(Uri::from_static("ws://127.0.0.1:8080"))
        .connect()
        .await?;
```

Sedangkan untuk mengubah websocket pada server, kode yang harus diubah adalah:
```rust
   let listener = TcpListener::bind("127.0.0.1:8080").await?;
    println!("listening on port 8080");
```

Client dan juga server harus memiliki port yang sama agar terhubung ke 1 koneksi yang sama. Jika tidak, maka akan terjadi error karena client tidak dapat menemukan port yang tepat.
