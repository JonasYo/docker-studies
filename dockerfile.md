# Dockerfile

### O dockerfile nada mais é do que as instruções que se deve mandar para o docker para fazer o build da sua aplicação
---
#### Alguns parametro do Dockerfile:

```FROM ubuntu```

* Define a image base para montar a imagem

---
```RUN apt-get update && apt-get install apache2 && apt-get clean```

* Serve para instalar pacotes, é executao durante o BUILD da imagem. O quanto menos RUN tiver é melhor, pois é menos camada, a cada RUN executado é uma nova camada.
---

```ADD opa.txt /diretorio/```

* Adiciona um arquivo da maquina host para um diretorio do container
---

```CMD ["sh", "-c", "echo", "$HOME"```

* Define um comando a ser executado quando um container baseado nessa imagem for iniciado, esse parâmetro pode ser sobrescrito caso o container seja iniciado utilizando alguma informação de comando, como: docker run -d imagem comando, neste caso o CMD da imagem será sobrescrito pelo comando informado;
---

```LABEL Description="bla bla bla"```

* Serve para conseguir colocar metadata que você precisar do container
---

```COPY opa.txt /diretorio/```

* Copia um arquivo da sua maquina host para o seu container
---

```ENTRYPOINT ["/usr/bin/apache2ctl", "-D", "FOREGROUND"]```

* nforma qual comando será executado quando um container for iniciado utilizando esta imagem, diferentemente do CMD, o ENTRYPOINT não é sobrescrito, isso quer dizer que este comando será sempre executado.
---

```EBV meunome="Vitor Carrilho"```

* Serve para configurar variáveis de ambiente para o container
---

```EXPOSE 3333```

* Define qual a porta do container deve ser exposta
---

```USER carrilho```

* Define o usário default da imagem
---

```WORKDIR /diretorio/```

* Define o diretorio de trabalho do container, ou seja, aonde será direcionado ao abrir o container.
---

```VOLUME  /opt/host /opt/container```

* Define a image base para montar a imagem
---

```MAINTAINER Vitor Carrilho```

* Define o criado da imagem

## Build

### Para realizar o build de um dockerfiler é necessario rodar o seguinte comando:

```ONBUILD <comando>```

* Define algumas instruções que podem ser realizadas quando alguma determinada ação for executada, é basicamente como uma trigger.
---

```docker build -t nome:1.0 .```

* ```-t <nome da imagem:versão>``` Define o nome e versão da respectiva imagem gerada pelo dockerfile

* ```.``` É o diretorio em que o dockerfile está
