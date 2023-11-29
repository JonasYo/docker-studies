# Limintando CPU e Memória do Docker

## Memória RAM:


```docker inspect <container-id/name> ```

* Mostra todas as informações do container 
---

```docker inspect <container-id/name> | grep -i mem```

* Mostra as informações da memoria RAM do container selecionado, se o item "memomy" retornar 0, é por que ainda não foi definido um limite para a memoria ram do container
---

```docker run -ti --memory 512M --name <nome-do-container> <imagem> /bin/bash```
### Executar/instanciar um contêiner (básico):

* ```-ti```: Permite assumir o bash do contêiner logo após instanciá-lo
    * ```-t``` : é para que você tenha uma terminal
    * ```-i``` : é para que você tenha uma interação com o container
* ```-d```: Usado no lugar do ‘-ti’. Instancia e inicia o contêiner em background
* ```--name <nome_container>```: Permite dar um nome ao contêiner. Recomendável para que possa tratá-lo por um nome ao invés de seu ID sha1.
* ```<nome_imagem>```: Imagem de base para o contêiner.
* ```--memory 512m```: Define a quantidade de memoria RAM disponivel no container na criação dele.

---

```docker update --memory 256m <container-id/name> ```

* Atribui uma nova quantidade de memoria ram ao container
---

## Processamento

#### O limite total de processamento no docker é equivalente a 2048, assumindo que são 3 containers, um com 1024, e dois com 512, o primeiro vaiter ter uso de 50%, enquanto os outros dois apenas 25%.



```docker inspect <container-id/name> | grep -i cpu```

* Mostra as informações da CPU do container selecionado, o item ChpuShares mostra a quantidade de processamento usada no container.
---

```docker run -ti --cpu-shares 1024 --name <nome-do-container> <imagem> /bin/bash```
### Executar/instanciar um contêiner (básico):

* ```-ti```: Permite assumir o bash do contêiner logo após instanciá-lo
    * ```-t``` : é para que você tenha uma terminal
    * ```-i``` : é para que você tenha uma interação com o container
* ```-d```: Usado no lugar do ‘-ti’. Instancia e inicia o contêiner em background
* ```--name <nome_container>```: Permite dar um nome ao contêiner. Recomendável para que possa tratá-lo por um nome ao invés de seu ID sha1.
* ```<nome_imagem>```: Imagem de base para o contêiner.
* ```--cpu-share 1024```: Define a quantidade de recurso que a CPU vai poder usar.

---

```docker update --cpu-shares 512 <container-id/name> ```

* Atribui uma nova quantidade de moria ram ao container
---