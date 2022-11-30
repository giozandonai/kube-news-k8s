# Projeto kube-news
## Sobre o projeto
O projeto Kube News é um projeto desenvolvido em NodeJS e um banco Postgres.

### Observações do projeto
A aplicação é exposta: <br>
**docker compose** Usando a porta 8080<br>
**Kubernetes** Usando o ingress bare metal na porta 80<br>

**srv/Dockerfile**
```
FROM node:16.15.0
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 8080
CMD ["node", "server.js"]
```

**Docker Hub - [giozandonai/kube-news](https://hub.docker.com/u/giozandonai/kube-news)**

## Subindo com DOCKER COMPOSE
`$ docker-compose --env-file .env up -d`

**Acessando a aplicação:**
`http://localhost:8080`

**Acessando pgadmin:**
`http://localhost:8090`

## Subindo com KUBERNETES
Acessar a pasta ./k8s:<br>
`kubectl apply -f . -R`<br>
`http://nome_dominio`<br>
