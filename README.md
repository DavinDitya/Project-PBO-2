# Project-PBO-2

### I Gusti Bagus Davin Dharma Ditya
2205551122

## About
Program ini bertujuan untuk membuat backend API yang akan digunakan dalam sebuah aplikasi e-commerce yang sederhana. API ini akan memberikan tanggapan dalam bentuk JSON. API ini akan mendukung berbagai metode permintaan, termasuk:
<br/>
**GET** untuk mendapatkan list atau detail data dari entitas. <br/>
**POST** untuk membuat data entitas baru. <br/>
**PUT** untuk mengubah data dari entitas. <br/>
**DELETE** untuk menghapus data dari entitas. <br/>

Semua data yang digunakan dalam aplikasi e-commerce ini akan disimpan di dalam sebuah **database SQLite**. Database ini akan digunakan untuk menyimpan informasi seperti data produk, data pelanggan, dan detail pesanan. Penggunaan database SQLite memungkinkan aplikasi untuk menyimpan dan mengelola data secara efisien. Selain itu, setelah backend API telah diprogram, akan dilakukan pengujian API menggunakan aplikasi **Postman**.

## Spesifikasi API dalam Aplikasi e-Commerce 
### **GET**

- GET /users untuk mendapatkan daftar semua user yang termuat di dalam database. <br/>
**http://localhost:8122/users** 


[

    {
        "firstName": "Davin",
        "lastName": "Ditya",
        "addresses": [],
        "phoneNumber": "082147309044",
        "id": 1,
        "type": "Buyer",
        "email": "davinditya@gmail.com"
    },
    {
        "firstName": "Sukma",
        "lastName": "Nigraha",
        "addresses": [],
        "phoneNumber": "082374893723",
        "id": 2,
        "type": "Seller",
        "email": "sukmanigraha@gmail.com"
    },
    {
        "firstName": "Rama",
        "lastName": "Putra",
        "addresses": [],
        "phoneNumber": "082347837482",
        "id": 3,
        "type": "Seller",
        "email": "rmaptra@gmail.com"
    },
    {
        "firstName": "Made",
        "lastName": "Jauhari",
        "addresses": [],
        "phoneNumber": "087493784736",
        "id": 4,
        "type": "Seller",
        "email": "mdjauhari@gmail.com"
    },
    {
        "firstName": "Nanda",
        "lastName": "Febian",
        "addresses": [],
        "phoneNumber": "08291327391",
        "id": 5,
        "type": "Buyer",
        "email": "nndafbian@gmail.com"
    }
]


<br/>

- GET /users/{id} untuk mendapatkan informasi user dan alamatnya. <br/>
**http://localhost:8122/users/1**

[

    {
        "firstName": "Davin",
        "lastName": "Ditya",
        "addresses": [
            {
                "province": "Bali",
                "city": "Denpasar",
                "postcode": "80114"
            }
        ],
        "phoneNumber": "082147309044",
        "id": 1,
        "type": "Buyer",
        "email": "davinditya@gmail.com"
    }
]


<br/>

- GET /users/{id}/products untuk mendapatkan daftar produk milik user. <br/>
**http://localhost:8122/users/2/products** 

[

    {
        "seller": 2,
        "price": "25000",
        "description": "Coklat Nikmat",
        "id": 1,
        "title": "SilverQueen",
        "stock": 50
    }
]

<br/>

- GET /users/{id}/orders untuk mendapatkan daftar order milik user. <br/>
**http://localhost:8122/users/1/orders**

[

    {
        "note": 2,
        "total": 5000,
        "discount": 0,
        "id": 1,
        "is_paid": "1",
        "buyer": 1
    }
]

<br/>

- GET /users/{id}/reviews untuk mendapatkan daftar review yang dibuat oleh user. <br/>
**http://localhost:8122/users/1/reviews**

[

    {
        "star": 5,
        "description": "Coklatnya Nikmat Banget",
        "order": 1
    }
]

<br/>

- GET /orders/{id} untuk mendapatkan informasi order, buyer, detail order, review, product title, beserta pricenya. <br/>
**http://localhost:8122/orders/1**

[

    {
        "note": 2,
        "total": 5000,
        "reviews": [
            {
                "star": 5,
                "description": "Coklatnya Nikmat Banget"
            }
        ],
        "discount": 0,
        "id": 1,
        "is_paid": "1",
        "order_detail": [
            {
                "product": "SilverQueen",
                "quantity": 2,
                "price": 2500
            }
        ],
        "buyer": 1
    }
]

<br/>

- GET /products untuk mendapatkan daftar semua produk. <br/>
**http://localhost:8122/products**

[

    {
        "seller": 2,
        "price": "25000",
        "description": "Coklat Nikmat",
        "id": 1,
        "title": "SilverQueen",
        "stock": 50
    },
    {
        "seller": 3,
        "price": "8000",
        "description": "Mengandung Vitamin C",
        "id": 2,
        "title": "UC1000",
        "stock": 58
    },
    {
        "seller": 4,
        "price": "5000",
        "description": "Minuman Segar",
        "id": 3,
        "title": "PopIce",
        "stock": 30
    }
]

<br/>

- GET /products/{id} untuk mendapatkan informasi produk dan seller. <br/>
**http://localhost:8122/products/1**

[

    {
        "seller": 2,
        "price": "25000",
        "description": "Coklat Nikmat",
        "id": 1,
        "title": "SilverQueen",
        "stock": 50,
        "first_name": "Davin"
    }
]

<br/>

### **POST**
- Menambah data baru kedalam user <br/>

{

    "id":"",
    "first_name":"Dede",
    "last_name":"Baskara",
    "email":"ddbaskara@gmail.com",
    "phone_number":"081412831821",
    "type":"Seller"
}

1 rows inserted!

<br/>


### **PUT**
- Mengubah data pada tabel users <br/>
**http://localhost:8122/users/1**
<br/>

{

    "id":"1",
    "first_name":"Davin",
    "last_name":"Ditya",
    "email":"davinditya@gmail.com",
    "phone_number":"082147309044",
    "type":"Buyer"
}

1 rows updated!

### **DELETE**
- Menghapus data dari entitas tertentu dimana saya mencoba untuk menghapus data yang terdapat pada tabel users id 4 <br/>
**http://localhost:8122/users/4**

1 rows deleted!

<br/>
