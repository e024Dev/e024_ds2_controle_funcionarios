# e024_ds2_controle_funcionarios

# Controle Funcionarios

Neste tutorial voces irao desenvolver as funcionalidades apresentadas nas aula teóricas em sala de aula.

Iremos criar um sistema web de controle de funcionários utilizando Spring Boot.

Siga os passos abaixo para concluirmos a criação de uma aplicação utilizando o padrão MVC.

## Criação do Projeto.

Acesse o site [inializr](https://start.spring.io/) e crie o projeto `e024_ds2_controle_feuncionarios`. 

Adicione as dependecias:
* Web;
* H2;
* DevTools;
* JPA;
* MySQL;
* Thymeleaf;
* Validation;

> Descompacte o projeto, aguarde o Maven baixar as dependencias.

### Configuração do Banco de dados em memória.

No arquivo `resources/application.properties`, adicione as configurações de conexão com a base de dados H2.

```properties
# Server
server.port=9000

# H2
spring.datasource.url=jdbc:h2:mem:cesario
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=aluno
spring.datasource.password=segredo@123
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect

```

### Mapeamento Objeto Relacional

Cria a classe `Departamento` no pacote `domain/funcionarios`.

> Relembre-se das configurações das colunas com as anotaçṍes @Column.

```java
@Entity
public class Departamento {
    
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Integer id;

    @Column(nullable = false, length = 100)
    private String descricao;

    

    public Departamento() {
    }

    

    public Departamento(String descricao) {
        this.descricao = descricao;
    }

    //TODO: Getters e Setters logo abaixo [como a IDE faz automaticamente, deixei o código para voce fazer]


    @Override
    public String toString() {
        return "Departamento [id=" + id + ", descricao=" + descricao + "]";
    }
    
}
```

### Teste da criação da entidade departamento

Após a criação da entidade, execute o projeto e acesse a url `http://localhost:9000/h2-console` utilizando os dados de conexão do `application.properties`.

### Crie o repositório para manipulação da entidade

No mesmo diretório da entidade `Departamento`, crie a classe `DepartamentoRepository` e adicione o trecho abaixo.

```java
@Repository
public interface DepartamentoRepository extends JpaRepository<Departamento, Integer>{
    
}

```

### Camada de Serviços

Iremos criar a camada de serviços, como a cama da de dados não deve conter regras de negócio, o acesso deverá ser realizado pela camada de serviços.

Crie a classe `services/DeparpatemtoService`.

```java
@Service
public class DepartamentoService {

    //TODO: Criar método buscar todos os departamentos
    //TODO: Criar método buscar por id
    //TODO: Criar método salvar
    //TODO: Criar método atualizar
    //TODO: Criar método apagar por id
}
```
