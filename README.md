# Design DB
## Ruby version
2.3.1

## Users table
| columns   | type    |                                        |
|-----------|---------|----------------------------------------|
| name      | string  | index: true, nill: false, unique: true |
| group_id  | integer | index: true, nill: false               |

### Association
has_many :group
belongs_to :group


## messages table
| column     | type     |                  |
|------------|----------|------------------|
| body       | text     |                  |
| image      | string   |                  |
| group_id   | integer  |                  |
| user_id    | integer  | foreign_key:true |
| timestamps | datetime |                  |

### Association
has_many :user
belongs_to :group
belongs_to :user


## groups table
| columns  | type    |                           |
|----------|---------|---------------------------|
| name     | string  | nill: false, unique: true |
| group_id | integer | index: true, nill: false  |

### Association
belongs_to :group


## groups_users table
| columns   | type    |                                        |
|-----------|---------|----------------------------------------|
| user_id | integer | index: true, nill: false, unique: true |
| group_id  | integer | nill: false                            |

### Association
* belongs_to :user
* belongs_to :group
