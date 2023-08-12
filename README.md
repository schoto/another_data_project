```
DROP SCHEMA IF EXISTS library_management;
CREATE SCHEMA IF NOT EXISTS library_management;

DROP TABLE IF EXISTS library_management.user_login;
CREATE TABLE IF NOT EXISTS library_management.user_login (
	user_id TEXT PRIMARY KEY,
    user_password TEXT,
    first_name TEXT,
	last_name TEXT,
	sign_up_on DATE,
	email_id TEXT
);
```
