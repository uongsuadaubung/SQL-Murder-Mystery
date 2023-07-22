# SQL Murder Mystery



En:  
There's been a Murder in SQL City! The SQL Murder Mystery is designed to be both a self-directed lesson to learn SQL concepts and commands and a fun game for experienced SQL users to solve an intriguing crime.

Vi:  
Đã có một vụ giết người ở Thành phố SQL! SQL Murder Mystery được thiết kế vừa là một bài học tự định hướng để tìm hiểu các khái niệm và lệnh SQL, vừa là một trò chơi thú vị dành cho những người dùng SQL có kinh nghiệm để giải quyết một tội ác hấp dẫn.

### New to SQL?

En:  
This exercise is meant more as a way to practice SQL skills than a full tutorial. If you've never used SQL at all, [try the walkthrough](https://mystery.knightlab.com/walkthrough.html). If you really want to learn a lot about SQL, you may prefer a complete tutorial like [Select Star SQL](https://selectstarsql.com/).

If you're comfortable with SQL, you can dive in below!

Vi:

### Experienced SQL sleuths start here

En:  
A crime has taken place and the detective needs your help. The detective gave you the crime scene report, but you somehow lost it. You vaguely remember that the crime was a **murder** that occurred sometime on **Jan.15, 2018** and that it took place in **SQL City**. Start by retrieving the corresponding crime scene report from the police department’s database.

Vi:  
Một vụ án đã xảy ra và thám tử cần sự giúp đỡ của bạn. Thám tử đã cung cấp cho bạn bản báo cáo hiện trường tội phạm, nhưng bạn đã mất nó mất rồi. Bạn hồi tưởng lại rằng vụ án là một vụ **giết người** xảy ra vào ngày **15 tháng 1 năm 2018** và đã diễn ra ở **Thành phố SQL**. Hãy bắt đầu bằng cách lấy lại báo cáo hiện trường tương ứng từ cơ sở dữ liệu của cảnh sát.

### Exploring the Database Structure
Experienced SQL users can often use database queries to infer the structure of a database. But each database system has different ways of managing this information. The SQL Murder Mystery is built using SQLite. Use this SQL command to find the tables in the Murder Mystery database.

#### Run this query to find the names of the tables in this database.

This command is specific to SQLite. For other databases, you'll have to learn their specific syntax.

```sql
SELECT name
  FROM sqlite_master
  where type = 'table'
```
result

| Tên bảng               | Mô tả                                 |
|------------------------|---------------------------------------|
| crime_scene_report     | Báo cáo hiện trường tội phạm          |
| drivers_license        | Thông tin giấy phép lái xe            |
| facebook_event_checkin | Thông tin check-in sự kiện Facebook   |
| interview              | Thông tin cuộc phỏng vấn lấy lời khai |
| get_fit_now_member     | Thông tin thành viên Get Fit Now      |
| get_fit_now_check_in   | Thông tin check-in Get Fit Now        |
| solution               | Thông tin giải pháp                   |
| income                 | Thông tin thu nhập                    |
| person                 | Thông tin cá nhân                     |


Besides knowing the table names, you need to know how each table is structured. The way this works is also dependent upon which database technology you use. Here's how you do it with SQLite.

#### Run this query to find the structure of the `crime_scene_report` table
Change the value of 'name' to see the structure of the other tables you learned about with the previous query.

```sql
SELECT sql 
  FROM sqlite_master
 where name = 'crime_scene_report'
```

Full [diagram](https://dbdiagram.io/d/64b8f13302bd1c4a5e6516ec)