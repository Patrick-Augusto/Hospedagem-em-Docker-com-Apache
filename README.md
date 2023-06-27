# Documentação do Projeto

Este é um guia de documentação para configurar e executar um contêiner Docker do servidor Apache HTTP para hospedar seu site. As instruções a seguir ajudarão você a configurar um ambiente de desenvolvimento local para o Apache usando o Docker.

## Requisitos

Antes de prosseguir, certifique-se de ter os seguintes requisitos em seu sistema:

1. Docker instalado e configurado no seu sistema. Você pode obter o Docker em [https://www.docker.com/get-started](https://www.docker.com/get-started).

## Configuração

Siga as etapas abaixo para configurar o contêiner do Apache HTTP usando o Docker:

1. Crie um novo diretório para o seu projeto do Apache:

```bash
mkdir meu-projeto-apache
cd meu-projeto-apache
```

2. Crie um novo arquivo chamado `docker-compose.yml` e abra-o em um editor de texto:

```bash
touch docker-compose.yml
```

3. Copie o código abaixo e cole no arquivo `docker-compose.yml`:

```yaml
version: '3.9'
services:
  apache:
    image: httpd:latest
    container_name: my-apache-app
    ports:
    - '80:80'
    volumes:
    - ./website:/usr/local/apache2/htdocs
```

4. Crie um diretório chamado `website` no mesmo diretório do arquivo `docker-compose.yml`. Este diretório será usado para armazenar os arquivos do seu site:

```bash
mkdir website
```

5. Coloque todos os arquivos do seu site no diretório `website`.

## Execução

Agora que a configuração está concluída, siga as etapas abaixo para executar o contêiner do Apache:

1. Abra o terminal e navegue até o diretório do projeto do Apache:

```bash
cd meu-projeto-apache
```

2. Execute o seguinte comando para iniciar o contêiner:

```bash
docker-compose up -d
```

Isso iniciará o contêiner Apache em segundo plano.

3. Abra o navegador da web e acesse `http://localhost` para visualizar seu site.

## Gerenciamento do Contêiner

Aqui estão alguns comandos úteis para gerenciar o contêiner do Apache:

- Para iniciar o contêiner:

```bash
docker-compose up -d
```

- Para parar o contêiner:

```bash
docker-compose down
```

- Para reiniciar o contêiner:

```bash
docker-compose restart
```

- Para verificar o status do contêiner:

```bash
docker-compose ps
```

## Considerações Finais

Agora você tem um ambiente local configurado com um contêiner Docker do Apache HTTP para hospedar seu site. Lembre-se de atualizar o diretório `website` com os arquivos atualizados do seu site sempre que necessário.

Se você quiser implantar seu site em um ambiente de produção, certifique-se de seguir as práticas recomendadas de segurança e escalabilidade.

Divirta-se desenvolvendo seu site com o Apache HTTP e Docker!
