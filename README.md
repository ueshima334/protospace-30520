# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| name       | string | null: false |
| email      | string | null: false |
| password   | string | null: false |
| profile    | string |             |
| occupation | string |             |
| position   | string |             |

- has_many :prototypes
- has_many :comments


## prototypes テーブル

| Column     | Type      | Options     |
| ---------- | --------- | ----------- |
| title      | string    | null: false |
| catch_copy | string    | null: false |
| concept    | string    | null: false |
| user       | reference | null: false,foreign_key: true |

- belongs_to :user
- has_many   :comments


## comments テーブル

| Column       | Type       | options                        |
| ------------ | ---------- | ------------------------------ |
| text         | string     | null: false                    |
| user         | references | null: false, foreign_key: true |
| prototype    | references | null: false, foreign_key: true |

- belongs_to :user
- belongs_to :prototype