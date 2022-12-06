# fortran
Imagem para projetos fortran. O foco do projeto é atender as demandas da empresa Crops Team na área 
de modelos agricola.

## Sabores
- `<prefixo>-dev` - Imagem voltada para ambientes de desenvolvimento
  * Um ambiente `miniconda` com `python 3.x`;
  * O compilador `gfortran`; 
  * A ferramenta de automação de build `cmake` 
  * O gestor de repositorio `git`;
  * O editor de text `vim`;
  * O meta-pacote `build-essential`;
  * pacotes python:
    * **C binding**: cython;
    * **ciência de dados**: numpy, scipy, scikit-learn, pandas;
    * **visualização de dados**: matplotlib, plotly, tables;
    * **jupyter**: notebook, ipykernel, jupyter_dash;
    * **teste**: pytest;
    * **etc**: fortls, isort, colorama;
<!-- - `<prefixo>-prod` - Imagem voltada para ambientes de produção -->
## Plataformas

A imagem está disponível para as seguintes plataformas:
 * `linux/amd64`
 * `linux/arm64`
## Como usar

Recomenda-se integrar a imagem com o plugin `Remote - Containers` do vscode. Você pode encontrar 
mais detalhes sobre o plugin [aqui](https://code.visualstudio.com/docs/remote/containers).


Você também pode usar a imagem para criar um container a ser executado de forma persistente, para 
posteriormente se conectar a ele. Criando um arquivo `docker-compose.yml` na raiz do seu projeto:

```yaml
version: "3.8"
services:
  org-fortran-project-dev:
    image: ghcr.io/crops-team/fortran:v1.0.0-dev
    container_name: org-fortran-project-dev
    # mantem o container ativo
    tty: true
    build:
      context: .
      dockerfile: Dockerfile.dev
    volumes:
      # mapeia o diretorio do projeto para o container  
      - .:/root/project:delegated
      # permite usar chaves ssh para acessar repositórios privados
      - ~/.ssh:/root/.ssh:ro 
```

```bash
# cria e inicia o container
$ docker-compose up -d
# acessa o container
$ docker attach org-fortran-project-dev
```

Você pode terminar a sair do container com `Ctrl + C`.


```bash
# para o container
$ docker container stop org-fortran-project-dev
```

<!-- pytest-cov, pytest-mock, pytest-benchmark -->