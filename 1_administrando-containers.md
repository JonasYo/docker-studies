# Administrando Containers Docker

## Comandos:

```docker -v ```

* Retorna a versão do docker

---

```docker run -d -p 80:80 --name <nome-do-container> <nome-da-imagem>```

* Executar/instancia um contêiner

  * ```-d```:  Instancia e inicia o contêiner em background
  * ```-p ```:  Define a porta a ser utilizada
  * ```-rm ```:  Remove o container após ser utilizado
  * ```--name <nome-do-container>```: Permite dar um nome ao contêiner.
  * ```<nome-da-imagem>```: Nome da __imagem de base__ para o contêiner.
  * ```-it```: Usado no lugar do ‘-d’. Permite assumir o bash do contêiner logo após instanciá-lo
      * ```-i``` : é para que você tenha uma interação com o container
      * ```-t``` : é para que você tenha uma terminal

---

```docker images ```

* Listas todas as imagens baixadas pelo docker em seu computador

---

```docker start -i <container-id/name>```

* Inicia a execução de um container
    * ```-i```: Permite que você tenha uma interação com o container

---

```docker stop <container-id/name>```

* Finaliza a execução de um container

---

```docker pause <container-id/name>```

* Pausa a execução de um container

---

```docker unpause <container-id/name>```

* Despausa a execução um container

---

```docker logs <container-id/name>```

* Será exibido no terminal as ultimas ações realizadas no container
    * ```-f```: O terminal ficará exibindo todos os logs 

---

```docker ps -a ```
* Lista todos os containers em execução
    * ```-a```: Lista todos containers que estão em execução ou não; (como se fosse um historico)

---

```docker rm -f  <container-id/name>```

* Remove um container do docker
    * ```-f```: Força a exculsão do container caso ele ainda esteja em execução

---

```docker attach <container-id/name> ```
* Entrar em um container em execução

---

```Ctrl + p + q ```
* Sair de um container sem matar ele

---

```docker stats <container-id/name>```

* Visualiza o quanto o container está ultilizando de recurso

---

```docker top <container-id/name>```

* Visualiza os processos executados no container

---

```docker build .```

* Cria uma imagem

---

```docker tag <image-id> <nome-da-imagem>:<nome-da-tag>```

* Nomeia uma imagem já existente

---

```docker build -t <nome-da-imagem>:<nome-da-tag> .```

* Cria uma imagem com nome e tag

---

```docker image ls <container-id/name>```

* Será exibido uma lista com todas as imagens instaladas

---

```docker rmi <image-id/name>```

* Remove uma imagem do docker
    * ```-f```: Força a exculsão da imagem caso ela ainda esteja em execução

---

```docker system prune```

* Remove imagens, containers e networks não utilizados

---

```docker cp <diretorio-do-arquivo> <diretorio-para-salvar>```

* Copia arquivos do diretorio X para o Y

---

```docker top <container-id/name>```

* Mostra informações de processamento do container

---

```docker inspect <container-id/name>```

* Mostra as configurações do container

---

```docker stats```

* Mostra informações dos containers em execução

---