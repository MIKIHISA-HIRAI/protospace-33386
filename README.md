# テーブル設計

## users テーブル

| Colum      | Type   | Options     | 
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association
- has_many : prototypes
- has_many : comments

## prototypes テーブル

| Colum      | Type       | Options     | 
| ---------- | ---------- | ----------- |
| title      | String     | null: false |
| catch_copy | text       | null: false |
| concept    | text       | null: false |
| user       | references |             |


### Association
- belongs_to : users
- has_many   : comments

## comments テーブル

| Column    | Type       |
| --------- | ---------- |
| text      | text       |
| user      | references |
| prototype | references |


### Association
- belongs_to :prototypes
- belongs_to :users