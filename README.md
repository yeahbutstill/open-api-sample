# Sebelum Belajar OpenApi
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
![alt text][doc1]

[doc1]: doc/Screenshot%20from%202022-02-12%2020-11-23.png "Doc1"

# OpenAPI Tipe Data (2)
![alt text][doc2]

[doc2]: doc/Screenshot%20from%202022-02-12%2020-18-22.png "Doc2"

# Document
* OpenAPI sangatlah sederhana, kita hanya perlu membuat satu file berisi semua data OpenAPI nya 
* OpenAPI memiliki struktur yang sudah ditentukan ketika membuat document nya 
* Kita bisa menggunakan JSON atau YAML untuk file nya
* https://spec.openapis.org/oas/v3.0.3#openapi-object 

# OpenAPI Object (1)
![alt text][doc3]

[doc3]: doc/Screenshot%20from%202022-02-12%2020-23-57.png "Doc3"

# OpenAPI Object (2)
![alt text][doc4]

[doc4]: doc/Screenshot%20from%202022-02-12%2020-26-12.png "Doc4"

# Kode : OpenAPI Document
```json5
{
  "openapi": "3.0.3",
  "info": {},
  "servers": [],
  "paths": {}
}
```

# info
* Info merupakan bagian dari informasi metadata tentang API yang kita buat 
* Kita bisa memasukkan author, lisensi, dan lain-lain

# Info Object
![alt text][doc6]

[doc6]: doc/Screenshot%20from%202022-02-12%2020-41-43.png "Doc6"

# Contact Object
![alt text][doc7]

[doc7]: doc/Screenshot%20from%202022-02-12%2020-47-46.png "Doc7"

# License Object
![alt text][doc8]

[doc8]: doc/Screenshot%20from%202022-02-12%2020-53-39.png "Doc8"

# Kode : Info
```json5

```