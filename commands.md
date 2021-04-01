
### build do Java ###
./mvnw package && java -jar target/validarCpf.jar

### Gerar imagem Docker ###
docker build -t heltonscampos/validadorcpf-concrete-novo -f Dockerfile .

### Rodar  imagem Docker e rodar localmente ###
docker run -d -p 8081:8088 --name validadorcpf-concrete-novo heltonscampos/validadorcpf-concrete-novo

###Criar a tag apontando para o repositório do Docker Hub (hub.docker.com/repository/docker/heltonscampos/validadorcpf-concrete) ###
docker tag heltonscampos/validadorcpf-concrete hub.docker.com/repository/docker/heltonscampos/validadorcpf-concrete

###subir para o dockerhub ###
docker push heltonscampos/validadorcpf-concrete-novo