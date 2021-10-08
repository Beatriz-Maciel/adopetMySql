create database AdoPet;
use adopet;

select * from vacina;
create table cliente (
id int not null auto_increment,
cpf varchar (11) not null unique,
nome_completo varchar (50) not null ,
telefone varchar (11) not null,
data_de_nascimento date not null ,
email varchar (30) not null unique ,
primary key (id),
fk_endereco int
);

create table endereco(
id int not null auto_increment,
cep varchar (8) not null ,
bairro varchar (50) not null,
logradouro varchar(50) not null,
numero int not null,
complemento varchar(50),
primary key (id)
);





create table  animal (
id int not null auto_increment,
nome varchar (50),
porte_animal char (20),
data_nascimento varchar (20),
primary key (id),
fk_cliente int,
fk_tipo_animal int,  
fk_sexo_animal int,
fk_vacina int

 );
 
 
create table sexo_animal(
id int not null auto_increment,
sexo varchar (30) not null unique,
primary key (id)
);


create table tipo_animal (
id int not null auto_increment,
tipo_animal  varchar (30) unique,
primary key (id)
);

create table vacina (
id int not null auto_increment,
primary key (id),
Tipo_vacina varchar (30),
data_de_vacincao date,
fk_animal int
);




create table acao (
id int not null auto_increment,
nome_acao varchar  (50) unique,
primary key (id)
);

create table historico_acao (
id int not null auto_increment ,
data_hora datetime not null,
primary key (id),
fk_acao int,
fk_cliente int,
fk_animal int
);
