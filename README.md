# GET API STARWARS


## Descrição
Esta aplicação desenvolvida em Ansible realiza uma consulta nesta API (https://swapi.dev),
faz o filtro de informações e com o módulo Debug do Ansible retorna a mensagem "O planeta {{ nome_planeta}} é mencionado em {{ numero_filmes}} filmes."

Imagem da Aplicação: (https://hub.docker.com/r/luickcarvalho/api-starwars/tags)

## Execução da Playbook, Utilizando Ansible Instalado Localmente

- Diretório da Playbook: get-api-starwars-ansible

- Tarefas Executadas dentro do Código

  1- Responsável pela consulta na API StarWars, que retorna o JSON com todas as informações.

  2- Trata o JSON e filtra o nome do planeta incluído na variável e realiza a contagem de quantos filmes da saga este planeta participou e retorna o resultado.

- Requisito de utilização

  Quando executar sua playbook, fique atento. Você deve ter o Ansible instalado em seu Sistema Operacional.

- Execução

  Para que a sua playbook seja executada, você deve estar no diretório da respectiva e digitar este comando incluído no nome do planeta.
  ```sh
  ansible-playbook playbook.yml -e 'nome_planeta=Kamino'
  ```
## Executar o Operator Ansible em um Cluster Kubernetes

- Requisito de utilização
  Possuir Cluster Kubernetes provisionado
  Clone do diretório kub-ans-ope-gt-api
  Ter o Make instalado
  
- Etapas de Utilização  
  
  Primeira
  
  Acessar o diretório kub-ans-ope-gt-api e executar o comando “make deploy”, automaticamente os serviços da aplicação serão provisionados no Kubernetes.
  
  Segunda
  
  Agora você precisa realizar a criação do serviço que irá executar as task com o comando “kubectl –f apply config/samples/lucasfilme_v1alpha1_starwars.yaml”,  
  caso que mudar no nome do planeta, basta editar o arquivo e alterar a variável "nome_planeta".
  
  Serviço provisionado!! 
  
  Terceira
  
  Agora é preciso executar o comando “kubectl logs --follow kub-ans-ope-gt-api-controller-manager-69c6b59b99-94rqh manager -n kub-ans-ope-gt-api-system”,
  para verificar se a playbook foi executada com sucesso e se retornou a mensagem “O planeta Kamino é mencionado em 1 filme”.
