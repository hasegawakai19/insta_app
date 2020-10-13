# insta DB設計

## usersテーブル
|Column|Type|Option|
|------|----|------|
|username|string|null: false|
|name|string|
|password|string|null: false|
|email|string|null: false|
### Association
- has_many :post
- has_many :coments
- has_many :favos
- has_many :#tags
- has_many :messages

## postsテーブル
|Column|Type|Option|
|------|----|------|
|text|text|
### Association
- belongs_to :user
- has_many :coments
- has_many :post_images
- has_many :favos

## post_imagesテーブル
|Column|Type|Option|
|------|----|------|
|product_id|references|null :false,foreign_key: true|
|image_url|string|null :false|

### Association
- belongs_to :posts

## #tagsテーブル
|Column|Type|Option|
|------|----|------|
|name|string|
### Association
- has_many :user
- has_many :post

## comentsテーブル
|Column|Type|Option|
|------|----|------|
|coment|text|

### Association
- belongs_to :post
- has_many :user