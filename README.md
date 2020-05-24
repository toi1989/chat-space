# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

##messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null:false|
|image|string|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
- belongs_to :groups
- belongs_to :users
- add_index :body

##usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
|email|string|null: false|
- has_many :groups, through: :groups_users
- has_many :message
- add_index :name

##groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group|text|null: false|
|user_id|integer|null: false, foreign_key: true|
- has_many :users, through: :groups_users
- add_index :

##groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
- belongs_to :groups
- belongs_to :users

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

