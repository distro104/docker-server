<p align="center" style="font-size:28px">
Docker-server
</p>
<hr>

<p align="justify" style="font-size:18px">
Projeto com o objetivo de disponibilizar servicos de PHP, banco de dados MariaDb com um servidor nginx para o desenvolvimento de projetos utilizando estas tecnologias. Foi desenvolvido e testado diretamente no linux Mint e caso seja usado no windows precisara de configurações adicionais para funcionar corretamente e poderão ter novas atualizações e adaptações com o tempo.
Este projeto foi desenvolvido com o objetivo de treinar o uso do Docker e não deve ser utilizado em produção, somente como teste no desenvolvimento de projetos ou como referência para outros.
</p>

<p align="center" style="font-size:20px; border:1px solid; padding: 5px;">
>> ⭐ << 
<br />
Se este projeto foi útil para você, considere deixar uma estrela (Star) no repositório. Esse pequeno gesto ajuda a divulgar o projeto, motiva a continuidade do desenvolvimento e incentiva a criação de novos conteúdos. Obrigado pelo apoio!
</p>

## Tecnologias utilizadas:
```
> Docker
> PHP 8.4-fpm
> nginx - Versão mais atualizada possivel
> MariaDb - Versão mais atualizada possivel
> Composer
```
## Requerimentos:
```
> git
> docker 
```
## Comandos:
### Os comandos abaixo seram utilizados para desde o download do repositorio ate a instalacao dos componentes do Docker:

```
> git clone https://github.com/distro104/docker-server.git
> cd docker-server
> composer install
> docker compose build --no-cache
> docker compose up -d
```

### Depois de finalizada a instalação dos componentes verifique se todos os servidores estão funcionando corretamente com o comando:
```
> docker ps 
```
### Os projetos devem ser criados em diretorios separados no caminho:
```
> php/public/ 
```
### Para acesso ao banco de dados foi deixado como default 2 usuarios sendo um com perfil de acesso DBA e outro como usuario normal, segue abaixo dados para acesso:
```
> MARIADB_ROOT_PASSWORD: secret
> MARIADB_DATABASE: docker
> MARIADB_USER: developer
> MARIADB_PASSWORD: secret
```
### Link para acessar a pagina ja funcionando na maquina local: 
```
> php info: http://localhost
```

```
> phpmyadmin: http://localhost:8080
```

### Acessar o composer dentro do container PHP:
```
> docker exec -ti app_php bash
#### Dentro do container no diretorio www acesse a pasta do projeto e execute os comandos:
> composer --version
> cd [diretorio do projeto]
> composer init
#### Para atualizar o autoload
> composer dump-autoload
#### Instalar uma nova biblioteca
> composer require [nome]/[nome]
#### Atualizar dependencias:
> composer update
```
