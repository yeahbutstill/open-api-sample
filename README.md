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

* OpenAPI merupakan standar spesifikasi, tidak tergantung bahasa pemrograman apapun, untuk membuat dokumentasi RESTful
  API.
* OpenAPI dibuat agar pengguna RESTful API tidak perlu mengakses kode aplikasi dan membaca dokumen manual (misal dalam
  bentuk doc, pdf) untuk memahami RESTful API yang dibuat
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

* Document OpenAPI hanya menggunakan JSON atau Yaml, jadi untuk membuat document OpenAPI kita cukup menggunakan Text
  Editor
* Namun jika kita ingin melihat OpenAPI dalam bentuk visual, kita juga bisa menggunakan Swagger
  Editor : https://editor.swagger.io/
* Jika menggunakan product JetBrains, bisa menggunakan plugin OpenAPI https://www.jetbrains.com/help/idea/openapi.html
* Jika menggunakan Visual Studio Code, bisa menggunakan plugin
  OpenAPI https://marketplace.visualstudio.com/items?itemName=42Crunch.vscode-openapi

# Tipe Data

* Saat kita membuat RESTful API, sudah dipastikan kita akan membuat request dan response, dimana dalam data request dan
  response sudah dipastikan terdapat detail data
* Misal jika terdapat data Product, pasti ada id, name, price, dan lain-lain
* Semua detail data tersebut pasti memiliki tipe data
* Kita tidak bisa menggunakan tipe data yang terdapat pada bahasa pemrograman yang digunakan untuk membuat RESTful API,
  oleh karena itu pada OpenAPI terdapat tipe data general yang bisa digunakan yang dapat dimengerti di semua bahasa
  pemrograman

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
"info": {
"title": "Bill Payment RESTful API",
"version": "1",
"description": "OpenAPI for Bill Payment RESTful API",
"termsOfService": "https://www.yeahbutsill.com/payment",
"contact": {
"name": "Dani Setiawan",
"url": "https://www.yeahbutsill.com",
"email": "dani.setiawan@ist.id"
},
"license": {
"name": "APACHE 2.0",
"url": "https://www.apache.org/licenses/LICENSE-2.0"
}
```

# Server

* Saat kita membuat API sudah pasti terdapat server RESTful API yang nanti akan kita buat
* Kita bisa memberitahu server yang tersedia di OpenAPI
* Misal, terdapat server development, staging, production dan lain-lain

# Server Object

![alt text][doc9]

[doc9]: doc/Screenshot%20from%202022-02-13%2005-13-34.png "Doc9"

# External Documentation
* External documentation merupakan bagian dalam OpenAPI jika kita ingin menambahkan link tambahan dalam OpenAPI 
* Bisa menuju link documentation lain, atau mungkin link menuju website

# External Documentation Object

![alt text][doc10]

[doc10]: doc/Screenshot%20from%202022-02-13%2009-16-34.png "Doc10"

# Kode: External Documentation
```json5
"externalDocs": {
    "description": "Github Yeah But Still",
    "url": "https://github.com/yeahbutstill"
  }
```

# Path
* Path merupakan representasi endpoint API di OpenAPI 
* Pada Path, kita tidak perlu menuliskan seluruh URL, cukup url di belakang setelah lokasi server

# Path Object
![alt text][doc11]

[doc11]: doc/Screenshot%20from%202022-02-13%2009-25-56.png "Doc11"

# Path Item Object (1)
![alt text][doc12]

[doc12]: doc/Screenshot%20from%202022-02-13%2009-28-12.png "Doc12"

# Path Item Object (2)
![alt text][doc13]

[doc13]: doc/Screenshot%20from%202022-02-13%2009-29-29.png "Doc13"

# Path Operation
![alt text][doc14]

[doc14]: doc/Screenshot%20from%202022-02-13%2009-31-51.png "Doc14"

# Kode : Path
```json5
"paths": {
    "/payment" : {
      "get": {},
      "post":  {}
    },
    "/payment/{paymentId}" : {
      "put": {},
      "delete": {}
    }
  }
```

# Operation
* Setiap Path yang kita buat di OpenAPI, bisa memiliki lebih dari satu Operation 
* Hal ini dikarenakan, dalam HTTP, satu URL bisa memiliki beberapa HTTP Method 
* Misal url untuk mengambil semua data dan membuat data baru, mungkin url nya sama, yang membedakan adalah HTTP Method nya, GET untuk mengambil data, POST untuk membuat data 
* Inti dari API Documentation adalah dokumentasi operation yang terdapat pada RESTful API yang kita buat

# Operation Object (1)
![alt text][doc15]

[doc15]: doc/Screenshot%20from%202022-02-13%2009-49-11.png "Doc15"

# Operation Object (2)
![alt text][doc16]

[doc16]: doc/Screenshot%20from%202022-02-13%2009-50-46.png "Doc16"

# Operation Object (3)
![alt text][doc17]

[doc17]: doc/Screenshot%20from%202022-02-13%2009-52-51.png "Doc17"

# Kode : Operation
```json5
"paths": {
    "/payment" : {
      "get": {
        "semmary": "Get All Payment",
        "description": "Only will return acative payment, complete payment or delete payment will be remove",
        "responses": {}
      },
      "post":  {
        "semmary": "Create new Payment",
        "description": "Create new active payment",
        "responses": {}
      }
    },
    "/payment/{paymentId}" : {
      "put": {},
      "delete": {}
    }
  }
```

#