# Configurando opções de rede(drivers) dos containers

```docker network ls```

* Será listado as configurações de redes 

---

```docker network create -d <driver> <name>```

* ```-d```: Para delimitar o driver
* ```<driver>```: Tipo do driver a ser utilizado
* ```<nome>```: Nome da rede

---

```docker network rm <name>```

* ```<nome>```: Nome da rede

---

```docker network prune```

* Será removido todas as redes não utilizadas

---

```docker run -ti --dns 8.8.8.8 <imagem> ```

* ```-ti```: Permite assumir o bash do contêiner logo após instanciá-lo
    * ```-t``` : é para que você tenha uma terminal
    * ```-i``` : é para que você tenha uma interação com o container
* ```--dns <dns>```: Serve para passar um servidor de dns que irá responder para as suas requisições
* ```<nome_imagem>```: Imagem de base para o contêiner.

---
```--hostname catota```

* ```--hostname <nome>```: Define o nome do container dentro dele.

---
```--link container1```
* ```--link <container>```: Serve para linkar a rede de dois containers

---
```--expose 80```

* ```--expose <porta>```: Expõe a porta de um container na máquina host
---
```--publish 8080:80 (or --p)```

* ```--expose <porta>```: Binda a porta especificada pelo host com a porta do container
---
```--mac-address 12:34:de:b0:6b:51```

* ```--mac-address <endereco_mac>```: Personaliza o endereço mac do container

---
```--network container:<name|id>```

* ```----network container:<name|id>```: Serve para definir qual será a rede em que o container usará, podendo ser o host ou de outro container

---
