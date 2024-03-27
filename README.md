# Exam
-- 1 task
create table Students(
	id BIGINT primary key,
	name Varchar(50),
	birthday date,
	gruppa INT
);

create table Subject(
	id BIGINT primary key,
	name Varchar(50),
	description varchar(50),
	grade INT 
);

create table PaymentType(
	id BIGINT primary key,
	name varchar(50)
);

create table Payment(
	id bigint primary key,
	type_id bigint,
	amount int,
	student_id bigint,
	payment_date TIMESTAMP,
	FOREIGN KEY (type_id) REFERENCES PaymentType(id),
	FOREIGN KEY (student_id) REFERENCES Student(id)
);

create table mark(
	id bigint primary key,
	student_id bigint,
	subject_id bigint,
	mark int,
	FOREIGN KEY (student_id) REFERENCES student(id),
	FOREIGN KEY (subject_id) REFERENCES subject(id)
);

-- 2 task

insert into Students(name, gruppa) values('Oliver', 2);
insert into Students(name, gruppa) values('James', 2);
insert into Students(name, gruppa) values('Lucas', 2);
insert into Students(name, gruppa) values('Henry', 2);

insert into Students(name, gruppa) values('Jhon', 1);
insert into Students(name, gruppa) values('Chris', 1);
insert into Students(name, gruppa) values('Carl',1);

insert into Students(name, gruppa) values('Jacob', 3);
insert into Students(name, gruppa) values('Logan',3);

insert into Subject(name, grade) values('Art', 1);
insert into Subject(name, grade) values('music',1);

insert into Subject(name, grade) values('Geography',2);
insert into Subject(name, grade) values('history',2);

insert into Subject(name, grade) values('PE',3);
insert into Subject(name, grade) values('math',3);

insert into Subject(name, grade) values('Scientse',4);
insert into Subject(name, grade) values('IT',4);

insert into Subject(name, grade) values('art',5);
insert into Subject(name, grade) values('english',2);

insert into PaymentType(name) values('Daily');
insert into PaymentType(name) values('Monthly');
insert into PaymentType(name) values('Weekly');

INSERT INTO Payment (type_id, amount, student_id, payment_date) VALUES (2, 190, 1, '2024-01-01');
INSERT INTO Payment (type_id, amount, student_id, payment_date) VALUES (3, 260, 4, '2024-02-01');
INSERT INTO Payment (type_id, amount, student_id, payment_date) VALUES (2, 120, 7, '2024-01-01');
INSERT INTO Payment (type_id, amount, student_id, payment_date) VALUES (1, 58, 6, '2024-01-01');

INSERT INTO Mark (student_id, subject_id, mark) VALUES (2, 1, 8);
INSERT INTO Mark (student_id, subject_id, mark) VALUES (4, 2, 5);
INSERT INTO Mark (student_id, subject_id, mark) VALUES (5, 2, 9);
INSERT INTO Mark (student_id, subject_id, mark) VALUES (8, 3, 4);
INSERT INTO Mark (student_id, subject_id, mark) VALUES (9, 4, 9);

-- 3 task

ALTER TABLE Students MODIFY COLUMN birthday DATE NOT NULL;
ALTER TABLE Mark MODIFY COLUMN mark INT CHECK (mark BETWEEN 1 AND 10);
ALTER TABLE Subject MODIFY COLUMN grade INT CHECK (grade BETWEEN 1 AND 5);
ALTER TABLE PaymentType COLUMN unique_name UNIQUE (name);

-- 4 task

SELECT * FROM Students;
SELECT * FROM Students LIMIT 50;
SELECT name FROM Students;
SELECT DISTINCT amount FROM Payment;






