# テーブル情報

## users テーブル

| Colum              | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
| encrypted_password | string | null: false |
| name               | text   | null: false |
| profile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| Colum      | Type       | Options     |
| ---------- | ---------- | ------------|
| title      | string     | null: false |
| catch_copy | text       | null: false |
| concept    | text       | null: false |
| user       | references | null: false |

### Association

- belongs_to :users
- has_many :comments

## comments テーブル

| Colum     | Type       | Options     |
| --------- | ---------- | ----------- |
| content   | text       | null: false |
| prototype | references | null: false |
| user      | references | null: false |

### Association

- belongs_to :users
- belongs_to :prototypes