# ProjetoFaculdade

CREATE TABLE Aluno 
(
    id_aluno INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    senha VARCHAR(255) NOT NULL
);

CREATE TABLE Atividade 
(
    id_atividade INT PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(100) NOT NULL,
    descricao TEXT,
    data DATE NOT NULL,
    horario TIME NOT NULL,
    categoria ENUM('Prova', 'Trabalho', 'Projeto', 'Outro') NOT NULL,
    id_aluno INT,
    FOREIGN KEY (id_aluno) REFERENCES Aluno(id_aluno) ON DELETE CASCADE
)
