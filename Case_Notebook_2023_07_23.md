## 00:21

#### Tìm kiếm nhân chứng thứ hai

Theo manh mối từ máy quay an ninh ta biết được nguười đó tên là **Annabel** sống ở đâu đó trên đường **Franklin Ave**

```sql
select * from person
where  name like "%Annabel%" and address_street_name = "Franklin Ave"
```

Result

| id    | name           | license_id | address_number | address_street_name | ssn       |
|-------|----------------|------------|----------------|---------------------|-----------|
| 16371 | Annabel Miller | 490173     | 103            | Franklin Ave        | 318771143 |

##### Tìm kiếm thông tin bằng lái xe có license_id = 490173

| id     | age | height | eye_color | hair_color | gender | plate_number | car_make | car_model |
|--------|-----|--------|-----------|------------|--------|--------------|----------|-----------|
| 490173 | 35  | 65     | green     | brown      | female | 23AM98       | Toyota   | Yaris     |

##### Tìm kiếm thông tin thu nhập có ssn = 318771143

Result: Rỗng

##### Tìm kiếm thông tin facebook

Result: Rỗng

##### Tìm kiếm thông tin phỏng vấn

Result: 



##### Tìm kiếm thông tin get_fit_now

Result: Rỗng