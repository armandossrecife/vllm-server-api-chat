# Instruções

## Servidor do Modelo LLM

Iniciar o container Nvidia com vLLM Server

### Iniciando o container do servidor de modelos LLMS

```bash
./start-vllm-server.sh
```

# Containers das aplicações (backend e frontend)

1. Pare os containers atuais (caso os containers dessa solução estejam em execução)
```bash
docker compose down
```

2. Reconstrua os containers (no caso de ajustes nos arquivos Dockerfile)
```bash
docker compose build --no-cache
```

3. Suba os containers com a nova configuração
```bash
docker compose up -d
```

4. Verifique se o backend consegue acessar o vLLM
```bash
docker compose exec backend curl http://host.docker.internal:8080/v1/models
```

## Acompanhar o log dos containers

```bash
docker compose logs -f
```

## Liste os containers dessa solução

```bash
docker compose ps -a
```