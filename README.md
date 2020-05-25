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
|body|text||
|image|string||
|user|references|null:false, foreign_key:true|
|group|references|null:false, foreign_key:true|

###Assosiation
- belongs_to :group
- belongs_to :user

##usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|index:true, null:false,unique:true|
|email|string|null:false,unique:true|
|password|string|null,false|

###Assosiation
- has_many :groups,through:：groups_users
- has_many :groups_users
- has_many :messages

##groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false,unique:true|

###Assosiation
- has_many :users, through: :groups_users
- has_many :messages
- has_many :groups_users

##groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

###Assosiation
- belongs_to :group
- belongs_to :user

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

