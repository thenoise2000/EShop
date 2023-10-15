
Aplicativo desenvolvido em Java Springboot para gerenciamento de produtos

Foi desenvolvida uma aplicação utilizando autenticação em dois níveis de usuários de acesso para gerenciamento de produtos com Spring Boot e utilizando um banco de dados MySQL.


Ferramentas

- Java 8

- SpringBoot

- SpringSecurity

- JPA

- MySQL

- Maven

- thymeleaf

- HTML

- CSS

Funcionamento 

Diagrama Entidade-Relacionamento (ERD) para Tabelas de Categoria e Produto


[Category] 1 ----> * [Product]



O ERD mostra que a tabela Categoria tem um relacionamento um-para-muitos com a tabela Produto. Isto significa que cada Categoria pode ter vários Produtos, mas cada Produto só pode pertencer a uma Categoria.

O relacionamento entre as duas tabelas é representado pela chave estrangeira category_id na tabela Produto. Esta chave estrangeira faz referência à chave primária Category_id na tabela Categoria.

Exemplo:

A categoria “Frutas” pode conter diversos produtos, como maçãs, bananas, uvas e laranjas.
O produto “maçã” só pode pertencer à categoria “Frutas”.
O ERD é uma ferramenta útil para projetar e compreender bancos de dados relacionais. Pode ajudar a garantir que o banco de dados esteja normalizado e que os relacionamentos entre as tabelas estejam definidos corretamente.

O modelo Entidade/Relacionamento é o seguinte 

             +--------------+
             |   category   |
             +--------------+
             | category_id  |
             | name         |
             +--------------+
                    |(1)
                    |
                    |
                    |(*)
             +--------------+
             |   product    |
             +--------------+
             | id           |
             | description  |
             | image_name   |
             | name         |
             | price        |
             | weight       |
             | category_id  |
             +--------------+
                    
                    
                    
                    
             +--------------+
             |    roles     |
             +--------------+
             | id           |
             | name         |
             +--------------+
                    |(1)
                    |                            +--------------+
                    |                            |  user_role   |
                    |                            +--------------+
                    |                            | user_id      |
                    |                            | role_id      |
                    |                            +--------------+
                    |
                    |(*)
             +--------------+
             |    users     |
             +--------------+
             | id           |
             | email        |
             | first_name   |
             | last_name    |
             | password     |
             +--------------+


* Para instalar

Clonamos ou baixamos o clone do repositório git https://github.com/thenoise2000/EShop
Vá para a raiz do projeto: cd ApiUsers
Compilamos: mvn clean install
Executamos mvn spring-boot:run


* Para desplegarlo ejecute

comando
  mvn spring-boot:run

Para usar esta API você deve primeiro inserir os dados de autenticação no formulário de login principal

- Email: admin@gmail.com
- Password: $Admin=25

O aplicativo usa um banco de dados MySQL e possui um registro de dados SQL anterior chamado shop.sql que você deve executar para carregar os dados do aplicativo.








