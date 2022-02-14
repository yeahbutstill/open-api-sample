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

```json
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
        "summary": "Get All Payment",
        "description": "Only will return acative payment, complete payment or delete payment will be remove",
        "responses": {}
      },
      "post":  {
        "summary": "Create new Payment",
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

# Parameter
* Parameter adalah data yang dikirim tidak melalui Request Body 
* Operation bisa memiliki parameter lebih dari satu 
* OpenAPI mendukung beberapa jenis parameter, yaitu Query Parameter, Path Variable, Header, dan Cookie 
* Kita bisa menambahkan parameter pada Operation, sehingga pengguna bisa tahu bahwa ada parameter yang perlu dikirim ketika memanggil Operation tersebut

# Parameter Object (1)
![alt text][doc18]

[doc18]: doc/Screenshot%20from%202022-02-13%2010-11-59.png "Doc18"

# Parameter Object (2)
![alt text][doc19]

[doc19]: doc/Screenshot%20from%202022-02-13%2010-14-30.png "Doc19"

# Kode : Parameter (1)
```json5
"get": {
        "summary": "Get All Payment",
        "description": "Only will return acative payment, complete payment or delete payment will be remove",
        "parameters": [
          {
            "name": "include_done",
            "in": "query",
            "required": false,
            "description": "Is include done payment"
          },
          {
            "name": "va_customer",
            "in": "query",
            "required": false,
            "description": "Filter payment by VA customer"
          }
        ],
        "responses": {}
      }
```

# Kode : Parameter (2)
```json5
"/payment/{paymentId}" : {
      "put": {
        "summary": "Update existing Payment",
        "description": "Update existing payment in database",
        "parameters": [
          {
            "name": "paymentId",
            "in": "path",
            "required": true,
            "description": "Payment id for updated"
          }
        ],
        "responses": {}
      },
      "delete": {
        "summary": "Delete existing Payment",
        "description": "Delete existing payment in database",
        "parameters": [
          {
            "name": "paymentId",
            "in": "path",
            "required": true,
            "description": "Payment id for deleted"
          }
        ],
        "responses": {}
      }
    }
```

# Schema
* Saat kita membuat parameter, kita mungkin ingin memberitahu tentang tipe data untuk parameter tersebut 
* Parameter memiliki attribute bernama schema, dimana schema sebenarnya sangat kompleks, kita akan bahas secara bertahap 
* Dimulai dari simple schema, misal tipe data yang sebelumnya sudah kita bahas

# JSON Schema Specification
* Schema menggunakan JSON Schema untuk mendefinisikan struktur datanya 
* JSON Schema bisa berisikan tipe sederhana, seperti number, string, boolean dan lain-lain, atau bahkan tipe data kompleks, seperti object dan array (yang akan kita bahas nanti)
* https://json-schema.org/
* https://json-schema.org/draft/2020-12/json-schema-core.html 

# Kode: Schema
![alt text][doc20]

[doc20]: doc/Screenshot%20from%202022-02-13%2010-53-22.png "Doc20"

# JSON Schema Validation
* Schema mendukung JSON Schema Validation 
* Hal ini membuat kita bisa memberitahu validasi yang diperlukan ketika pengguna membaca OpenAPI kita 
* Dengan kita tambahkan Schema Validation, pengguna RESTful API kita bisa tahu validation yang kita buat tanpa harus kita buat dokumentasi secara terpisah
* https://json-schema.org/draft/2020-12/json-schema-validation.html 

# Kode: Schema Validation
![alt text][doc21]

[doc21]: doc/Screenshot%20from%202022-02-13%2017-59-34.png "Doc21"

# Request Body
* OpenAPI juga mendukung dokumentasi untuk request body 
* Dengan ini, kita memberi tahu tentang schema request body yang harus dikirim ketika menggunakan RESTful API kita 
* Request body mendukung schema, sehingga kita memberi tahu bentuk schema format data, bahkan validasi yang diperlukan

# Request Body Object
![alt text][doc22]

[doc22]: doc/Screenshot%20from%202022-02-13%2018-11-00.png "Doc22"

# Media Type Object
![alt text][doc23]

[doc23]: doc/Screenshot%20from%202022-02-13%2018-12-50.png "Doc23"

# Kode : Request Body
```json5
"post": {
        "summary": "Create new Payment",
        "description": "Create new active payment",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {

              }
            }
          }
        },
```

# Object Schema
* Sebelumnya kita hanya membuat schema sederhana, seperti schema tipe data boolean atau string 
* Spesifikasi di JSON Schema juga mendukung pembuatan schema berupa objek, yaitu data yang memiliki attribute lebih dari satu

# Kode : Object Schema
```json5
"application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "customer" : {
                    "type": "string",
                    "minLength": 1,
                    "required": true
                  },
                  "priority": {
                    "type": "integer",
                    "format": "int32",
                    "required": true,
                    "default": 1
                  }
                }
              }
            }
```

# Array Schema
* Selain tipe data object, Schema juga mendukung tipe data array 
* Saat membuat tipe data array, kita juga bisa menentukan tipe data items yang terdapat di array, bisa tipe data sederhana, bisa tipe data kompleks seperti object atau array lagi

# Kode : Array Schema
```json5
"tags": {
                    "type": "array",
                    "required": false,
                    "minItems": 1,
                    "items": {
                      "type": "string",
                      "minLength": 1
                    }
                  }
```

# Example
* OpenAPI mendukung example data 
* Example data merupakan data contoh yang bisa kita tambahkan baik itu di Parameter, Request Body dan Response Body

# Kode : Example di Parameter
```json5
{
            "name": "va_customer",
            "in": "query",
            "required": false,
            "description": "Filter payment by VA customer",
            "schema": {
              "type": "string",
              "minLength": 1,
              "maxLength": 30
            },
            "examples": {
              "fixed_virtual_account" : {
                "description": "Nomor akun virtual yang secara unik ditentukan oleh pelanggan. Misalnya, aplikasi e-wallet yang menggunakan nomor ponsel pengguna sebagai nomor ID. Dengan jenis virtual account ini, pengguna dapat melakukan pembayaran secara berulang untuk menambah saldo e-wallet tanpa harus memasukkan nomor ID setiap kali melakukan transaksi.",
                "value": "1087832081912"
              },
              "non_fixed_virtual_account" : {
                "description": "Nomor akun virtual yang ditentukan secara acak dan biasanya hanya bisa digunakan untuk satu kali transaksi. Misalnya, ketika pelanggan ingin melakukan pembayaran melalui virtual account di sebuah e-commerce, maka nomor ID yang diperoleh pelanggan tersebut tidak akan dapat digunakan kembali untuk melakukan transaksi lainnya.",
                "value": "123812371484182"
              }
```

# Kode : Example di Request Body
```json5
"examples": {
                "fixed_virtual_account" : {
                  "description": "Example create payment fixed VA",
                  "value": {
                    "va_customer" : "1087832081912",
                    "priority": 30,
                    "tags": [
                      "BCA",
                      "BSI",
                      "CIMB",
                      "BTN",
                      "BVIC"
                    ]
                  }
                },
                "non_fixed_virtual_account" : {
                  "description": "Example create payment non fixed VA",
                  "value": {
                    "va_customer" : "123812371484182",
                    "priority": 30,
                    "tags": [
                      "TOKOPEDIA",
                      "BUKALAPAK",
                      "SHOOPE",
                      "BLIBLI",
                      "LAZADA"
                    ]
                  }
                }
              }
```

# Response Body
* Selain Request Body, kita juga mendokumentasikan Response Body di OpenAPI 
* Dengan demikian, kita bisa memberi tahu format Response Body yang kita kembalikan pada RESTful API yang kita buat 
* Yang menarik di OpenAPI, kita bisa memberi tahu format response body sesuai dengan response status nya, misal kita bisa tentukan untuk response status 200, 400, 500, dan lain-lain

# Response Body Object
![alt text][doc24]

[doc24]: doc/Screenshot%20from%202022-02-14%2006-26-55.png "Doc24"

# Response Object
![alt text][doc25]

[doc25]: doc/Screenshot%20from%202022-02-14%2006-30-09.png "Doc25"

# Kode : Response Body
```json5
"200": {
            "description": "Success get all payment",
            "content": {
              "application/json": {
                "schema": {
                  "type": "array",
                  "items": {
                    "type": "object",
                    "properties": {
                      "id": {
                        "type": "string"
                      },
                      "va_customer": {
                        "type": "string"
                      },
                      "priority": {
                        "type": "number",
                        "format": "int32"
                      },
                      "tags": {
                        "type": "array",
                        "items": {
                          "type": "string"
                        }
                      }
                    }
                  }
                },
                "examples": {
                  "success": {
                    "description": "Example success get all payment",
                    "value": [
                      {
                        "id": "1",
                        "va_customer": "fixed_virtual_account",
                        "priority": 30,
                        "tags": [
                          "BCA",
                          "BSI",
                          "CIMB",
                          "BTN",
                          "BVIC"
                        ]
                      },
                      {
                        "id": "2",
                        "va_customer": "non_fixed_virtual_account",
                        "priority": 30,
                        "tags": [
                          "TOKOPEDIA",
                          "BUKALAPAK",
                          "SHOOPE",
                          "BLIBLI",
                          "LAZADA"
                        ]
                      }
                    ]
                  }
                }
              }
            }
          }
```