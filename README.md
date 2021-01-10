# テーブル設計

## usersテーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| position   | text   | null: false |

### Association
- has_many :comments

## prototypesテーブル

| Column        | Type          | Options     |
| ------------- | ------------- | ----------- |
| title         | string        | null: false |
| catch_copy    | text          | null: false |
| concept       | text          | null: false |
| image         | ActiveStorage |             |
| user          | references    |             |

### Association
- has_many :comments

## commentsテーブル

| Column    | Type       | Options     |
| --------- | ---------- | ----------- |
| text      | string     | null: false |
| user      | references |             |
| prototype | references |             |

### Association
- belongs_to :users
- belongs_to :prototypes