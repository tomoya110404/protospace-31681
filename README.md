# ProtoSpaceのER図

## users  テーブル

| column     |  type         |  options        |   
| --------   | --------      | --------------- |
| email      | string        | NOT NULL        |
| password   | string　　　　　| NOT NULL        |　
| profile    | string        | NOT NULL        |
| occupation | string        | NOT NULL        |
| position   | string        | NOT NULL        |

### Association

- has_many :prototypes
- has_many :comments

##　prototypes  テーブル

| column      |  type        |  options        |   
| --------    | --------     | --------------- |
| title       | string       |  NOT NULL       |
| catch_copy  | text　　      | NOT NULL        |
| concept     | text         | NOT NULL        |
| image       |              |                 |
| user        | references   |                 |
 
### Association

- belongs_to :users
- has_many   :comments

##  comments テーブル

| column       |  type       |  options        |   
| --------     | --------    | --------------- |
| text         | text        | NOT NULL        |
| user         | references　|                 |　
| prototype    | references  |                 |

### Association
belongs_to :users
belongs_to :prototypes