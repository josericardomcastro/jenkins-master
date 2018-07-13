# Jenkins em containers utilizando o Kubernetes

Projeto de instalação do [jenkins](https://jenkins.io/) em containers utilizando o orquestrados [Kubernets](https://kubernetes.io/).

# Imagem docker customizada

```
cd docker-image
docker build . -t <repository>/jenkins-master:1.0
```

Testar a Imagem

```
docker run --name docker-jenkins \
    -p 8080:8080 \
    -v jenkins_home:/var/jenkins_home \
    <repository>/jenkins-master:1.0
```


# Utilização

Execute o arquivo "00-configuration" para criação dos objetos kubernetes.

```
chmod +x 00-configuration
./00-configuration
```

Para obter a url de acessar ao jenkins, utilize o comando abaixo.

```
minikube service jenkins-service --url --all-namespace
```

# Remoção

Caso queira remover todo o projeto, execute o arquivo "99deleteall".

```
chmod +x 99-deleteall
./99-deleteall
```
