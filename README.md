# 🍔 iMordy

<p align="center">
  <strong>Abriu, pediu, chegou! 🚀</strong>
</p>

<p align="center">
  Um novo jeito de pedir comida, conectando clientes, restaurantes e entregadores em uma única plataforma.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-em%20desenvolvimento-FFC857?style=for-the-badge" />
  <img src="https://img.shields.io/badge/platform-mobile%20%7C%20web-000000?style=for-the-badge" />
  <img src="https://img.shields.io/badge/license-MIT-FFFFFF?style=for-the-badge" />
</p>

---

## 🍟 Sobre o projeto

O **iMordy** é uma plataforma de **delivery de comida** criada para conectar consumidores e estabelecimentos de forma simples, rápida e intuitiva.

A ideia é oferecer uma experiência completa:

> **Abriu → escolheu → pediu → acompanhou → chegou.**

O projeto nasceu com o objetivo de construir uma alternativa moderna para o mercado de delivery, com foco em **experiência do usuário, praticidade e tecnologia**.

O iMordy pretende reunir em um único ecossistema:

* 👤 Clientes
* 🍔 Restaurantes
* 🛵 Entregadores
* 💳 Pagamentos
* 📦 Pedidos
* 📍 Localização e acompanhamento
* ⭐ Avaliações
* 🔔 Notificações

---

## 💡 A ideia

Hoje, pedir comida já faz parte da rotina de milhões de pessoas.

Porém, plataformas de delivery podem apresentar problemas como:

* 💰 taxas elevadas para estabelecimentos;
* 📱 experiências pouco intuitivas;
* 🏪 dificuldade para pequenos restaurantes ganharem visibilidade;
* 🛵 problemas de logística;
* 🔎 dificuldade para encontrar novos estabelecimentos;
* 📊 pouca flexibilidade para os restaurantes administrarem seus pedidos.

O **iMordy** nasce com a proposta de explorar uma experiência diferente.

### 🎯 Nossa missão

> **Facilitar a conexão entre quem quer comer e quem quer vender comida.**

---

# 🚀 Funcionalidades

O projeto está sendo desenvolvido de forma modular, permitindo que novas funcionalidades sejam adicionadas conforme a plataforma evolui.

### 👤 Cliente

* Cadastro e login
* Autenticação segura
* Gerenciamento de perfil
* Cadastro de endereço
* Busca por restaurantes
* Visualização de cardápios
* Adição de produtos ao carrinho
* Criação de pedidos
* Acompanhamento do pedido
* Histórico de pedidos
* Avaliação de restaurantes

### 🍔 Restaurante

* Cadastro do estabelecimento
* Gerenciamento do restaurante
* Gerenciamento de cardápio
* Cadastro de produtos
* Controle de disponibilidade
* Recebimento de pedidos
* Atualização do status dos pedidos
* Histórico de vendas

### 🛵 Entregador

* Cadastro
* Disponibilidade para entregas
* Visualização de pedidos disponíveis
* Aceitação de entregas
* Atualização do status da entrega
* Histórico de entregas

### 📦 Pedidos

O fluxo principal do pedido deverá seguir uma estrutura semelhante a:

```text
🛒 Carrinho
   ↓
📋 Pedido criado
   ↓
🏪 Restaurante recebeu
   ↓
👨‍🍳 Pedido em preparação
   ↓
📦 Pedido pronto
   ↓
🛵 Saiu para entrega
   ↓
🏠 Pedido entregue
```

---

# 🏗️ Arquitetura

O iMordy está sendo pensado desde o início com uma arquitetura preparada para crescimento.

A aplicação utiliza uma abordagem baseada em **serviços independentes**, permitindo separar responsabilidades e facilitar manutenção, testes e evolução do sistema.

Uma visão simplificada:

```text
                    ┌──────────────────┐
                    │     iMordy       │
                    │   Mobile / Web   │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │       BFF        │
                    │ Backend for      │
                    │ Frontend        │
                    └────────┬─────────┘
                             │
              ┌──────────────┼──────────────┐
              │              │              │
              ▼              ▼              ▼
       ┌────────────┐ ┌────────────┐ ┌────────────┐
       │ Auth       │ │ Restaurant │ │   Orders   │
       │ Service    │ │  Service   │ │  Service   │
       └────────────┘ └────────────┘ └────────────┘
              │              │              │
              └──────────────┼──────────────┘
                             ▼
                    ┌──────────────────┐
                    │    Database      │
                    └──────────────────┘
```

A arquitetura poderá evoluir conforme novas necessidades surgirem.

---

# 🔐 Autenticação

O projeto possui um serviço dedicado à autenticação e autorização.

A autenticação utiliza **JWT (JSON Web Token)** para permitir que usuários autenticados acessem os recursos protegidos da aplicação.

Fluxo simplificado:

```text
Cliente
   │
   │ Login
   ▼
Auth Service
   │
   │ Validação
   ▼
JWT
   │
   ▼
Cliente
   │
   │ Authorization: Bearer <token>
   ▼
API protegida
```

Isso permite separar a responsabilidade de autenticação das demais funcionalidades da plataforma.

---

# 🛠️ Tecnologias

## Backend

O backend está sendo desenvolvido principalmente utilizando:

* ☕ **Java**
* 🌱 **Spring Boot**
* 🔐 **Spring Security**
* 🎫 **JWT**
* 🗄️ **PostgreSQL**
* 🐘 **MyBatis**
* 📡 **OpenFeign**
* 🧪 **JUnit**
* 🎭 **Mockito**
* 🐳 **Docker**

## Frontend

A interface da plataforma será construída utilizando tecnologias modernas para aplicações web/mobile.

Entre elas:

* ⚛️ **React**
* ▲ **Next.js**
* 📘 **TypeScript**
* 💅 **Styled Components**

---

> Alguns módulos ainda estão em planejamento e serão implementados conforme o desenvolvimento do projeto avançar.

---

# 🎨 Identidade visual

O iMordy possui uma identidade visual pensada para transmitir:

* 🍔 Alimentação
* ⚡ Velocidade
* 😋 Apetite
* 🖤 Modernidade
* ✨ Simplicidade

### Paleta principal

| Cor        | Hex       | Utilização                |
| ---------- | --------- | ------------------------- |
| 🟨 Amarelo | `#FFC857` | Cor principal / destaque  |
| ⬛ Preto    | `#000000` | Logo / textos / contraste |
| ⬜ Branco   | `#FFFFFF` | Fundos / contraste        |
| 🟫 Bege    | `#F5E6CC` | Fundos secundários        |

A cor **#FFC857** é utilizada como elemento de destaque da identidade, enquanto o preto fornece contraste e personalidade à marca.

---

# 🧩 Principais módulos

### 🔐 Authentication

Responsável por:

* cadastro;
* login;
* geração de JWT;
* validação de tokens;
* autorização;
* segurança da aplicação.

### 👤 Users

Responsável pelo gerenciamento dos usuários da plataforma.

### 🏪 Restaurants

Responsável pelos estabelecimentos e seus cardápios.

### 🛒 Orders

Responsável pela criação e gerenciamento dos pedidos.

### 🛵 Delivery

Responsável pela logística e entregas.

### 💳 Payments

Responsável pelo processamento e controle dos pagamentos.

---

# 🗺️ Roadmap

O desenvolvimento do iMordy será realizado por etapas.

### 🟡 Fase 1 — Fundação

* [x] Definição do nome **iMordy**
* [x] Definição do conceito da marca
* [x] Definição do slogan
* [x] Definição inicial da identidade visual
* [x] Estrutura inicial do backend
* [x] Serviço de autenticação
* [x] Implementação inicial de JWT
* [ ] Estrutura inicial do frontend

### 🟠 Fase 2 — MVP

* [ ] Cadastro de usuários
* [ ] Login
* [ ] Cadastro de restaurantes
* [ ] Cadastro de produtos
* [ ] Cardápio
* [ ] Carrinho
* [ ] Criação de pedidos
* [ ] Histórico de pedidos
* [ ] Integração frontend/backend

### 🔵 Fase 3 — Delivery

* [ ] Cadastro de entregadores
* [ ] Distribuição de pedidos
* [ ] Atualização de status
* [ ] Rastreamento
* [ ] Notificações
* [ ] Histórico de entregas

### 🟣 Fase 4 — Escala

* [ ] Sistema de avaliações
* [ ] Cupons
* [ ] Promoções
* [ ] Fidelidade
* [ ] Recomendações
* [ ] Métricas para restaurantes
* [ ] Observabilidade
* [ ] Escalabilidade da infraestrutura

---

# 🧪 Qualidade

O projeto busca manter boas práticas de desenvolvimento desde sua construção.

Entre elas:

* ✅ Testes unitários
* ✅ Separação de responsabilidades
* ✅ Código organizado
* ✅ Arquitetura modular
* ✅ Tratamento de exceções
* ✅ Validação de dados
* ✅ Autenticação e autorização
* ✅ Controle de versões com Git
* ✅ Documentação das APIs

---

# 🌱 Desenvolvimento

O iMordy ainda está em **desenvolvimento ativo**.

Novas funcionalidades, serviços e decisões arquiteturais serão adicionados conforme o projeto evoluir.

A ideia é construir o sistema de maneira incremental:

```text
              💡 Ideia
                 │
                 ▼
            🏗️ Arquitetura
                 │
                 ▼
             💻 Código
                 │
                 ▼
              🧪 Testes
                 │
                 ▼
             🚀 Deploy
                 │
                 ▼
            📈 Evolução
                 │
                 └──────────► 💡
```

---

# 🤝 Contribuindo

Contribuições são bem-vindas!

Caso queira contribuir:

```bash
# Clone o projeto
git clone <repository-url>

# Entre no diretório
cd iMordy

# Crie uma branch
git checkout -b feature/minha-feature

# Faça suas alterações

# Commit
git commit -m "feat: adiciona minha feature"

# Push
git push origin feature/minha-feature
```

Depois, abra um **Pull Request**.

---

# 📌 Convenção de commits

O projeto utiliza uma convenção baseada em **Conventional Commits**.

Exemplos:

```text
feat: adiciona cadastro de restaurante
fix: corrige autenticação JWT
refactor: reorganiza serviço de pedidos
test: adiciona testes do usuário
docs: atualiza README
chore: atualiza dependências
```

---

# 🔮 Visão

O objetivo do iMordy não é simplesmente criar mais um aplicativo de delivery.

A visão é construir um **ecossistema completo para alimentação**, onde tecnologia, restaurantes, entregadores e consumidores estejam conectados.

```text
        👤 CLIENTE
             │
             │
             ▼
        🍔 iMordy
       ╱     │     ╲
      ╱      │      ╲
     ▼       ▼       ▼
🏪 RESTAURANTE  🛵 ENTREGADOR  💳 PAGAMENTO
     │                   │
     └─────────┬─────────┘
               ▼
          🏠 CLIENTE
```

---

# 🍔 iMordy

## **Abriu, pediu, chegou!**

O iMordy está sendo construído para transformar a experiência de pedir comida em algo **simples, rápido e agradável**.

**Do primeiro clique até a última mordida.** 🍔

---

<p align="center">
  <strong>iMordy © 2026</strong>
</p>

<p align="center">
  Feito com ☕ + 💻 + 🍔
</p>
