# Technical Test - Backend Engineer

In this test, the candidate should craft a **Customer** **RESTFul** API Service within the allotted time.

Upload to private repository in github.com and invite these persons as a collaborators:

- UserID github : **ariefpsn**

### RESTFul Specifications

1. The API must comply **RESTFul** guideline
2. Free to improvise or create your own API response object
3. Have to use the given endpoints and follow the requirements
4. Create API use **Python** or **PHP** with Framework **Laravel**
5. Store data use **MariaDB** or **MySQL** database
6. Create script to **migration database**.
7. Applied **request validation**
8. Provide **unit test** on your project
9. Provide the proper **README**
10. Running in **docker** container
11. Adding extras like (but not limited to) fancy architectural and elegant **error handling** **&** **logging**

## Customer Store Object

| Column       | Type     |
|--------------|----------|
| id           | integer  |
| title        | string   |
| name         | string   |
| gender       | string   |
| phone_number | string   |
| image        | string   |
| email        | string   |
| created_at   | datetime |
| updated_at   | datetime |

### Example Object:

```json
{
  "id": 1,
  "title": "Mr",
  "name": "Adrien Philippe",
  "gender": "M",
  "phone_number": "085222334445",
  "image": "https://img.freepik.com/premium-vector/man-avatar-profile-round-icon_24640-14044.jpg",
  "email": "adrien.philippe@gmail.com",
  "created_at": "2020-08-01 10:56:31",
  "updated_at": "2020-08-08 09:30:23"
}
```

## Address Store Object

| Column      | Type     |
|-------------|----------|
| id          | integer  |
| customer_id | integer  |
| address     | string   |
| district    | string   |
| city        | string   |
| province    | string   |
| postal_code | integer  |
| created_at  | datetime |
| updated_at  | datetime |

### Example Object:

```json
{
  "id": 1,
  "customer_id": 1,
  "address": "Kawasan Karyadeka Pancamurni Blok A Kav. 3",
  "district": "Cikarang Selatan",
  "city": "Bekasi",
  "province": "Jawa Barat",
  "postal_code": 17530,
  "created_at": "2020-08-01 10:56:31",
  "updated_at": "2020-08-08 09:30:23"
}
```

### The API must handle the following endpoints:

## 1. List Of Customer

| Name        | Detail                                                                                                 |
|-------------|--------------------------------------------------------------------------------------------------------|
| endpoint    | /customer                                                                                              |
| method      | GET                                                                                                    |
| Description | return a list of the customer in JSON format, the customer must be sorted by rating and alphabetically |
| Extra       | You can applied some improvisation on this request and response                                        |

## 2. Detail Of Customer

<table>
<tr>
<th>Name</th>
<th>Detail</th>
</tr>
<tr>
<td>Endpoint</td>
<td>/customer/:id</td>
</tr>
<tr>
<td>method</td>
<td>GET</td>
</tr>
<tr>
<td>Description</td>
<td>
Description	return the details of a customer and address in JSON format
<br>
example:

```json
{
  "id": 1,
  "title": "Mr",
  "name": "Adrien Philippe",
  "gender": "M",
  "phone_number": "085222334445",
  "image": "https://img.freepik.com/premium-vector/man-avatar-profile-round-icon_24640-14044.jpg",
  "email": "adrien.philippe@gmail.com",
  "address": [
    {
      "id": 1,
      "address": "Kawasan Karyadeka Pancamurni Blok A Kav. 3",
      "district": "Cikarang Selatan",
      "city": "Bekasi",
      "province": "Jawa Barat",
      "postal_code": 17530,
      "created_at": "2020-08-01 10:56:31",
      "updated_at": "2020-08-08 09:30:23"
    },
    {
      "id": 2,
      "address": "Kantor Taman A9 Unit C3-C4 Lot. 8/9 Jl. DR. Ide Anak Agung Gde Agung No. 9",
      "district": "Setiabudi",
      "city": "Jakarta Selatan",
      "province": "Daerah Khusus Ibukota Jakarta",
      "postal_code": "12950",
      "created_at": "2020-08-01 10:56:31",
      "updated_at": "2020-08-08 09:30:23"
    }
  ],
  "created_at": "2020-08-01 10:56:31",
  "updated_at": "2020-08-08 09:30:23"
}
```

</td>
</tr>
</table>

## 3. Add New Customer

<table>
<tr>
<th>Name</th>
<th>Detail</th>
</tr>
<tr>
<td>Endpoint</td>
<td>/customer</td>
</tr>
<tr>
<td>method</td>
<td>POST</td>
</tr>
<tr>
<td>Description</td>
<td>
Add a customer to the customers list, the data will be sent as a JSON in the request body :

```json
{
  "title": "Mr",
  "name": "Adrien Philippe",
  "gender": "M",
  "phone_number": "085222334445",
  "image": "https://img.freepik.com/premium-vector/man-avatar-profile-round-icon_24640-14044.jpg",
  "email": "adrien.philippe@gmail.com"
}
```

</td>
</tr>
</table>

## 4. Add New Address

<table>
<tr>
<th>Name</th>
<th>Detail</th>
</tr>
<tr>
<td>Endpoint</td>
<td>/address</td>
</tr>
<tr>
<td>method</td>
<td>POST</td>
</tr>
<tr>
<td>Description</td>
<td>
Add a address to the address list, the data will be sent as a JSON in the request body :

```json
{
  "address": "Kawasan Karyadeka Pancamurni Blok A Kav. 3",
  "district": "Cikarang Selatan",
  "city": "Bekasi",
  "province": "Jawa Barat",
  "postal_code": 17530
}
```

</td>
</tr>
</table>

## 5. Update Customer

<table>
<tr>
<th>Name</th>
<th>Detail</th>
</tr>
<tr>
<td>Endpoint</td>
<td>/customer/:id</td>
</tr>
<tr>
<td>method</td>
<td>PATCH</td>
</tr>
<tr>
<td>Description</td>
<td>
Update a customer to the customers list, the data will be sent as a JSON in the request body :

```json
{
  "title": "Mr",
  "name": "Adrien Philippe",
  "gender": "M",
  "phone_number": "085222334445",
  "image": "https://img.freepik.com/premium-vector/man-avatar-profile-round-icon_24640-14044.jpg",
  "email": "adrien.philippe@gmail.com"
}
```

</td>
</tr>
</table>

## 6. Update Address

<table>
<tr>
<th>Name</th>
<th>Detail</th>
</tr>
<tr>
<td>Endpoint</td>
<td>/address/:id</td>
</tr>
<tr>
<td>method</td>
<td>PATCH</td>
</tr>
<tr>
<td>Description</td>
<td>
Update a address to the address list, the data will be sent as a JSON in the request body :

```json
{
  "address": "Kawasan Karyadeka Pancamurni Blok A Kav. 3",
  "district": "Cikarang Selatan",
  "city": "Bekasi",
  "province": "Jawa Barat",
  "postal_code": 17530
}
```

</td>
</tr>
</table>

## 7. Delete Customer

| Name        | Detail                                      |
|-------------|---------------------------------------------|
| Endpoint    | /customer/:id                               |
| method      | DELETE                                      |
| Description | delete a customer and address from database |

## 8. Delete Address

| Name        | Detail                         |
|-------------|--------------------------------|
| Endpoint    | /address/:id                   |
| method      | DELETE                         |
| Description | delete a address from database |