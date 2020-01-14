# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|null: false|
### Association
- has_many :messages
- has_many :groups_users
- has_many :users, through groups_users

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|user_name|string|null: false|
### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: :groups_users

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|groups|references|null: false, foreign_key: true|
|users|references|null: false, foreign_key: true|
### Association
- belongs_to :groups
- belongs_to :users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|string||
|tweets|string||
|users_id|string|null: false, foreign_key: true|
|groups_id|string|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user
