# FLASK JENKINS

1. [Pré-requisitos](#pre-requisitos)
2. [Criando e iniciando o container do Jenkins](#criando-e-iniciando-o-container-do-jenkins)
3. [Criando a pipeline](#criando-a-pipeline)
4. [Executando a pipeline](#executando-a-pipeline)
5. [Tratando erros](#tratando-erros)

## Pré-requisitos
- É necessário que sua máquina tenha o docker. Caso não tenha instale pelo tutotial: [How To Install and Use Docker on Ubuntu 22.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04)

## Criando e iniciando o container do Jenkins
Para criar o container Docker com a imagem do jenkins é preciso rodar o seguinte no seu terminal:
```bash
docker compose up
```
O comando **"docker compose up"** cria e inicia os contêineres conforme as configurações especificadas no arquivo. E se tudo ocorrer bem, vamos finalmente para configuração do jenkins.

![](https://boozallen.github.io/sdp-docs/learning-labs/1/local-development/_images/logs_init_password.png)

Após a criação do container será disponibilizado uma chave de acesso, essa chave vai ser utilizada no painel de controle do Jenkins. Para acessar o painel abra o seu navegador e digite a URL localhost:8080, vai ser aberto a página abaixo:

![](https://i.stack.imgur.com/EeLNT.png)

Copie e cole a chave no campo de input e clique em continue. Em seguida clique em **Install suggested plugins**, quando finalizar crie seu perfil e siga em frente, deixe a URL padrão e prossiga novamente. Pronto, você já pode usar o Jenkins!

## Criando a pipeline
Para criar uma pipeline primeiramente clique em `New Item`.
![Alt text](https://www.lambdatest.com/support/assets/images/j2-47b3450920087188b97b7dc694f8e3aa.png)

Em seguida adicione um nome para a sua pipeline e selecione a opção `Pipeline`, desça o seu scroll até ver o botão ok e clique nele.
![](https://www.jenkins.io/doc/book/resources/pipeline/new-item-creation.png)

Por último é necessário que a pipeline seja configurada, preencha o campo de descrição e depois desça o scroll até o tópico pipeline, nele no campo **definition** selecione `Pipeline script from SCM`, no campo **SCM** selecione o `Git` e em **Repository URL** coloque como exemplo a URL abaixo:
```
https://github.com/JoalisonM/flask-jenkins
```
Para finalizar, em **Branches to build** adicione o nome da branch do seu repositório do github, para o repositório acima digite `main`. Agora você pode salvar e sua pipeline está pegando.
![](https://devopspilot.com/content/jenkins/tutorials/pipeline/images/01-first-pipeline-job/jenkins-pipeline-scm.png)

## Executando a pipeline

Após criar a pipeline vá no menu e selecione o **`Open Blue Ocean`**, nele você escolhe a pipeline que deseja ver sendo executa e, ao abrir, clica em `Run` para que a execução seja realizada.

## Tratando erros

É bem provável que você enfrentará erro de permissões, então para corrigir os mesmos siga os passos a seguir.

Navegue até o diretório onde se encontra o docker.sock :
```
cd /var/run
```
Dê as permissões ao docker.sock
```
  sudo chmod 777 docker.sock
```
Adicione o jenkins aos usuários da sua máquina:
```
  useradd jenkins
```
Adicione o Jenkins ao grupo Docker e root, lhe concedendo as permissões necessárias:
```
  sudo usermod -aG docker jenkins
```
```
  sudo usermod -aG root jenkins
```
Para visualizar se eles foram adicionados corretamente, utilize os comandos abaixo:
```
  grep docker /etc/group
```
```
  grep root /etc/group
```