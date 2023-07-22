
## 23:05

Dựa vào thông tin được cung cấp từ đầu vào ngày 15 tháng 1 năm 2018 đã xảy ra một vụ giết người ở Thành phố SQL,
ta sẽ truy cập vào crime_scene_report để lấy thông tin về vụ án.

```sql
select * from crime_scene_report
  where city = "SQL City" and 
        type = "murder" and 
        date = 20180115
```

Result

| date     | type   | description                                                                                                                                                                               | city     |
|----------|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| 20180115 | murder | Security footage shows that there were 2 witnesses. The first witness lives at the last house on "Northwestern Dr". The second witness, named Annabel, lives somewhere on "Franklin Ave". | SQL City |

| date     | type   | mô tả                                                                                                                                                                                                               | city     |
|----------|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| 20180115 | murder | Các hình ảnh an ninh cho thấy có 2 nhân chứng. Nhân chứng đầu tiên sống tại căn nhà cuối cùng trên đường "Northwestern Dr". Nhân chứng thứ hai, có tên là Annabel, sống ở một nơi nào đó trên đường "Franklin Ave". | SQL City |                                                                                                                                                                                                                         |      |


Dựa vào những thông tin có đuợc thì ta sẽ đi điều tra hai nhân chứng dựa theo mô tả.

#### Tìm nhân chứng đầu tiên đầu tiên

```sql
select * from person
where address_street_name = "Northwestern Dr" and
      address_number in (select max(address_number) from person)
```

Result 

| id    | name           | license_id | address_number | address_street_name | ssn       |
|-------|----------------|------------|----------------|---------------------|-----------|
| 14887 | Morty Schapiro | 118009     | 4919           | Northwestern Dr     | 111564949 |

##### Tìm kiếm thông tin bằng lái xe có license_id = 118009

| id     | age | height | eye_color | hair_color | gender | plate_number | car_make      | car_model |
|--------|-----|--------|-----------|------------|--------|--------------|---------------|-----------|
| 118009 | 64  | 84     | blue      | white      | male   | 00NU00       | Mercedes-Benz | E-Class   |

##### Tìm kiếm thông tin thu nhập có ssn = 111564949

Result: rỗng


##### Tìm kiếm facebook

Result: rỗng

##### Tìm kiếm Lời khai

| person_id | transcript                                                                                                                                                                                                                      |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 14887     | I heard a gunshot and then saw a man run out. He had a "Get Fit Now Gym" bag. The membership number on the bag started with "48Z". Only gold members have those bags. The man got into a car with a plate that included "H42W". |

| person_id | lời khai                                                                                                                                                                                                                                                                     |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 14887     | Tôi nghe thấy tiếng súng và sau đó nhìn thấy một người đàn ông chạy ra ngoài. Anh ta có một chiếc túi "Get Fit Now Gym". Số thành viên trên túi bắt đầu bằng "48Z". Chỉ có các thành viên vàng mới có túi như vậy. Người đàn ông lên xe ô tô có biển số bắt đầu bằng "H42W". |





##### tìm kiếm thành viên getfitnow

Result: rỗng

Kết luận sơ bộ thì nhân chứng đầu tiên có tên là 
Morty Schapiro, tuổi 64, cao 84, mắt xanh, tóc bạc, 
không có thu nhập có vẻ như đây là người thất nghiệp -.-
không có thông tin gì hữu ích