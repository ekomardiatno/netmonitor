# Status Response
```text
OK | BAD_REQUEST | NOT FOUND | UNAUTHORIZED | EXPIRED
```
---
## **POST Login**
```javascript
{
  method: 'POST',
  body: {
    username: STRING,
    password: STRING
  },
  response: {
    status_string: 'OK',
    message: STRING,
    data: {
      user: {
        user_id: STRING,
        user_group_id: ARRAY,
        slug: STRING,
        firstname: STRING,
        lastname: STRING,
        email: STRING,
        image: URL,
      },
      token_key: STRING
    }
  }
}
```
---
## **GET Daftar Barang**
```javascript
{
  method: 'GET',
  header: {
    'Token-Key': STRING
  },
  params: {
    nama_barang: STRING,
    client_id: STRING,
    tahun: STRING,
    kondisi: STRING,
    page: STRING,
    limit: STRING
  },
  response: {
    status_string: 'OK',
    message: STRING
    data: [
      {
        inventaris_id: STRING,
        nama_barang: STRING,
        harga: STRING,
        no_urut: STRING,
        nama_client: STRING,
        kondisi: STRING,
      }
    ]
  }
}
```
---
## **GET Detail Barang**
```javascript
{
  method: 'GET',
  header: {
    'Token-Key': STRING
  },
  params: {
    inventaris_id: STRING
  },
  response: {
    status_string: 'OK',
    message: STRING,
    data: {
      inventaris_id: STRING,
      no_urut: STRING,
      nama_barang: STRING,
      harga: STRING,
      client_id: STRING,
      kondisi: STRING,
      tahun_anggaran: STRING,
      kode_barang: STRING,
      volume: STRING,
      satuan: STRING,
      merek_type: STRING,
      bahan: STRING,
      no_kontrak: STRING,
      tanggal_kontrak: STRING_DATE,
      nama_penyedia: STRING,
      images: ARRAY_STRING,
      images_thumb: ARRAY_URL
    }
  }
}
```
---
## **PUT Detail Barang**
```javascript
{
  method: 'PUT',
  header: {
    'Content-Type': 'application/json',
    'Token-Key': STRING
  },
  params: {
    inventaris_id: STRING
  },
  body: {
    client_id: STRING,
    kondisi: STRING,
    old_images: ARRAY_STRING,
    deleted_images: ARRAY_STRING,
    new_images: ARRAY_BASE64
  },
  response: {
    status_string: 'OK'
    message: STRING
  }
}
```
---
## **GET Daftar Klien**
```javascript
{
  method: 'GET',
  header: {
    'Token-Key': STRING
  },
  params: {
    nama_client: STRING,
    page: STRING,
    limit: STRING
  },
  response: {
    status_string: 'OK',
    message: STRING,
    data: [
      {
        title: STRING (nama_client),
        id: STRING (client_id)
      }
    ]
  }
}
```