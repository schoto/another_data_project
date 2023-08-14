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

DROP TABLE IF EXISTS library_management.publisher;
CREATE TABLE IF NOT EXISTS library_management.publisher (
	publisher_id TEXT PRIMARY KEY,
    publisher TEXT,
    distributor TEXT,
	releases_count INT,
	last_release DATE
);

DROP TABLE IF EXISTS library_management.author;
CREATE TABLE IF NOT EXISTS library_management.author (
	author_id TEXT PRIMARY KEY,
	first_name TEXT,
	last_name TEXT,
	publications_count INT
);

DROP TABLE IF EXISTS library_management.books;
CREATE TABLE IF NOT EXISTS library_management.books (
	book_id TEXT PRIMARY KEY,
    book_code TEXT,
    book_name TEXT,
    author_id TEXT REFERENCES library_management.author (author_id),
	publisher_id TEXT REFERENCES library_management.publisher (publisher_id),
    book_version TEXT,
    release_date DATE,
    available_from DATE,
    is_available BOOLEAN
);

DROP TABLE IF EXISTS library_management.staff;
CREATE TABLE IF NOT EXISTS library_management.staff (
	staff_id TEXT PRIMARY KEY,
    first_name TEXT,
	last_name TEXT,
    staff_role TEXT,
    start_date DATE,
    last_date DATE,
    is_active BOOLEAN,
    work_shift_start TIME,
	work_shift_end TIME
);

DROP TABLE IF EXISTS library_management.readers;
CREATE TABLE IF NOT EXISTS library_management.readers (
	reader_id TEXT PRIMARY KEY,
    first_name TEXT,
	last_name TEXT,
	registered_on DATE,
	books_issued_total INT,
	books_issued_current INT,
	is_issued BOOLEAN,
	last_issue_date DATE,
	total_fine FLOAT,
	current_fine FLOAT
);
```
