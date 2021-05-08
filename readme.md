# DPI - Ruby 3

Este é um projeto de exemplo para aplicações Ruby 3.0, usando containers Docker.
Foi configurado para facilitar o processo de desenvolvimento com uma imagem do projeto ricardopedias/docker-project.

## Infraestrutura

O projeto faz uso da seguinte configuração:

- Ruby 3.0
- Nginx 1.18
- Passenger 6.0
- Bundle 2.2

## Execução do projeto

Para executar a infraestrutura, use:

```
docker-compose up
ou
docker-compose up -d
```

Em seguida, para subir a aplicação, execute:

```
./bundle install
```

Ao subir o container, o Nginx será automaticamente iniciado:

```
// para acessar a aplicação
http://localhost:1111/
```

## Desenvolvimento

Na raiz do projeto, existe um comando de atalho para o Bundle, que permite executá-lo sem precisar acessar o terminal do container. Por exemplo, para executar qualquer comando, basta invocar:

```
./bundle <qualquer comando>
```

Para entrar no container com facilidade, existe um cmando especial: 

```
./bundle bash
```

## Refresh da aplicação

Por padrão, após a primeira compilação, o Passenger guarda a aplicação em cache. Para que o Passenger ignore o cache em todas as visitas nos URLs, basta criar o arquivo "always_restart.txt" no diretório "tmp",  como é explicado no comando abaixo:

```
mkdir tmp
touch tmp/always_restart.txt
```

## Referências

- https://github.com/rack/rack
- https://bundler.io/man/bundle-config.1.html
- https://www.phusionpassenger.com/library/walkthroughs/basics/ruby/reloading_code.html
- https://guides.rubygems.org/run-your-own-gem-server
