# Design DB
## Ruby version
2.3.1

## Users table
| columns   | type    | options                                    |
|-----------|---------|--------------------------------------------|
| name      | string  | index: true, null: false, unique: true     |

## Association
* has_many :groups_users
* has_many :groups, through :groups_users
* has_many :messages


## messages table
| column     | type     | options                                    |
|------------|----------|--------------------------------------------|
| body       | text     |                                            |
| image      | string   |                                            |
| group_id   | integer  | index: true, null: false, foreign_key:true |
| user_id    | integer  | index: true, null: false, foreign_key:true |

### Association
* belongs_to :user
* belongs_to :group


## groups table
| columns  | type    | options                                    |
|----------|---------|--------------------------------------------|
| name     | string  | null: false, unique: true                  |

### Association
* has_many :users
* has_many :groups_users
* has_many :messages, through groups_users


## groups_users table
| columns   | type    | options                                    |
|-----------|---------|--------------------------------------------|
| user_id   | integer | index: true, null: false, foreign_key:true |
| group_id  | integer | index: true, null: false, foreign_key:true |

### Association
* belongs_to :user
* belongs_to :group
