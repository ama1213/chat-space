## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :groops  through:  :groops_users
- has_many :groops_users
- has_many :messeges

## groopsテーブル
|Column|Type|Options|
|------|----|-------|
|title|text|null: false|
|text|text|null: false|
|users_id|integer|null: false, foreign_key: true|
### Association
- has_many :users  through:  :groops_users
- has_many :groops_users
- has_many :messeges

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|users_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :groups
- belongs_to :users

## messegesテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|text|null: false|
|users_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :users
- belongs_to :groops
