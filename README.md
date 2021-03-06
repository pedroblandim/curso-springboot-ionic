# curso-springboot-e-ionic
Curso de Spring Boot, Hibernate, REST, Ionic, JWT, S3, MySQL.
O projeto consiste num sistema de cadastro de pedidos, com autenticação de usuários.

## Anotações:
### Dicas
  * Cuidado com as referências cíclicas ao criar uma relação bidirecional (problema resolvido com @JsonIgnore no lado da associação que não deve ser serializada, ou utilizar @JsonManagedReference e @JsonBackReference).
  * A JPA se baseia nos métodos get das entidades para a serialização das mesmas.
  * Escolhendo estratégia de herança para a hierarquia de uma classe de entidade (geralmente): Escolher tabela única (SINGLE_TABLE) quando as subclasses possuem poucos campos ou criar uma tabela para cada classe (JOINED), caso contrário.
  * Por utilizarmos uma classe abstrata para representar o pagamento, com duas subclasses a extendendo, é possível perceber a existência de um polimorfiso na resposta trazida pelo end point de Pedidos. O pagamento relacionado ao pedido requisitado pode ser uma instância de qualquer subclasse de Pagamento.

### Camadas

#### Serviço
  
  * A camada de serviço tem a responsabilidade de oferecer operações de consulta para os controladores REST. 
  * Faz a ligação entre os controladores e a camada de domínio. 
  * A camada de serviço não tem contato nenhum com alguma tecnologia específica, já que sua resposabilidade é intermediar a camada de domínio e os controladores. 
  * Possúi as regras de negócio que porventura não tenham sido implementadas na camada de domínio. 
  * Utiliza a camada de acesso a dados.

#### Camada de acesso a dados (Repository)
  
  * Tem a responsabilidade de conversar com o banco de dados (implementa o CRUD dos resources, por exemplo) 

#### Controladores (Resources)
  
  * Ponto de entrada da aplicação

#### Domínio (Domain)

  * Entidades do banco de dado
  * Faz a ligação entre os objetos da área de conhecimento do problema a ser tratado com o código em si.
  
 
 
