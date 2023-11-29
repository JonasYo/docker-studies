# Docker Compose

```docker-compose up -d```

* Inicia o container

---

```docker-compose ps```

* Lista os containers em execução

---

```docker-compose down```

* Finaliza a execução dos containers em background

---

#build = Indica o caminho do seu Dockerfile
build: .


#command = Executa um comando 
command: bundle exec thin -p 3000


#container_name = Dá um nome para o container 
container_name: my-web-container


#dns = indica o dns server
dns: 8.8.8.8


#dns_search = Especifica um search domain 
dns_search: example.com


#dockerfile = Especifica um Dockerfile alternativo
dockerfile: = Dockerfile-alternativo


#env_file = Especifica um arquivo com variáveis de ambiente
env_file: /varambiente/env


#environment = Adiciona variáveis de ambiente
environment:
 RACK_ENV:development


#expose = Expõe a porta do container
expose:
 - "3000"
 - "8000"


#external_links - "Linka" containers que não estão especificado no docker-compose atual
external_links:
 - redis_1
 - project_db_1:mysql


#extra_hosts = Adiciona uma entrada no /etc/hosts do container
extra_hosts:
 - "somehost:162.242.195.82"
 - "otherhost:50.31.209.229"


#image = Indica uma imagem
image: ubuntu:18.04


#labels = Adiciona metadata ao container 
labels:
 com.example.description: "Accounting webapp"
 com.example.departament: "Finance"


#links = "Linka" containers dentro do mesmo docker-compose
links:
 - db
 - db:database


#log_driver = Indica o formato do log a ser gerado, por ex: syslog, json-file, etc
log_driver: syslog
#ou
logging:
 driver:syslog


#log_opt = Indica onde mandar os logs, pode ser local ou em um syslog remoto
log_opt:
 syslog-address: "tcp://192.168.1.42:123"
#ou
logging:
 driver:syslog
 options:
  syslog-address: "tcp://192.168.1.42:123"


#net = Modo de uso da rede
net:"bridge"
net:"host"


#ports = expõe as portas do container e do host
ports:
 - "3000"
 - "80:9000"


#volumes, volume_driver = Monta volumes no container
volume
 - /var/lib/mysql
 - /opt/data:/var/lib/mysql
 - ./cache:/tmp/cache


#volumes_from = Monta volumes através de outro container
volumes_from:
 - service_name
 - service_name:ro