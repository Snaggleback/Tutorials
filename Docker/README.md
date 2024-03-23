# Docker (_Mini Aulão_)

## Introdução

O Docker revolucionou a forma como desenvolvemos, testamos e implantamos aplicações. Através de **containers**, o Docker permite empacotar tudo que seu aplicativo precisa para funcionar em uma única unidade leve e portátil

Este tutorial completo irá te guiar por todos os aspectos do Docker, desde a instalação até a criação de imagens complexas e o gerenciamento de containers em produção

## Parte 1: Instalação e Conceitos Básicos

1. **Instalação do Docker:**
    - Acesse o [site oficial do Docker](https://www.docker.com/get-started) e siga as instruções para instalar o Docker em seu sistema operacional
    - Verifique se a instalação foi bem sucedida executando o comando `docker version`
2. **Conceitos Básicos do Docker:**
    - **Imagem:** Um modelo executável que contém tudo que seu aplicativo precisa para funcionar
    - **Container:** Uma instância em execução de uma imagem
    - **Dockerfile:** Um arquivo de texto que define como construir uma imagem
    - **Docker Hub:** Um repositório central de imagens públicas
3. **Primeiros Passos com o Docker:**

    - Crie um **Dockerfile** simples para um aplicativo Python:

    ```docker
    FROM python:3.9

    RUN pip install flask

    COPY . /app

    CMD ["python", "app.py"]
    ```

    - Construa a imagem a partir do **Dockerfile**:

    ```docker
    docker build -t my-app .
    ```

    - Execute o container da imagem:

    ```docker
    docker run -p 5000:5000 my-app
    ```

Acesse o aplicativo em seu navegador web em seu [localhost (porta 5000)](http://localhost:5000)

## Parte 2: Conceitos Intermediários

1. **Gerenciamento de Containers:**
    - Utilize o comando `docker ps` para listar containers em execução
    - Pare um container com o comando `docker stop <container_id>`
    - Remova um container com o comando `docker rm <container_id>`
2. **Volumes:**
    - Utilize volumes para persistir dados entre containers
    - Crie um volume com o comando `docker volume create my-volume`
    - Monte o volume em um container com a opção `-v` do comando `docker run`
3. **Redes:**
    - Crie redes personalizadas para containers se comunicarem
    - Conecte containers a uma rede com a opção `--network` do comando `docker run`

## Parte 3: Conceitos Avançados

1. **Imagens Multi-estágio:**
    - Crie imagens multi-estágio para otimizar o tamanho e a segurança das imagens
    - Utilize diferentes estágios para compilar, instalar e executar seu aplicativo
2. **CI/CD com Docker:**
    - Utilize o Docker para automatizar o processo de CI/CD
    - Crie pipelines que constroem, testam e implantam seus containers automaticamente
3. **Orquestração de Containers:**
    - Utilize ferramentas como Docker Swarm ou Kubernetes para gerenciar containers em produção
    - Escale seus containers horizontalmente para atender à demanda

## Recursos Adicionais e Conclusão

1. Documentação oficial do Docker: [https://docs.docker.com/](https://docs.docker.com/)
2. Docker Hub: [https://hub.docker.com/](https://hub.docker.com/)
3. Tutoriais do Docker: [https://www.docker.com/get-started](https://www.docker.com/get-started)

O Docker é uma ferramenta poderosa que pode otimizar seu fluxo de trabalho de desenvolvimento e tornar a implantação de aplicações mais eficiente. Este tutorial te forneceu uma base sólida para começar a usar o Docker. Explore os recursos adicionais para aprofundar seus conhecimentos e dominar essa tecnologia

> **Observação:** Este tutorial oferece um resumo abrangente do Docker. Para uma compreensão mais profunda e completa, é altamente recomendado que você explore recursos adicionais e pratique os conceitos abordados. Você pode fazer isso consultando a documentação oficial do Docker ou seguindo o tutorial oficial disponível
