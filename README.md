# Design DB
## Ruby version
2.3.1

## Users table
| columns | type   |                                        |
|---------|--------|----------------------------------------|
| name    | string | index: true, nill: false, unique: true |
| mail    | string | index: true, nill: false, unique: true |

## messages table
| column     | type     |
|------------|----------|
| body       | text     |
| image      | string   |
| group_id   | integer  |
| user_id    | integer  |
| timestamps | datetime |


## Association
* has_many :members_tag
* has_many :groups, through: members_tag
* has_many :messages_tag
* has_many :members, through: memssages_tag
