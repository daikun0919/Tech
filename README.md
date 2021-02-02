# Tech Chat README

## userテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false|
|email|integer|null: false|

### Association
- has_many :messages
- has_many  :groups,  through:  :group_users
- has_many :group_users

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false|

### Association
- has_many :messages
- has_many  :users,  through:  :group_users
- has_many  :group_users

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user