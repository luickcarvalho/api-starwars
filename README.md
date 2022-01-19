# GET API STARWARS


## Descrição
Está aplicação foi desenvolvida em Ansible realiza um GET nesta API (https://swapi.dev),
e utilizando o modulo Debug do Ansible para que retorne está mensagem "O planeta {{ nome_planeta}} é mencionado em {{ numero_filmes}} filmes."

Imagem da Aplicação (https://hub.docker.com/r/luickcarvalho/api-starwars/tags)

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

- Requisito de utilização
  Possuir Cluster Kubernetes provisionado
  Clone do diretorio kub-ans-ope-gt-api
  Instalação do Make
  
- Etapas de utilização  
  
  Primeira
  Acessar esse o diretório kub-ans-ope-gt-api e executar o comando “make deploy”, automaticamente os serviços da aplicação serão provisionados no Kubernetes.
  
  Segunda
  Agora você precisa realizar a criação do serviço que irá rodar a task da playbook com o comando “kubectl –f apply config/samples/lucasfilme_v1alpha1_starwars.yaml”
  Serviço provisionado!! 
  
  Terceira
  Agora é preciso rodar este comado “kubectl logs --follow kub-ans-ope-gt-api-controller-manager-69c6b59b99-94rqh manager -n kub-ans-ope-gt-api-system”,
  para verificar se a playbook foi executada com sucesso e se retornou a mensagem “O planeta Kamino é mencionado em 1 filme”.
