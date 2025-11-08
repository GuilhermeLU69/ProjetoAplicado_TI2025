# 🏗️ Visão Geral da Arquitetura do Sistema

## 📋 **Filosofia da Arquitetura**

O Sistema de Organização e controle dos chamados técnicos de T.I. segue uma **arquitetura em camadas** com princípios de **design orientado a domínio**, construído em FastAPI com separação clara de responsabilidades entre camadas de apresentação, negócio e dados.

### **🎯 Padrões Arquiteturais**

- **Arquitetura em Camadas**: Separação clara entre camadas de apresentação, negócio e dados
- **Padrão Repository**: Abstração de acesso a dados
- **Design Orientado a Domínio**: Lógica de negócio organizada em torno de entidades de domínio
- **Influências da Arquitetura Limpa**: Inversão de dependência para isolamento da lógica de negócio

---

## 🏛️ **Diagrama da Arquitetura do Sistema**

```
 ───────────────────────────────────────────────────────────────────────┐
│                    CAMADA DE APRESENTAÇÃO                             │
├───────────────────────────────────────────────────────────────────────┤
│  Componentes React.js   │  Roteamento SPA   │  Validação no Cliente   │
│  (interfaces dinâmicas) │  (React Router)   │  (React Hook Form)      │
├───────────────────────────────────────────────────────────────────────┤
│                        CAMADA DE NEGÓCIO                              │
├───────────────────────────────────────────────────────────────────────┤
│   Controladores Express │   Lógica de API    │   Serviços Backend     │
│   (rotas REST)          │   (validação, fluxo│   (envio de e-mails,   │
│                         │   de chamados)     │   notificações)        │
├───────────────────────────────────────────────────────────────────────┤
│                          CAMADA DE DADOS                              │
├───────────────────────────────────────────────────────────────────────┤
│    Repositórios SQL     │    ORM/Query Builder│    Integrações Futuras│
│    (CRUD com PostgreSQL)│    (Sequelize, Knex)│    (ex: APIs de ativos│
│                         │                     │     ou autenticação)  │
├───────────────────────────────────────────────────────────────────────┤
│                    CAMADA DE INFRAESTRUTURA                           │
├───────────────────────────────────────────────────────────────────────┤
│  Banco PostgreSQL  │  Containers Docker  │  Hospedagem Render/Railway │
│  Variáveis .env    │  Segurança CORS     │  Deploy contínuo CI/CD     │
└───────────────────────────────────────────────────────────────────────┘

```

---
# Explicação por camada

## Camada de Apresentação

Objetivo: Interação direta com o usuário, coleta de dados e envio de requisições para o backend

- React.js: Criação de interfaces dinâmicas e responsivas.
- React Router: Navegação entre páginas sem recarregar (SPA).
- React Hook Form: Validação de formulários no cliente, garantindo que os dados estejam corretos antes de serem enviados.

Exemplo prático: Um funcionário acessa o sistema, preenche um formulário de chamado e envia — tudo isso acontece aqui.

## Camada de Negócio



- Express define os endpoints da API REST.
- Lógica de API trata regras como abertura e fechamento de chamados.
- Serviços como envio de e-mails ou notificações são desacoplados da lógica principal.

## Camada de Negócio

Objetivo: Processar regras de negócio, controlar o fluxo de chamados e executar ações como notificações.

- Express (Node.js): Define rotas REST e trata requisições HTTP.
- Lógica de API: Valida dados, aplica regras de SLA, gerencia estados dos chamados.
- Serviços Backend: Envia e-mails, dispara notificações, integra com outros módulos.

Exemplo prático: Ao receber uma requisição de abertura de chamado, essa camada valida os dados, registra no banco e envia uma notificação ao técnico.

## Camada de Dados

Objetivo: Persistência e recuperação de dados, abstração do banco e integração com fontes externas.

- Repositórios SQL: Funções que realizam operações CRUD diretamente no PostgreSQL.
- ORM/Query Builder: Ferramentas como Sequelize ou Knex facilitam consultas e migrações.
- Integrações Futuras: APIs externas para autenticação, inventário de ativos, etc.

Exemplo prático: Quando um técnico atualiza o status de um chamado, essa camada grava a alteração no banco.

# Camada de Infraestrutura

Objetivo: Gerenciar ambiente, segurança, deploy e orquestração da aplicação.

- PostgreSQL: Banco relacional robusto para armazenar chamados, usuários e ativos.
- Docker: Criação de containers para garantir consistência entre ambientes.
- Render/Railway: Plataformas de hospedagem com suporte a Node.js e PostgreSQL.
- Variáveis .env: Configurações sensíveis como senhas e tokens.
- CORS & Segurança: Controle de acesso entre frontend e backend.
- CI/CD (GitHub Actions): Automatiza testes, builds e deploys contínuos.

Exemplo prático: Toda vez que você faz uma alteração no código e envia para o GitHub, essa camada cuida de testar e publicar automaticamente.

## 📂 **Estrutura Atual do Projeto**

```
projeto_aplicado/

```

---

## 🌐 **Arquitetura de Componentes**

### 1. Camada de Apresentação (Frontend com React.js)

🔧 **Componentes Principais**:
- Componentes React: Unidades reutilizáveis que representam partes da interface (ex: formulário de chamado, lista de chamados).
- React Router: Gerencia a navegação entre páginas sem recarregar (Single Page Application).
- Hooks (useState, useEffect): Controlam estado e ciclo de vida dos componentes.
- React Hook Form / Yup: Validação de dados no cliente antes de enviar ao backend.
- Serviço de API (Axios/Fetch): Comunicação com a API via requisições HTTP.

🧩 **Responsabilidades**:
- Renderizar interfaces dinâmicas e responsivas.
- Validar dados do usuário antes do envio.
- Exibir mensagens de erro, loading e feedback.
- Navegar entre páginas como “Abrir Chamado”, “Meus Chamados”, “Painel do Gestor”.

### 2. Camada de Negócio (Backend com Node.js + Express)

🔧 **Componentes Principais**:
- Express Router: Define rotas REST (ex: /chamados, /usuarios, /auth).
- Controllers: Recebem requisições, validam dados e delegam para serviços.
- Middlewares: Autenticação JWT, CORS, tratamento de erros.
- Services: Contêm a lógica de negócio (ex: regras de SLA, envio de notificações).
- Utils: Funções auxiliares como formatação de datas, cálculo de prazos.

🧩 **Responsabilidades**:
- Validar e processar requisições recebidas do frontend.
- Aplicar regras de negócio (ex: prazo de atendimento, escalonamento).
- Gerenciar autenticação e autorização.
- Encaminhar dados para persistência ou retorno ao cliente.

### 3. Camada de Dados (PostgreSQL + ORM)

🔧 **Componentes Principais**:
- Modelos ORM (Sequelize/Knex): Representam tabelas do banco como objetos JS.
- Repositórios: Funções que executam operações CRUD.
- Migrações: Scripts que versionam e atualizam o schema do banco.
- Conexão com o banco: Gerenciada via pool de conexões.

🧩 ***Responsabilidades***:
- Persistir dados de chamados, usuários, ativos, etc.
- Realizar consultas otimizadas e seguras.
- Gerenciar transações (ex: abertura de chamado + envio de notificação).
- Preparar dados para consumo pelo backend.

### 4. Camada de Infraestrutura

🔧 **Componentes Principais**:
- Docker: Cria containers para rodar o sistema de forma isolada e padronizada.
- Render/Railway: Hospedagem da aplicação e do banco de dados.
- GitHub Actions: Automatiza testes, builds e deploys (CI/CD).
- Arquivo .env: Armazena variáveis sensíveis (ex: senhas, tokens).
- Middleware de Segurança: CORS, rate limiting, headers seguros.

🧩 **Responsabilidades**:
- Garantir que o sistema rode de forma consistente em qualquer ambiente.
- Automatizar o processo de deploy com segurança.
- Proteger dados sensíveis e controlar acesso entre camadas.
- Monitorar logs e falhas em produção.

---

## 🗄️ **Arquitetura do Banco de Dados**

### **Visão Geral do Relacionamento de Entidades**


### **Princípios de Design do Banco de Dados**

### **Considerações de Performance**

---

## 🔐 **Arquitetura de Segurança**

### **Fluxo de Autenticação**
```
1. Credenciais do Usuário → Validação de Senha (Argon2)
2. Usuário Válido → Geração de Token JWT (HS256)
3. Requisições Subsequentes → Validação de Middleware JWT
4. Token Válido → Injeção de Contexto do Usuário
5. Acesso ao Endpoint → Autorização baseada em função
```

### **Camadas de Segurança**
- **Segurança de Transporte**: Toda comunicação entre cliente e servidor é feita via HTTPS, garantindo criptografia dos dados em trânsito
- **Autenticação**: Utilização de JWT (JSON Web Token) com assinatura segura (HS256), armazenado no cliente e validado em cada requisição.
- **Autorização**: Implementação de RBAC (Role-Based Access Control), permitindo acesso a rotas e funcionalidades conforme o perfil do usuário (ex: técnico, gestor).
- **Validação de Entrada**: No backend, os dados recebidos são validados com bibliotecas como Joi (Node.js) ou Pydantic (Python), prevenindo injeções e inconsistências.
- **Proteção CORS**: Configuração de CORS no Express para restringir origens permitidas, evitando requisições maliciosas de domínios externos.
- **Segurança de Senha**: As senhas são armazenadas com hash Argon2, considerado um dos algoritmos mais seguros atualmente, resistente a ataques de força bruta.

---

## 🚀 **Arquitetura de Implantação**

### **Ambiente de Desenvolvimento**
```
┌─────────────┐  ┌─────────────┐  ┌─────────────┐
│   FastAPI   │  │ PostgreSQL  │  │    Redis    │
│  (Local)    │  │  (Docker)   │  │  (Docker)   │
│ Porta: 8000 │  │ Porta: 5432 │  │ Porta: 6379 │
└─────────────┘  └─────────────┘  └─────────────┘
```

### 🔧 **Descrição dos Componentes**

#### FastAPI (Local)

- Framework leve e rápido para APIs REST.
- Executado diretamente na máquina local para testes rápidos.
- Porta padrão: 8000.

#### PostgreSQL (Docker)

- Banco de dados relacional robusto.
- Executado em container Docker para isolamento e consistência.
- Porta padrão: 5432.

#### Redis (Docker)

- Armazenamento em memória para cache e filas.
- Ideal para acelerar respostas e gerenciar tarefas assíncronas.
- Porta padrão: 6379.

## 🔧 **Justificativa da Escola das Tecnologias**

### **Framework Backend: FastAPI**
- **Suporte Async**: Alto desempenho async/await
- **Type Safety**: Type hints nativos do Python
- **Documentação Automática**: Geração OpenAPI/Swagger
- **Validação**: Validação automática de requisição/resposta
- **Python Moderno**: Recursos Python 3.11+

### **Banco de Dados: PostgreSQL + SQLModel**
- **Conformidade ACID**: Consistência e confiabilidade de dados
- **Suporte JSON**: Evolução de schema flexível
- **Performance**: Performance comprovada de nível empresarial
- **Type Safety**: SQLModel conecta Pydantic e SQLAlchemy
- **Suporte a Migrações**: Controle de versão Alembic

### **Autenticação: JWT**
- **Stateless**: Autenticação escalável
- **Baseado em Padrões**: Conformidade RFC 7519
- **Baseado em Função**: Autorização granular
- **Seguro**: Algoritmo HS256 com rotação de segredos

### **Infraestrutura: Docker + Docker Compose**
- **Consistência**: Paridade desenvolvimento/produção
- **Isolamento**: Isolamento de serviço e gerenciamento de dependências
- **Escalabilidade**: Pronto para orquestração de containers
- **Portabilidade**: Implantação agnóstica à nuvem

---

## 🔮 **Evolução Futura da Arquitetura**

### **Fase 1: Estado Atual (MVP)**
- ✅ Operações CRUD básicas
- ✅ Autenticação JWT
- ✅ Autorização baseada em função
- ✅ Persistência de banco de dados

### **Fase 2: Aprimoramento de Serviços (3-6 meses)**
- 🔄 Extração de camada de serviço
- 🔄 Arquitetura orientada a eventos
- 🔄 Cache avançado
- 🔄 Processamento de jobs em background

---

## 🔗 **Documentação Relacionada**

- **[Análise de Qualidade de Código](CODE_QUALITY.md)** - Padrões de design, princípios SOLID, code smells
- **[Guia de Desenvolvimento](DEVELOPMENT.md)** - Configuração e fluxos de trabalho de desenvolvimento
- **[Guia de Implantação](DEPLOYMENT.md)** - Estratégias de implantação em produção
- **[Guia de Testes](../projeto_aplicado/cli/tests/README.md)** - Arquitetura de testes e estratégias
