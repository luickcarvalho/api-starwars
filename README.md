# GET API STARWARS


## Descrição
Está aplicação foi desenvolvida em Ansible realiza um GET nesta API (https://swapi.dev),
e utilizando o modulo Debug do Ansible para que retorne está mensagem "O planeta {{ nome_planeta}} é mencionado em {{ numero_filmes}} filmes."

## Execução da Playbook, Utilizando Ansible Instalado Localmente

- Diretorio da Playbook: get-api-starwars-ansible

- Tarefas Executadas dentro do Código

  1- Responsável pela consulta na API StarWars e retornar um JSON com todas as informações.

  2- Tratar o JSON e filtra o nome do planeta incluído na variável e realiza a contagem em quantos filmes da saga este planeta teve exibição e retorna o resultado.

- Requisito de utilização

  Quando executar sua playbook, fique atento que deve ter o Ansible instalado em seu SO.

- Execução

  Para que a sua playbook seja você deve estar no diretório da respectiva e digitar este comando incluído no nome do planeta que deseja.
  ```sh
  ansible-playbook playbook.yml -e 'nome_planeta=Kamino'
  ```
## Execução Operator Ansible em um Cluster Kubernetes

 Imagem da Aplicação (https://hub.docker.com/r/luickcarvalho/api-starwars/tags).

- Requisito de utilização
   Precisa possuir um cluster kubernetes provisionado.

- Execução
   Primeiramente precisa realizar a criação do documento responsável pelo deployment do Pod, 
   apontando a imagem que está ali em cima. 
