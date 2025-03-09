# Bookshelf API

## Overview
Bookshelf API adalah layanan RESTful API yang memungkinkan pengguna untuk mengelola koleksi buku mereka, termasuk menambahkan, memperbarui, menghapus, dan mendapatkan daftar buku.

## Base URL
```
http://localhost:{port}/books
```

## Endpoints

### 1. Tambah Buku
**Endpoint:**
```
POST /books
```
**Body Request:**
```json
{
    "name": "Nama Buku",
    "year": 2024,
    "author": "Penulis Buku",
    "summary": "Ringkasan Buku",
    "publisher": "Penerbit",
    "pageCount": 100,
    "readPage": 50,
    "reading": true
}
```
**Response:**
```json
{
    "status": "success",
    "message": "Buku berhasil ditambahkan",
    "data": {
        "bookId": "string"
    }
}
```

### 2. Dapatkan Semua Buku
**Endpoint:**
```
GET /books
```
**Response:**
```json
{
    "status": "success",
    "data": {
        "books": [
            {
                "id": "string",
                "name": "Nama Buku",
                "publisher": "Penerbit"
            }
        ]
    }
}
```

### 3. Dapatkan Detail Buku
**Endpoint:**
```
GET /books/{bookId}
```
**Response:**
```json
{
    "status": "success",
    "data": {
        "book": {
            "id": "string",
            "name": "Nama Buku",
            "year": 2024,
            "author": "Penulis Buku",
            "summary": "Ringkasan Buku",
            "publisher": "Penerbit",
            "pageCount": 100,
            "readPage": 50,
            "finished": false,
            "reading": true,
            "insertedAt": "timestamp",
            "updatedAt": "timestamp"
        }
    }
}
```

### 4. Perbarui Buku
**Endpoint:**
```
PUT /books/{bookId}
```
**Body Request:**
```json
{
    "name": "Nama Buku Diperbarui",
    "year": 2025,
    "author": "Penulis Buku Diperbarui",
    "summary": "Ringkasan Buku Diperbarui",
    "publisher": "Penerbit Diperbarui",
    "pageCount": 150,
    "readPage": 100,
    "reading": false
}
```
**Response:**
```json
{
    "status": "success",
    "message": "Buku berhasil diperbarui"
}
```

### 5. Hapus Buku
**Endpoint:**
```
DELETE /books/{bookId}
```
**Response:**
```json
{
    "status": "success",
    "message": "Buku berhasil dihapus"
}
```

## Query Parameters
- `?reading=1` : Mendapatkan buku yang sedang dibaca.
- `?reading=0` : Mendapatkan buku yang tidak sedang dibaca.
- `?finished=1` : Mendapatkan buku yang telah selesai dibaca.
- `?finished=0` : Mendapatkan buku yang belum selesai dibaca.
- `?name=Dicoding` : Mencari buku berdasarkan nama.

## Error Handling
- `400 Bad Request`: Kesalahan dalam permintaan, seperti `readPage` lebih besar dari `pageCount`.
- `404 Not Found`: Buku tidak ditemukan.
- `500 Internal Server Error`: Kesalahan pada server.

---

Dokumentasi ini berdasarkan koleksi Postman yang diunggah dan dapat digunakan sebagai referensi dalam pengembangan atau pengujian API.

