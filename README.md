# Introdução ao Desenvolvimento de Sistemas Web - Integração Backend e Frontend

Este é o repositório que centraliza e orquestra a aplicação completa de desenvolvimento web, unificando o backend, frontend das duas disciplinas em um único ambiente local usando Docker Compose.

## Subprojetos Independentes

Os componentes deste projeto são versionados e mantidos em repositórios separados no GitHub:

1.  **Backend (Java / Spring Boot)**:
    *   Pasta local: `backend/`
    *   Repositório: [https://github.com/LuisOtavioSantos/FLD679533.git](https://github.com/LuisOtavioSantos/FLD679533.git)
2.  **Frontend (TypeScript / Next.js)**:
    *   Pasta local: `frontend/`
    *   Repositório: [https://github.com/LuisOtavioSantos/FLD6795336CET.git](https://github.com/LuisOtavioSantos/FLD6795336CET.git)

---

## Como Clonar e Inicializar o Projeto

Para obter todo o ambiente configurado com as pastas do frontend e backend integradas, utilize o comando de clonagem recursiva do Git:

```bash
git clone --recursive https://github.com/LuisOtavioSantos/Intro-o-Ao-Desenvolvimento-de-Sistemas-Web.git
```

Se você já clonou o repositório sem a flag `--recursive`, inicialize os submódulos rodando dentro da raiz:

```bash
git submodule update --init --recursive
```

---

## Como Executar a Aplicação (Orquestração Docker Compose)

A partir da raiz deste repositório, você pode iniciar toda a pilha de serviços.

### 1. Pré-requisitos
*   Crie o arquivo `.env` dentro da pasta `backend/` contendo suas credenciais (use `backend/.env-template` como modelo).

### 2. Modo Desenvolvimento com Watch (Hot-Reloading em tempo real)
Para rodar a aplicação monitorando e atualizando automaticamente qualquer mudança no código do backend ou frontend:

```bash
docker compose -f docker-compose-dev.yml watch
```
Ou use a flag `--watch` diretamente:
```bash
docker compose -f docker-compose-dev.yml up --build --watch
```

### 3. Modo Desenvolvimento Tradicional (Background)
Para rodar os contêineres clássicos em segundo plano:

```bash
docker compose -f docker-compose-dev.yml up -d
```

### 4. Parar a Execução
```bash
docker compose -f docker-compose-dev.yml down
```
