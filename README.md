<!-- テーブル設計 -->

<!-- users table -->

|column              |   type       |     options             |
|————----------------|————----------|-------------------------|
|email               |string        |null: false, unique: true|
|encrypted_password  |string        |null: false              |
|name                |string        |null: false              |
|profile             |text          |null: false              |
|occupation          |text          |null: false              |
|position            |text          |null: false              |

- has_many :prototypes
- has_many :comments


<!-- prototypes table -->

|column             |type              |options               |
|————---------|————----------|--------------------------------|
|title        |string        |null: false                     |
|catch_copy   |text          |null: false                     |
|concept      |text          |null: false                     |
|user         |references    |null: false, foreign_key: true  |

- has_many :comments
- belongs_to :user


<!-- comments table -->


|column       |type          |options                         |
|————---------|————----------|--------------------------------|
|content      |text          |null: false                     |
|phototype    |references    |null: false, foreign_key:true   |
|user         |references    |null: false, foreign_key: true  | 

- belongs_to :user
- belongs_to :prototype