# テーブル設計

## users テーブル

| Column   | Type         | Options         |
| -------- | ------------ | --------------- |
| id       | SERIAL       | NOT NULL        |
| name     | VARCHAR(128) | NOT NULL        |
| email    | VARCHAR(128) | NOT NULL UNIQUE |
| password | VARCHAR(512) | NOT NULL        |

### Option
-PRIMARY KEY (id)

## rooms テーブル

| Column | Type         | Options  |
| ------ | ------------ | -------- |
| id     | SERIAL       | NOT NULL |
| name   | VARCHAR(128) | NOT NULL |

### Option
- PRIMARY KEY (id)

## room_users テーブル

| Column  | Type   | Options  |
| ------- | ------ | -------- |
| id      | SERIAL | NOT NULL |
| user_id | INT    | NOT NULL |
| room_id | INT    | NOT NULL |

### Option
- PRIMARY KEY (id)
- FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
- FOREIGN LEY (room_id) REFERENCES rooms(id) ON DELETE CASCADE