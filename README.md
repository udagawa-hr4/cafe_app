# README


## users

| Column             | Type        | Option                   |
|--------------------|-------------|--------------------------|
| email              | string      | null:false, unique: true |
| encrypted_password | string      | null:false               |

### Association

- has_many :posts
- has_many :reviews
- has_one :profiles

## posts

| Column | Type       | Option                       |
|--------|------------|------------------------------|
| title  | string     | null:false                   |
| text   | text       |                              |
| user   | references | null:false,foreign_key: true |


### Association
- belongs_to :user
- has_many :reviews


## profiles

| Column             | Type        | Option                       |
|--------------------|-------------|------------------------------|
| nickname           | string      | null:false                   |
| first_name         | string      | null:false                   |
| family_name        | string      | null:false                   |
| phone_number       | integer     | null:false                   |
| birthday           | date        | null:false                   |
| introduction       | string      |                              |
| user               | references  | null:false,foreign_key: true |

### Association

- belongs_to :user