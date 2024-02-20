# Banco de dados para uma discoteca
____________________________________________

Este projeto consiste em um banco de dados elaborado para gerenciar as informações de uma gravadora de forma eficiente. As informações são cuidadosamente organizadas em tabelas que representam as principais entidades de negócio. Esse processo segue uma sequência lógica, começando pela extração das informações do modelo de negócio, seguida pela elaboração do modelo entidade-relacionamento, a criação do modelo relacional e, por fim, a implementação do modelo físico no banco de dados.
____________________________________________

## Modelo de negócio.

Uma discoteca está planejando desenvolver um sistema de controle para gerenciar seu acervo de discos. Em essência, o banco de dados precisará armazenar informações cruciais sobre os discos, como o nome, a duração total, o ano de lançamento, o gênero de cada um e sua gravadora. A duração de cada disco será determinada diretamente pelo tempo de todas as músicas contidas nele. Além disso, as 
músicas só poderão fazer parte de um único disco.
O sistema também precisa registrar informações sobre os artistas envolvidos na gravação de cada disco, incluindo nome, data de nascimento e um identificador único para cada um. 
Essas informações são essenciais para garantir um controle eficaz do acervo da discoteca e para facilitar a gestão e organização dos discos.

## Modelo Entidade Relacionamento

![Modelo Entidade Relacionamento](https://github.com/Wanderson-Martins/MySQL/assets/84239851/e7f5238f-ed2f-430f-bf65-d9b057102ae7)

## Modelo Relacional

![Modelo Logico](https://github.com/Wanderson-Martins/MySQL/assets/84239851/bcaee951-e274-42ac-b224-ce232efefcd8)

## Estrutura do Banco de Dados

![Estrutura](https://github.com/Wanderson-Martins/MySQL/assets/84239851/3706eab6-cbfb-450c-8027-87847cbdd4e1)
____________________________________________

## As principais tabelas do banco são:

- `Tabela 1`: artista: tabela que contém as informações dos artistas, como nome e data de nascimento.
- `Tabela 2`: disco: tabela que contém as informações dos discos produzidos pela gravadora, como título, tempo total, ano de lançamento, entre outros.
- `Tabela 3`: gravadora: tabela que contém as informações da própria gravadora, como nome, entre outros.
- `Tabela 4`: genero: tabela que contém as informações dos gêneros musicais, como nome.
- `Tabela 5`: musica: tabela que contém as informações das músicas, como título, tempo, letra, entre outros.
____________________________________________

## Views

 - `View 1`: v_disco_artista_genero: Essa view retorna uma lista com os títulos dos discos, os nomes dos artistas e os gêneros musicais a que pertencem. É possível utilizá-la para consultar as informações dos discos, artistas e gêneros simultaneamente.
- `View 2`: v_disco_musica: Essa view retorna uma lista com os títulos dos discos, o nome das músicas e o tempo de duração de cada música. É possível utilizá-la para consultar as informações das músicas presentes em cada disco.
- `View 3`: v_gravadora_quantidade_discos: Essa view retorna uma lista com o nome das gravadoras e a quantidade de discos que elas possuem. É possível utilizá-la para consultar as informações das gravadoras presentes no banco de dados.
____________________________________________

## Procedures

- `Procedure 1`: sp_insert_disco: Insere um novo disco na tabela tb_disco, verificando se os dados de entrada (titulo_disco, tempo_disco, ano_lancamento, id_artista, id_gravadora, id_genero) são válidos e não nulos. Para garantir que o tempo total do disco seja a soma do tempo das músicas que o compõem, a procedure realiza uma soma do tempo das músicas com o mesmo id_disco do disco a ser inserido e compara com o valor passado como parâmetro. Caso os dados de entrada não sejam válidos, a procedure não realiza a inserção e retorna uma mensagem de erro.
`Procedure 2`: sp_delete_musica: Deleta uma música da tabela tb_musica, verificando se o id da música é válido e não nulo. Caso não seja, a procedure não realiza a exclusão e retorna uma mensagem de erro.                                                                        
- `Procedure 3`: sp_update_artista: Atualiza as informações de um artista na tabela tb_artista. Verifica se os dados de entrada (nome_artista, ano_nascimento, id_pais) são válidos e não nulos. Impede a inserção de caracteres numéricos no nome do artista e garante que as datas sejam inseridas corretamente.

____________________________________________

## Trigger

- `Trigger`: trigger_insert_tb_musica: Atua sobre a tabela tb_musica, executando uma série de ações quando uma nova linha é inserida na tabela. A trigger atualiza o campo tempo_disco na tabela tb_disco, somando o tempo da nova música inserida ao tempo já existente do disco. 
____________________________________________

# Como Contribuir

### Pré-requisitos
- É necessário ter o MySQL instalado na sua máquina.
- É necessário ter um software que permita a criação de um banco de dados, como o MySQL Workbench, instalado na sua máquina.

### Instalação
- 1 - Clone este repositório.
- 2 - Abra o MySQL Workbench e crie um novo banco de dados com o nome "db_discoteca".
- 3 - Abra o arquivo "cargainicial.sql" localizado na pasta raiz deste repositório e execute-o no seu banco de dados. Isso criará todas as tabelas necessárias para a gestão de uma gravadora, como descrito na seção "ESTRUTURA DO BANCO DE DADOS", assim como todas as procedures necessárias para inserção, atualização e exclusão de dados nas tabelas, views e Triggers.

## Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para sugerir melhorias, correções de bugs ou adicionar novas funcionalidades através de pull requests.

## Autor
Este projeto foi desenvolvido por Wanderson Martins.