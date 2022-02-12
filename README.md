# open-api-sample


# Sebelum Belajar
temen-temen wajib sudah memahami basic
* HTTP
* RESTful API

# Agenda 
* Pengenalan OpenAPI 
* Tipe Data 
* Document 
* Info 
* Component 
* Path 
* Tag 
* Security 
* Dan lain-lain

# Pengenalan OpenAPI
* OpenAPI merupakan standar spesifikasi, tidak tergantung bahasa pemrograman apapun, untuk membuat dokumentasi RESTful API. 
* OpenAPI dibuat agar pengguna RESTful API tidak perlu mengakses kode aplikasi dan membaca dokumen manual (misal dalam bentuk doc, pdf) untuk memahami RESTful API yang dibuat 
* OpenAPI bisa menggunakan tool untuk menampilkan secara visual, bahkan untuk membuat kode program client atau server
* https://www.openapis.org/
* https://github.com/OAI/OpenAPI-Specification
* https://swagger.io/specification/ 

# Document Structure
* OpenAPI memiliki struktur document yang sudah standar 
* Namun kita diberi dua opsi untuk membuat document nya, bisa menggunakan JSON atau YAML
* https://www.json.org/
* https://yaml.org/ 

# OpenAPI Editor
* Document OpenAPI hanya menggunakan JSON atau Yaml, jadi untuk membuat document OpenAPI kita cukup menggunakan Text Editor 
* Namun jika kita ingin melihat OpenAPI dalam bentuk visual, kita juga bisa menggunakan Swagger Editor : https://editor.swagger.io/
* Jika menggunakan product JetBrains, bisa menggunakan plugin OpenAPI https://www.jetbrains.com/help/idea/openapi.html
* Jika menggunakan Visual Studio Code, bisa menggunakan plugin OpenAPI https://marketplace.visualstudio.com/items?itemName=42Crunch.vscode-openapi 

# Tipe Data
* Saat kita membuat RESTful API, sudah dipastikan kita akan membuat request dan response, dimana dalam data request dan response sudah dipastikan terdapat detail data 
* Misal jika terdapat data Product, pasti ada id, name, price, dan lain-lain 
* Semua detail data tersebut pasti memiliki tipe data 
* Kita tidak bisa menggunakan tipe data yang terdapat pada bahasa pemrograman yang digunakan untuk membuat RESTful API, oleh karena itu pada OpenAPI terdapat tipe data general yang bisa digunakan yang dapat dimengerti di semua bahasa pemrograman

# OpenAPI Tipe Data (1)
![alt text][doc]

[doc]: doc/Screenshot%20from%202022-02-12%2020-11-23.png "Doc"

