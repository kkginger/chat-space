# DB設計


## usersテーブル

|Column |type |Options |
|-------|-----|--------|
| name   | string | index: true, null: false, unique: true |
| email   | string | null: false, unipue: true              |
| password  | string | null: false |

### Association
- has_many :groups, through: :groups_users
- has_many :groups_users
- has_many :massages


## groupsテーブル

|Column |type |Options |
|-------|-----|--------|
| name | string | null: false, unipue: true |

### Association
- has_many :users, through: :groups_users
- has_many :groups_users
- has_many :messages


## messagesテーブル

|Column |type |Options |
|-------|-----|--------|
| body     | text    |  |
| image    | string  |  |
| group | integer | foreign_key: true |
| user  | integer | foreign_key: true |

### Association
- belongs_to :user
- belongs_to :group


## groups_usersテーブル

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
