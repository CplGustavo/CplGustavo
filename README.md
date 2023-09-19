# --------ETAPA 1---------------


Atividade diagramas DER/MER
SLIDE 10 (NESTE EXERCÍCIO SERÁ OBSERVADO A IDENTIFICAÇÃO DOS ELEMENTOS DO DER (ENTIDADE/ATRIBUTOS/RELACIONAMENTO)
PETSHOP
![image](https://github.com/CplGustavo/CplGustavo/assets/144744164/d370486d-b3cc-44c2-9043-050bcb936d47)

PRODUTORA GAMES

![image](https://github.com/CplGustavo/CplGustavo/assets/144744164/b5c2e699-6278-45f3-95ce-f6bab12b7571)

# --------ETAPA 2---------------
 
SLIDE 19 (NESTE EXERCÍCIO SERÁ OBSERVADO A CARDINALIDADE ENTRE OS COMPONENTES APRESENTADOS, ALÉM DA IDENTIFICAÇÃO DOS ELEMENTOS DO DER).

BIBLIOTECA

![image](https://github.com/CplGustavo/CplGustavo/assets/144744164/cb9f872f-ce2f-427c-9e08-b4ecd23aec48)

LOCADORA

![image](https://github.com/CplGustavo/CplGustavo/assets/144744164/698d3a3e-d5ae-4a09-b8c7-d6a8f3198189)

SUPERMERCADO

![image](https://github.com/CplGustavo/CplGustavo/assets/144744164/916d939f-75b4-4572-8105-e69d721c8222)

VIDEOTECA

![image](https://github.com/CplGustavo/CplGustavo/assets/144744164/941124d7-1099-49b3-9cfd-139843197377)


# --------ETAPA 3---------------

 #  ALUNOS
Crie um banco de dados para armazenar dados de alunos. Um aluno deve ter RA, nome, data de nascimento, endereço e e-mail;


CREATE TABLE alunos (
  ra INT,
  nome VARCHAR(60),
  data_nasc DATE,
  endereco VARCHAR(100),
  email VARCHAR(30)
  );
  INSERT INTO alunos (ra, nome , data_nasc, endereco, email)
  VALUES (223, 'henrique', '2023-04-09', 'rua waldo', 'henrique@gmail.com')   
  
  INSERT INTO alunos (ra, nome , data_nasc, endereco, email)
  VALUES(222,'ronaldo', '2002-04-09', 'rua amelia', 'ronaldo@gmail.com')
  
  INSERT INTO alunos (ra, nome , data_nasc, endereco, email)
  VALUES (225, 'jonas', '2002-04-09', 'rua cristina', 'jonas@gmail.com')  
  
  INSERT INTO alunos (ra, nome , data_nasc, endereco, email)
  VALUES (226, 'leticia', '2003-04-09', 'rua donas', 'leticia@gmail.com')  
  
  INSERT INTO alunos (ra, nome , data_nasc, endereco, email)
  VALUES (227, 'gustavo', '2000-04-09', 'rua waldo', 'gustavoalberto@gmail.com')         
         
         
  SELECT * FROM alunos;


 
  
 #  COLABOLADORES

  2 — Crie um banco de dados para armazenar dados de colaboradores de uma empresa. Um colaborador deve ter um código de identificação, nome, CPF, cargo e salário;
CREATE DATABASE EmpresaDB;

USE EmpresaDB;

CREATE TABLE Colaboradores (
    CodigoIdentificacao INT PRIMARY KEY,
    Nome VARCHAR(255),
    CPF CHAR(11),
    Cargo VARCHAR(100),
    Salario DECIMAL(10, 2)
);

INSERT INTO Colaboradores (CodigoIdentificacao, Nome, CPF, Cargo, Salario)
VALUES
    (1, 'João Silva', '12345678900', 'Gerente', 5000.00),
    (2, 'Maria Santos', '98765432100', 'Analista de Vendas', 3500.00),
    (3, 'Pedro Alves', '45678912300', 'Programador', 4000.00),
    (4, 'Ana Oliveira', '78912345600', 'Designer Gráfico', 3800.00),
    (5, 'Carlos Rodrigues', '32165498700', 'Analista Financeiro', 4500.00);


#--------ETAPA 4---------------

Após a criação dos MER, crie as bases de dados de cada um dos exercícios dados na ETAPA 1;
Insira os dados necessários para compor a base de dados criada;

1 - Um petshop deseja manter cadastrados seus clientes bem como seus pets.
Um cliente deve informar seu nome, CPF, e-mail e telefone, além do nome, espécie e data de nascimento de seu pet.

CREATE DATABASE PetshopDB;

USE PetshopDB;

CREATE TABLE Clientes (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    Nome VARCHAR(255),
    CPF CHAR(11),
    Email VARCHAR(255),
    Telefone VARCHAR(15)
);

CREATE TABLE Pets (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    Nome VARCHAR(255),
    Especie VARCHAR(100),
    DataNascimento DATE,
    DonoID INT,
    FOREIGN KEY (DonoID) REFERENCES Clientes(ID)
);


# PRODUTORA

2 - Em uma produtora de games, há desenvolvedores, que possuem um nome, CPF, data de nascimento.
CREATE DATABASE ProdutoraGamesDB;

USE ProdutoraGamesDB;

CREATE TABLE Desenvolvedores (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    Nome VARCHAR(255),
    CPF CHAR(11) UNIQUE,
    DataNascimento DATE
);



#BIBLIOTECA

Uma biblioteca efetua registro de autores e livros. Um autor é cadastrado com seu nome, e-mail, nacionalidade e data de nascimento. Já um livro é registrado com o título, quantidade de páginas, acabamento e editora.
CREATE DATABASE BibliotecaDB;

-- Usar o banco de dados
USE BibliotecaDB;

CREATE TABLE Autores (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    Nome VARCHAR(255),
    Email VARCHAR(255),
    Nacionalidade VARCHAR(100),
    DataNascimento DATE
);
CREATE TABLE Livros (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    Titulo VARCHAR(255),
    QuantidadePaginas INT,
    Acabamento VARCHAR(50),
    Editora VARCHAR(100)
);




# LOCADORA 


Uma locadora de automóveis, mantém registro dos automóveis. Um automóvel é cadastrado com placa, modelo, ano, nome da montadora, site da montadora, logotipo da montadora.
CREATE DATABASE LocadoraAutomoveisDB;

USE LocadoraAutomoveisDB;

CREATE TABLE Automoveis (
    Placa VARCHAR(10) PRIMARY KEY,
    Modelo VARCHAR(255),
    Ano INT,
    Montadora VARCHAR(100),
    SiteMontadora VARCHAR(255),
    LogotipoMontadora VARCHAR(255)
);





# SUPERMERCADO 



Um supermercado cadastra seus produtos. Um produto é identificado por seu nome, preço, quantidade em estoque, nome da marca, SAC da marca, nacionalidade da marca.
CREATE DATABASE SupermercadoDB;

USE SupermercadoDB;

CREATE TABLE Produtos (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    Nome VARCHAR(255),
    Preco DECIMAL(10, 2),
    QuantidadeEstoque INT,
    Marca VARCHAR(100),
    SACMarca VARCHAR(255),
    NacionalidadeMarca VARCHAR(100)
);



# VIDEOTECA 



Uma videoteca precisa cadastrar o título, duração, idioma original e preço de cada filme. É necessário cadastrar também o elenco de cada filme onde se registra o nome, data de nascimento, nacionalidade de cada ator/atriz. Opcionalmente, inclua o cadastro de diretores com atributos que julgar necessários.

CREATE DATABASE VideotecaDB;

USE VideotecaDB;

CREATE TABLE Filmes (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    Titulo VARCHAR(255),
    Duracao INT, -- Duração em minutos
    IdiomaOriginal VARCHAR(50),
    Preco DECIMAL(10, 2)
);

CREATE TABLE Elenco (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    NomeAtorAtriz VARCHAR(255),
    DataNascimento DATE,
    Nacionalidade VARCHAR(100),
    FilmeID INT,
    FOREIGN KEY (FilmeID) REFERENCES Filmes(ID)
);

CREATE TABLE Diretores (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    NomeDiretor VARCHAR(255),
    DataNascimento DATE,
    Nacionalidade VARCHAR(100),
    FilmeID INT,
    FOREIGN KEY (FilmeID) REFERENCES Filmes(ID)
);



















