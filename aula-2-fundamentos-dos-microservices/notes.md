# Fundamentos dos Microservices

### Representação arquitetura monolítica

![](./assets/representacao-monolito.png)

* Serviços aglomerados em uma única aplicação

* Único banco de dados (único ponto de falha)

### Representação arquitetura de microsserviços

![](./assets/representacao-microsservico.png)

* Serviços distribuídos e independentes

* Banco de dados para cada aplicação

### Fundamentos

* Envolve desde conceitos técnicos, financeiras e gerenciais moldados principalmente sobre a necessidade do negócio

* A mudança de paradigma para microsserviços requer também uma mudança equivalente na estrutura da organização. Não só uma questão técnica. É também cultural e organizacional

* É um subconjunto dos conceitos de sistemas distribuídos modernos

### Sincronia de dados em sistemas distribuídos

* **IMPORTANTE**: não há como garantir alta disponibilidade com consistência forte ao mesmo tempo em uma arquitetura de microsserviços com dados distribuídos

  > **Consistência de dados**: garantir a integridade dos dados, sem divergência e nem ambiguidade de dados dentro da aplicação
   ![](./assets/exemplo-consistencia-de-dados.png)

### Disponibilidade VS Consistência forte

> **Teorema CAP**

* Para garantir a alta disponibilidade em sistemas distribuídos com dados compartilhados é necessário a sincronia de dados de forma assíncrona e não bloqueante, gerando uma **consistência eventual**

  > **Consistência eventual**: os dados podem estar momentaneamente desatualizados ou não replicados ao serem consultados

* **Exemplo**

  ![](./assets/disponibilidade-vs-consistencia-forte.png)

### UUIDs

* Meio de criar dados com identificadores únicos afim de evitar conflitos/ambiguidades

* **OBS**: no contexto de microsserviços, identificados sequenciais não é uma boa abordagem

  ![](./assets/identificaores-uuid.png)

* São identificadores temporais universalmente exclusivos e essenciais para a sincronia de dados distribuídos

* **Vantagens**

  * Geração simples

  * Fácil replicação de dados

  * Garantia de uma maior manutenibilidade

  * Únicos em qualquer base de dados

### Acoplamento em microsserviços

* **Não** existe desacoplamento absoluto entre os microsserviços, entretanto é possível ter um **baixo acoplamento**

* **Exemplo**

  ![](./assets/exemplo-acoplamento.png)

### Disponibilidade em microsserviços

* **OBS**: não existe 100% de disponibilidade, pois sempre existirá alguma dependência entre os serviços da aplicação

* **Exemplo**

  ![](./assets/disponibilidade.png)

### Distribuição das bases de dados em microsserviços

* É possível ter compartilhamento de bancos de dado entre serviços

* **OBS**: é comum essa prática no início do processo de migração de monolito para microsserviço

### Padrões de microsserviços

> É fundamental durante a elaboração de uma aplicação de microsserviços

* 1 base de dado por serviço

  * **Vantagem**: diminui o acoplamento 

  * **Desvantagem**: é necessário saber lidar corretamente com os **dados distribuídos** (sincronização de dados e com a consistência eventual)
