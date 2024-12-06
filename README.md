# Instruções para Execução dos Scripts no Oracle

Este repositório contém os scripts de criação de pacotes PL/SQL para gerenciamento de alunos, disciplinas, professores e suas respectivas funcionalidades no Oracle Database.

## Como Executar os Scripts

### Preparar o Ambiente:
- Certifique-se de ter o Oracle Database configurado e rodando.
- Utilize uma ferramenta como o Oracle SQL Developer ou o Oracle Live SQL.

### Criar as Tabelas Base (se necessário):
Antes de executar os scripts de pacotes, certifique-se de que as tabelas associadas estão criadas no banco de dados:
- `aluno`
- `disciplina`
- `professor`
- `turma`
- `matricula`

### Executar os Scripts:
1. Abra o script do pacote desejado no Oracle SQL Developer.
2. Execute primeiro a especificação do pacote (`CREATE OR REPLACE PACKAGE ...`) e depois o corpo do pacote (`CREATE OR REPLACE PACKAGE BODY ...`).

### Testar as Funcionalidades:
- Use os exemplos de testes fornecidos no repositório ou crie seus próprios blocos PL/SQL para chamar os procedimentos e funções de cada pacote.

---

## Resumo dos Pacotes

### **PKG_ALUNO**
Gerencia as operações relacionadas aos alunos.
- **Procedures:**
  - `EXCLUIR_ALUNO`: Exclui um aluno e todas as matrículas associadas a ele.
- **Cursores:**
  - `LISTAR_ALUNOS_MAIORES_18`: Retorna os alunos maiores de 18 anos.
  - `LISTAR_ALUNOS_POR_CURSO`: Lista os alunos matriculados em um curso específico.

---

### **PKG_DISCIPLINA**
Gerencia as operações relacionadas às disciplinas.
- **Procedures:**
  - `CADASTRAR_DISCIPLINA`: Cadastra uma nova disciplina, evitando duplicatas.
  - `LISTAR_ALUNOS_DISCIPLINA`: Lista os alunos matriculados em uma disciplina específica.
- **Cursores:**
  - `TOTAL_ALUNOS_POR_DISCIPLINA`: Retorna as disciplinas e o número total de alunos matriculados, exibindo apenas aquelas com mais de 10 alunos.
- **Funções:**
  - `MEDIA_IDADE_DISCIPLINA`: Calcula a média de idade dos alunos de uma disciplina.

---

### **PKG_PROFESSOR**
Gerencia as operações relacionadas aos professores.
- **Procedures:**
  - `TOTAL_TURMAS_POR_PROFESSOR`: Lista os professores e o total de turmas que cada um leciona, filtrando apenas aqueles com mais de uma turma.
- **Funções:**
  - `TOTAL_TURMAS_PROFESSOR`: Retorna o total de turmas de um professor específico.
  - `PROFESSOR_DISCIPLINA`: Retorna o nome do professor responsável por uma disciplina específica.

---

## Dicas para Execução

- **Ativar DBMS_OUTPUT:**
  - Para visualizar resultados de cursores ou mensagens de saída, ative o `DBMS_OUTPUT` no Oracle SQL Developer.
  
- **Erros ao Recompilar:**
  - Caso encontre erros ao compilar um pacote, utilize o comando `SHOW ERRORS` para identificar os problemas.

- **Alterar Dados para Testes:**
  - Insira dados nas tabelas relacionadas para simular cenários reais e validar as funcionalidades dos pacotes.

---
