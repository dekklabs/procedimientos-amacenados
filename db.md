# Practicas

```
use MiWeb;

create table if not exists user
(
	id int(8) primary key auto_increment,
    name varchar(50) not null,
    lastname varchar(80) null,
    email varchar(150) not null,
    password varchar(100) not null,
    avatar text null,
    cover text null,
    description text null,
    website varchar(150) null
);

select * from user;

-- Es necesario agregar delimiter antes de iniciar un procedimiento almacenado y al finalizar agregar $$
DELIMITER $$
CREATE PROCEDURE insertUser(IN _name varchar(50), _email varchar(150), _password varchar(100))
BEGIN
	INSERT INTO user(name, email, password)
		VALUES(_name, _email, _password);
END $$

call insertUser('Dekk', 'dekk@gmail.com', '123123');
```
