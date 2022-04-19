# Parking Control API   - Spring Boot - Michelli Brito

## Aplicação

API para controle de estacionamento

## Tecnologias

- Spring Boot
- Spring MVC
- Spring Data JPA
- Spring Validation 

## Criar projeto 

Utilizar spring initializr 

![image](https://user-images.githubusercontent.com/52088444/160170983-bac72749-f23b-48ef-a421-1073e3b7d7b8.png)

[Site spring initializr  ](https://start.spring.io/)


## Observação

![image](https://user-images.githubusercontent.com/52088444/160170586-987f5ef8-29b6-49f0-a6cd-28aeca32b56d.png)

![image](https://user-images.githubusercontent.com/52088444/160170705-db791478-2b30-4d96-bfda-92fc2fadeddf.png)

## Configuração da base de Dados

As configurações são feitas dentro de applications.properties

- primeiro cria a base de dados no postgrees nomeado como: parking-control-db;
- depois de criar a base de dados eu posso definir a conexão da aplicação com a base;

spring.datasource.url= jdbc:postgresql://localhost:5432/parking-control-db

spring.datasource.username=postgres

spring.datasource.password=postgres

spring.jpa.hibernate.ddl-auto=update  ("update" : sempre que criamos e mapeamos entidades, na hora que executamos a aplicação
isso seja criado automaticamente na base de dados,sem que tenhamos que ir na base para criar scripts)

spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation=true (desabilitar o non_contextual_creative
para não ter problemas de gerar logs de erros)


## Anotações

 @RestController :  para essa classe saber que ela vai sem um bean do tipo Controller e for gerados as 
 dependencias quando for necessário

A anotação @GetMapping é uma versão especializada de @RequestMappinganotação que atua como um atalho para
arquivos @RequestMapping(method = RequestMethod.GET).

Os @GetMappingmétodos anotados nas classes anotadas @Controller tratam das solicitações HTTP GETque correspondem
a uma determinada expressão de URI.



## Informações
implements Serializable  : Serialização é a técnica que permite transformar o estado de um objeto em uma sequência bytes. 
Depois que um objeto for serializado ele pode ser gravado (ou persistido) em um arquivo de dados e recuperado do arquivo
e desserializado para recriar o objeto na memória.

**O que é UUID?**
É um identificador universalmente exclusivo utilizado para identificação de qualquer coisa no mundo da computação. 
O UUID é um número de 128 bits representado por 32 dígitos hexadecimais, exibidos em cinco grupos separados por hifens, 
na forma textual8-4-4-4-12 sendo um total de 36 caracteres (32 caracteres alfanuméricos e 4 hifens). Por exemplo:
3d0ca315-aff9–4fc2-be61–3b76b9a2d798
O objetivo dos UUIDs é possibilitar a identificação unica de uma informação em sistemas distribuídos, sem uma coordenação
central. Neste contexto a palavra única deve ser tomada com o significado de “praticamente única” uma vez que os identificadores
possuam um tamanho finito, é possível para dois itens diferentes compartilhar do mesmo identificador. O tamanho e o processo 
de geração do identificador necessitam ser selecionados de forma a tornar esta improbabilidade suficientemente na prática.


## MVC

**A camada Model**

A camada Model (modelo) representa a parte de sua aplicação que implementa a lógica do negócio. Isto significa que ela é
responsável por obter os dados convertendo-os em conceitos significativos para sua aplicação, assim como, processar, 
validar, associar e qualquer outra tarefa relativa ao tratamento dos dados.

À primeira vista, os objetos do tipo Model podem ser vistos como a primeira camada de interação com qualquer banco de 
dados que você possa estar usando na sua aplicação. Mas em geral eles representam os principais conceitos em torno do 
qual você implementa sua aplicação.

No caso de uma rede social, a camada Model cuida de tarefas como as de salvar os dados dos usuários e o relacionamento
entre amigos, armazenar e recuperar as fotos dos usuários, encontrar novos amigos para sugestões e etc. Neste exemplo 
os Models podem ser vistos como “Amigo”, “Usuario”, “Comentario”e “Foto”.

**A camada Controller**

A camada Controller (controlador) lida com as requisições dos usuários. É responsável por retornar uma resposta com a 
ajuda das camadas Model e View.

Os Controllers podem ser vistos como gerentes tomando os devidos cuidados para que todos os recursos necessários para 
completar uma tarefa sejam delegados para os trabalhadores corretos. Ele aguarda os pedidos dos clientes, verifica a
validade de acordo com as regras de autenticação e autorização, delega dados para serem obtidos ou processados pelos 
Models e seleciona o tipo correto de apresentação dos dados para o qual o cliente está aceitando para finalmente delegar
o trabalho de renderização para a camada de visualização.
