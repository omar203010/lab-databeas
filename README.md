create database store;

Create table countries(
    code int primary key auto_increment ,
name varchar(20) unique ,
continent_name varchar(20) not null
);

Create table users(
    id int primary key auto_increment ,
    fuul_name varchar(20),
    email varchar(20) unique,
    gender char(1) check ( gender='m' or gender='f'),
    data_of_birth varchar(15),
    country_code int,
    foreign key (country_code) references countries(code)

);

Create table orders(
    id int primary key auto_increment ,
    user_id int,
    status varchar(6) check (status='start' or status='finish'),
    foreign key (user_id) references users(id)
);


Create table products(
    id int primary key auto_increment ,
     name varchar(10) not null ,
     price int default  0,
     status varchar(10) check ( 'valid' or 'expired' )
);
Create table orders_products(
    order_id int,
    product_id int,
     quantity int default  0,
     foreign key (product_id) references products(id),
     foreign key (order_id) references orders(id)
);
insert  into countries(name, continent_name) values  ('omar','Asia');

insert  into users(gender,email) values  ('m','omar@gmail.com');
insert  into orders(user_id,status) values  (1,'start');



update  countries set  name='Ali' where code=1;
delete from  products where id=1;




<img src="Screenshot 2023-02-27 105907.png">























