Hibernate-App, OneToMany
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

```postgresql
INSERT INTO Person(name, age) VALUES('Tom1', 35);
INSERT INTO Person(name, age) VALUES('Tom2', 45);
INSERT INTO Person(name, age) VALUES('Tom3', 55);

INSERT INTO Item(person_id, item_name) VALUES(1, 'Book');
INSERT INTO Item(person_id, item_name) VALUES(1, 'AirPods');
INSERT INTO Item(person_id, item_name) VALUES(2, 'Iphone');
INSERT INTO Item(person_id, item_name) VALUES(3, 'Kindle');
INSERT INTO Item(person_id, item_name) VALUES(3, 'TV');
INSERT INTO Item(person_id, item_name) VALUES(3, 'PlayStation');
```