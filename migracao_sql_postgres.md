# migracao_sql_postgres.ipynb

Este notebook em Python apresenta um script simples e funcional para realizar a **migração de todas as tabelas do esquema `DBO` de um servidor MS SQL Server** para um servidor PostgreSQL. O processo é automatizado utilizando bibliotecas Python e pode ser facilmente adaptado para diferentes projetos e estruturas de dados.

## 🎯 Motivação

Durante a elaboração de conteúdos didáticos em SQL, surgiu a necessidade de executar e testar queries utilizando a engine do PostgreSQL. Para isso, escolhi como base o conhecido banco de dados **AdventureWorksDW2022**, originalmente hospedado em um servidor MS SQL Server.

Embora existam soluções mais robustas e complexas para esse tipo de migração, optei por desenvolver uma abordagem mais direta e acessível utilizando Python, com foco em simplicidade e reprodutibilidade.

## ⚙️ Descrição do Processo

O notebook realiza os seguintes passos:

1. **Conexão com o MS SQL Server**  
   Utiliza credenciais e parâmetros de conexão para acessar o banco onde está hospedado o `AdventureWorksDW2022`.

2. **Identificação das Tabelas**  
   Executa uma consulta para listar todas as tabelas pertencentes ao esquema `DBO`. Essa etapa pode ser facilmente ajustada para outros esquemas conforme necessário.

3. **Armazenamento das Tabelas**  
   As tabelas identificadas são armazenadas em uma lista Python para posterior iteração.

4. **Conexão com o PostgreSQL**  
   Estabelece conexão com o banco de destino no PostgreSQL. É importante que este banco já esteja previamente criado.

5. **Migração das Tabelas**  
   Para cada tabela:
   - Os dados são carregados em um `DataFrame` do Pandas.
   - Utilizando a engine de conexão, a tabela é criada e os dados são inseridos no PostgreSQL.

6. **Encerramento das Conexões**  
   Ao final do processo, todas as conexões com os bancos de dados são encerradas de forma segura.

## 📌 Requisitos

- Python 3.x  
- Bibliotecas: `pandas`, `sqlalchemy`, `pyodbc`, `psycopg2`  
- Acesso aos servidores MS SQL Server e PostgreSQL  
- Banco de destino previamente criado no PostgreSQL

## 📚 Observações

- O script foi desenvolvido com foco em **simplicidade e clareza**, ideal para fins educacionais e pequenas migrações.
- Pode ser expandido para incluir tratamento de tipos de dados, índices, constraints e outras estruturas avançadas.

## 🤝 Contribuições

Sugestões de melhoria, correções ou adaptações são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.

---

> Este notebook é parte de um repositório maior dedicado à Engenharia de Dados aplicada. Explore os demais scripts e recursos disponíveis!
