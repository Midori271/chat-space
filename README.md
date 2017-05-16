# Design DB
## Ruby version
2.3.1

## Users table
| columns | type   |                                        |
|---------|--------|----------------------------------------|
| name    | string | index: true, nill: false, unique: true |
| mail    | string | null: false                            |

## messages table
| column   | type    |
|----------|---------|
| body     | text    |
| image    | string  |
| group_id | integer |
| user_id  | integer |

#＃ Association
* has_many :groups, through: members
* has_many :messages
* has_many :members
