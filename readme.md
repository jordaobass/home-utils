# 📌 Explicação do Arquivo

## ✅ Home Assistant

- Usa a rede "host" para acessar dispositivos como Zigbee/Z-Wave.
- Monta a pasta de configuração em `/home/usuario/homeassistant`.


## ✅ MariaDB

- Banco de dados para histórico do Home Assistant.
- Usuário hass e senha hasspassword.


## ✅ PostgreSQL

- Alternativa ao MariaDB caso precise de um banco mais robusto.
- Usuário hass e senha hasspassword


# 📌 Como Rodar o Docker Compose


1️⃣ Crie as pastas para os volumes:

````shell
mkdir -p /home/usuario/homeassistant /home/usuario/mariadb /home/usuario/postgres
````

2️⃣ Salve o `docker-compose.yml` e suba os contêineres:

````shell
docker-compose up -d
````

3️⃣ Verifique os logs para confirmar que tudo está rodando:

````shell
docker ps
````

# 📌 Configurar o Home Assistant para Usar MariaDB ou PostgreSQL

Por padrão, o Home Assistant usa um banco SQLite. Para usar MariaDB ou PostgreSQL, edite o `configuration.yaml`:

✅ Para MariaDB:

````shell
recorder:
  db_url: mysql://hass:hasspassword@127.0.0.1/homeassistant?charset=utf8mb4
````
✅ Para PostgreSQL:

````shell
recorder:
  db_url: postgresql://hass:hasspassword@127.0.0.1/homeassistant
````

Após editar, reinicie o Home Assistant para aplicar as mudanças.


# 📌 Conclusão

🚀 Com esse setup, você terá um Home Assistant rápido e estável, rodando junto com MariaDB e PostgreSQL para armazenar dados.

✅ Estou executando tudo isso com um GenMachine para testes e vou migrar para um raspberry 4b ou orange berry 5 ambos com 8gb


