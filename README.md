# Design DB
## Ruby version
2.3.1

## Users table
| columns  | type    |                                        |
|----------|---------|----------------------------------------|
| name     | string  | index: true, nill: false, unique: true |
| group_id | integer | index: true, nill: false               |

## messages table
| column     | type     |
|------------|----------|
| body       | text     |
| image      | string   |
| group_id   | integer  |
| member_id    | integer  |
| timestamps | datetime |

## groups table
| columns | type   |
|---------|--------|
| member  | string |

## 中間テーブル
| columns   | type    |                                        |
|-----------|---------|----------------------------------------|
| member_id | integer | index: true, nill: false, unique: true |
| group_id  | integer | nill: false                            |

## Association
* has_many :members_tag
* has_many :groups, through: members_tag
* has_many :messages_tag
* has_many :members, through: memssages_tag
* belongs_to :member
* belongs_to :group
