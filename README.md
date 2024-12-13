* Hibernate-App, OneToMany
* Работа с транзакциями

```postgresql
CREATE TABLE Person (
    id int PRIMARY KEY GENERATED ALWAYS AS IDENTITY,
    name varchar(100) NOT NULL,
    age int CHECK (age < 100)
);

CREATE TABLE Item (
    id int PRIMARY KEY GENERATED ALWAYS AS IDENTITY,
    person_id int REFERENCES Person(id) ON DELETE SET NULL,
    item_name varchar(100) NOT NULL
);
```