# docker-server
### Projeto com o objetivo de disponibilizar servicos de PHP, banco de dados MariaDb com um servidor nginx para o desenvolvimento de projetos utilizando estas tecnologias. Tambem foi desenvolvido e testado diretamente no linux Mint e caso seja usado no windows precisara de configurações adicionais para funcionar corretamente.
``` Este projeto foi desenvolvido com o objetivo de treinar o uso do Docker e não deve ser utilizado em produção, somente como teste ou referência. ```

## Tecnologias utilizadas:
> Docker <br />
> PHP 8.4-fpm <br />
> nginx - Versão mais atualizada possivel <br />
> MariaDb - Versão mais atualizada possivel <br />

## Requerimentos:
> git <br />
> docker <br />
> composer <br />

## Comandos:
### Os comandos abaixo seram utilizados para desde o download do repositorio ate a instalacao dos componentes do Docker:

```
git clone https://github.com/distro104/docker-server.git

cd docker-server

composer install

docker compose build

docker compose up -d
```

### Depois de finalizada a instalação dos componentes verifique se todos os servidores estão funcionando corretamente com o comando:
``` 
docker ps 
```

### Os projetos devem ser criados em diretorios separados no caminho:
```
php/public/ 
``` 

#### Link para acessar a pagina ja funcionando na maquina local: [http://localhost](#http://localhost)

