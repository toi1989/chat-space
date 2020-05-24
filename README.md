# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

##messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|index:true,null:false|
|image|string||
|user_id|integer|null:false, foreign_key:true|
|group_id|integer|null:false, foreign_key:true|
###Assosiation
- belongs_to :groups
- belongs_to :users

##usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|index:true, null:false,unique:true|
|email|string|null:false,unique:true|
|password|string|null,false|
###Assosiation
- has_many :groups,through:groups_users
- has_many :messages

##groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group|string|null: false,unique:true|
###Assosiation
- has_many :users, through: :groups_users

##groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
###Assosiation
- belongs_to :groups
- belongs_to :users

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

