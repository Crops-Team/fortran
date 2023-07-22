## [unreleased]

### Adicionado

### Modificado

### Corrigido

### Removido

### Outros

- A documentação e`devcontainer.json` tratam de forma equivocada o
  suporte docker dentro de contêineres de desenvolvimento. Não se
  trata de DinD (docker in docker) mas sim de DooD (docker out of docker).

---

## [1.3.2] : [1.3.1...1.3.2]

### Adicionado

- Adiciona `curl` na imagem de produção, para health checks.
- Adiciona o pacote python `pytest-xdist` permitindo abordar os testes de forma paralela
  no futuro.

## [1.3.1] : [1.3.0...1.3.1]

### Adicionado

- Adiciona `gdb` e e o pacote python para o `docker SDK` a imagem de desenvolvimento.

### Corrigido

- corrige `devcontainer` em `README.md` na verdade foi adicionado suporte para 
  `docker-out-of-docker`.

## [1.3.0] : [1.2.1...1.3.0]

### Adicionado

- Suporte a `docker-in-docker` na imagen de desenvolvimento.
- Pacotes `setuptols`, `wheel`, e `build`, úteis em ambientes de 
  desenvolvimento python para fazer a construção de pacotes e wheels.

### Modificado

- Imagens `<sufixo>-deploy` agora serão `<sufixo>-prod`.

### Removido

- Imagens de produção foram simplificadas e tiveram diversos pacotes 
  removidos. Agora dependências extras devem ser instalados sob demanda 
  por cada projeto.


### Outros

- Adiciona `.devcontainer` para testes de `docker-in-docker`.
- Passa a incluir um `CHANGELOG.md`


## [1.2.1] : [1.2.0...1.2.1]

### Corrigido

- Corrige nome do ambiente `conda` nas imagen de desenvolvimento, estava 
  sendo nomeado como `deploy`.

## [1.2.0] : [1.0.0...1.2.0]

---

## [1.0.0] : [0.5.0...1.0.0]

---

## [0.5.0]

- Primeiro release.

[unreleased]: https://github.com/Crops-Team/fortran/compare/v1.3.2...HEAD

[1.3.2]: https://github.com/Crops-Team/fortran/releases/tag/v1.3.2
[1.3.1...1.3.2]: https://github.com/Crops-Team/fortran/compare/v1.3.1...v1.3.2

[1.3.1]: https://github.com/Crops-Team/fortran/releases/tag/v1.3.1
[1.3.0...1.3.1]: https://github.com/Crops-Team/fortran/compare/v1.3.0...v1.3.1

[1.3.0]: https://github.com/Crops-Team/fortran/releases/tag/v1.2.1
[1.2.1...1.3.0]: https://github.com/Crops-Team/fortran/compare/v1.2.1...v1.3.0

[1.2.1]: https://github.com/Crops-Team/fortran/releases/tag/v1.2.1
[1.2.0...1.2.1]: https://github.com/Crops-Team/fortran/compare/v1.2.0...v1.2.1

[1.2.0]: https://github.com/Crops-Team/fortran/releases/tag/v1.2.0
[1.0.0...1.2.0]: https://github.com/Crops-Team/fortran/compare/v1.0.0...v1.2.0

[1.0.0]: https://github.com/Crops-Team/fortran/releases/tag/v1.0.0
[0.5.0...1.0.0]: https://github.com/Crops-Team/fortran/compare/v0.5.0...v1.0.0

[0.5.0]: https://github.com/Crops-Team/fortran/releases/tag/v0.5.0