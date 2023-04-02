# テーブル設計

## usersテーブル

|column             |Type   |Options              |
|-------------------|-------|---------------------|
|email              |string |not null, ユニーク制約|
|encrypted_password |string |not null             |
|name               |string |not null             |
|profile            |text   |not null             |
|occupation         |text   |not null             |
|position           |text   |not null             |

- has_many :prototypes
- has_many :comments


## prototypesテーブル

|column      |Type      |Options          |
|------------|----------|-----------------|
|title       |string    |not null         |
|catch_copy  |string    |not null         |
|concept     |string    |not null         |
|user        |references|not null, 外部キー|

- belongs_to :user
- has_many :comments


## commentsテーブル

|column      |Type      |Options          |
|------------|----------|-----------------|
|content     |string    |not null         |
|prototype   |references|not null, 外部キー|
|user        |references|not null, 外部キー|

- belongs_to :user
- belongs_to :prototype