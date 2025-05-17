# Event Publisher

## a. How much data your publisher program will send to the message broker in one run?
Publisher akan mengirimkan 5 event (data) ke message broker.

## b. What does 'amqp://guest:guest@localhost:5672' mean?
- guest pertama: username RabbitMQ
- guest kedua: password RabbitMQ
- localhost:5672: alamat dan port default RabbitMQ berjalan secara lokal

![Screenshot (2434)](https://github.com/user-attachments/assets/4d1859c4-a6e5-436d-85b6-692def08fd20)

![image](https://github.com/user-attachments/assets/da50bbda-98e2-4bd0-a281-1c465196ba1c)

Setelah publisher dijalankan beberapa kali, grafik pada dashboard RabbitMQ menunjukkan adanya spike pada message rates.

Ini menandakan bahwa setiap kali publisher dijalankan, beberapa event dikirim sekaligus ke message broker. RabbitMQ mencatat aktivitas ini sebagai lonjakan (spike) pada grafik jumlah pesan masuk.

Setiap spike mewakili batch event yang dikirim (5 event per `cargo run`). Grafik akan kembali turun setelah semua pesan diproses oleh subscriber.
