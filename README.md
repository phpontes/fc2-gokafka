# GoKafka - Produtor e Consumidor Kafka com Go

Este é um projeto introdutório que demonstra como produzir e consumir mensagens do Apache Kafka utilizando a linguagem Go. O ambiente é orquestrado com Docker e foi originalmente forkado do repositório da [Full Cycle](https://github.com/codeedu/fc2-gokafka).

## 📦 Tecnologias Utilizadas

- [Go](https://golang.org/)
- [Apache Kafka](https://kafka.apache.org/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [Confluent Kafka Go Client](https://github.com/confluentinc/confluent-kafka-go)

## 🚀 Estrutura do Projeto

.
├── cmd/
│ ├── producer/ # Publica mensagens no tópico Kafka
│ │ └── main.go
│ └── consumer/ # Consome mensagens do tópico Kafka
│ └── main.go
├── docker-compose.yaml # Serviços do Kafka e ZooKeeper
├── Dockerfile # Imagem do app Go
├── go.mod / go.sum # Dependências Go


## ⚙️ Como Executar

### 1. Clone o projeto

```bash
git clone https://github.com/phpontes/fc2-gokafka.git
cd fc2-gokafka

2. Suba o ambiente Kafka com Docker Compose

docker-compose up -d

Isso irá subir os serviços:

    ZooKeeper

    Kafka

    Kafka UI (em http://localhost:8080 para monitoramento)

3. Execute o consumidor

go run cmd/consumer/main.go

Ele ficará escutando o tópico teste.

4. Execute o produtor (em outro terminal)

go run cmd/producer/main.go

Isso publicará uma mensagem de exemplo no tópico Kafka ("transferencia").

Você verá a mensagem sendo recebida pelo consumer.
📺 Kafka UI

A interface gráfica para visualização dos tópicos Kafka estará disponível em:

http://localhost:8080

Use o host kafka:9092 nas configurações da UI se necessário.
🧪 Exemplo de Fluxo

    O producer publica a mensagem "transferencia" no tópico "teste".

    O consumer consome essa mensagem e imprime no console.

📚 Créditos

Projeto baseado no curso da Full Cycle.