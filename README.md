# README


## usersテーブル

|Column |type |Options |
|-------|-----|--------|
| name   | string | index: true, null: false, unique: true |
| email   | string | null: false, unipue: true              |
| password  | string | null: false |

### Association
- has_many :groups, through: :group_users
- has_many :group_users
- has_many :massages


## groupテーブル

|Column |type |Options |
|-------|-----|--------|
| name | string | index: true, null: false, unipue: true |

### Association
- has_many :users, through: :group_users
- has_many :group_users
- has_many :messages


## messagesテーブル

|Column |type |Options |
|-------|-----|--------|
| body     | text    | null: false |
| image    | string  |  |
| group | integer | foreign_key: true |
| user  | integer | foreign_key: true |

### Association
- belongs_to :user
- belongs_to :group


## group_usersテーブル

|Column |type |Options |
|-------|-----|--------|
| user_id | integer| null: false, foreign_key: true|
| group_id| integer| null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user




This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
