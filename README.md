# Design DB
## Ruby version
2.3.1

## Members table
| columns   | type    |                                        |
|-----------|---------|----------------------------------------|
| name      | string  | index: true, nill: false, unique: true |
| member_id | integer | index: true, nill: false, unique: true |
| group_id  | integer | index: true, nill: false               |

## messages table
| column     | type     |
|------------|----------|
| body       | text     |
| image      | string   |
| group_id   | integer  |
| member_id    | integer  |
| timestamps | datetime |

## groups table
| columns  | type    |                           |
|----------|---------|---------------------------|
| name     | string  | nill: false, unique: true |
| group_id | integer | index: true, nill: false  |

## chat table
| columns   | type    |                                        |
|-----------|---------|----------------------------------------|
| member_id | integer | index: true, nill: false, unique: true |
| group_id  | integer | nill: false                            |

## Association
* has_many :chat
* has_many :groups, through: chat
* has_many :members, through: chat
* belongs_to :member
* belongs_to :group
