# BibliotecaUniversitariaSQL

-- Criação da tabela Alunos
CREATE TABLE Alunos (
    AlunoID INT PRIMARY KEY,
    Nome VARCHAR(50) NOT NULL,
    Curso VARCHAR(50),
    AnoIngresso INT
);

-- Criação da tabela Autores
CREATE TABLE Autores (
    AutorID INT PRIMARY KEY,
    NomeAutor VARCHAR(50) NOT NULL
);

-- Criação da tabela Livros
CREATE TABLE Livros (
    LivroID INT PRIMARY KEY,
    Titulo VARCHAR(100) NOT NULL,
    AnoPublicacao INT
);

-- Criação da tabela Livro_Autor
CREATE TABLE Livro_Autor (
    LivroID INT,
    AutorID INT,
    PRIMARY KEY (LivroID, AutorID),
    FOREIGN KEY (LivroID) REFERENCES Livros(LivroID),
    FOREIGN KEY (AutorID) REFERENCES Autores(AutorID)
);

-- Criação da tabela Empréstimos
CREATE TABLE Emprestimos (
    EmprestimoID INT PRIMARY KEY,
    AlunoID INT,
    LivroID INT,
    DataEmprestimo DATE,
    DataDevolucao DATE,
    FOREIGN KEY (AlunoID) REFERENCES Alunos(AlunoID),
    FOREIGN KEY (LivroID) REFERENCES Livros(LivroID)
);
