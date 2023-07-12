# fortran
Imagem para projetos fortran. O foco do projeto é atender as demandas da empresa Crops Team na área 
de modelos agricola.

## Sabores
- `<prefixo>-dev` - Imagem voltada para ambientes de desenvolvimento
  * Um ambiente `miniconda` com `python 3.8`;
  * Ferramentas extras: `build-essential`, `git`, `gfortran`, `libgdal-dev`, `cmake`, `vim`, `curl`,
    `docker-ce`, `docker-ce-cli`, `containerd.io`, `docker-compose-plugin`;
    
  > **OBS**: Para contêineres DinD (docker in docker) é preciso rodar o contêner com `--privileged`
    assim como montar o `docker.socket` no container. Observe que isto envolve questões de segurança
    relevantes para o seu uso.

  * pacotes python: `setuptools>=46.0`,`wheel`, `build`, `Cython`, `pandas`, `geopandas`, 
    `openpyxl`, `numpy`, `scipy`, `scikit-learn`, `flask`, `flask_httpauth`, `flask_caching`, 
    `gunicorn`, `notebook`, `ipykernel`, `jupyter_dash`, `colorama`, `tables`, `plotly`,
    `matplotlib`, `isort`, `fortls`, `pytest`, `pytest-html`,

- `<prefixo>-prod` - Imagem voltada para ambientes de produção
  * Um ambiente `miniconda` com `python 3.8`;
  * Biblioteca `libgfortran`
## Plataformas

A imagem está disponível para as seguintes plataformas:
 * `linux/amd64`
 * `linux/aarch64`

## Como usar

Recomenda-se integrar a imagem com o plugin `Remote - Containers` do vscode. Você pode encontrar 
mais detalhes sobre o plugin [aqui](https://code.visualstudio.com/docs/remote/containers).


Você também pode usar a imagem para criar um container a ser executado de forma persistente, para 
posteriormente se conectar a ele. Criando um arquivo `docker-compose.yml` na raiz do seu projeto:

```yaml
version: "3.8"
services:
  org-fortran-project-dev:
    image: ghcr.io/crops-team/fortran:v1.3.0-dev
    volumes:
      # mapeia o diretorio do projeto para o container  
      - .:/root/project:delegated
      # permite usar chaves ssh para acessar repositórios privados
      - ~/.ssh:/root/.ssh:ro 
    # mantem o container ativo    
    tty: true
```

```bash
# cria e inicia o container em modo detached
$ docker-compose up -d
# acessa o container
$ docker attach org-fortran-project-dev
```

Você pode sair do container com `Ctrl + C`.


```bash
# termina o container
$ docker container stop <nome-do-contêiner>
```
<!-- pytest-cov, pytest-mock, pytest-benchmark -->