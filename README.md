# 🎊 Plataforma de Gerenciamento de Eventos - GitParty

---

## 📖 Sobre o Projeto

Esta API foi desenvolvida para facilitar o gerenciamento de eventos e inscrições, substituindo processos manuais por uma solução automatizada.

A aplicação permite organizar participantes, eventos e inscrições de forma eficiente, evitando duplicidade de cadastro e excesso de participantes.

---

## 🎯 Objetivo

- 📌 Organizar participantes  
- 🎟️ Controlar vagas dos eventos  
- 🔄 Gerenciar cancelamentos  
- 🚫 Evitar inscrições duplicadas  

---

## 🧰 Tecnologias Utilizadas

- Node.js  
- Express  
- MariaDB  
- Prisma  
- JavaScript  

---

## 📁 Estrutura do Projeto

```bash
src/
 ┣ controllers/
 ┣ models/
 ┣ routes/
 ┣ services/
 ┗ app.js / server.js
```

---

## 📌 Entidades do Sistema

### 👥 Participantes

- id  
- nome  
- email  
- senha  
- data_cadastro  

---

### 📆 Eventos

- id  
- titulo  
- descricao  
- data_evento  
- local  
- capacidade_maxima  
- status (ativo, cancelado, encerrado)  

---

### 📝 Inscrições

- id  
- usuario_id  
- evento_id  
- data_inscricao  
- status (confirmada, lista_espera, cancelada)  

---

## ⚙️ Regras de Negócio

### 🔢 Limite de participantes

Cada evento possui uma capacidade máxima.  
Ao atingir o limite, novas inscrições vão para a lista de espera.

---

### 🚫 Inscrição duplicada

Um usuário não pode se inscrever mais de uma vez no mesmo evento.

---

### ⏳ Cancelamento

O cancelamento só pode ser feito até 24 horas antes do evento.

---

### 🔄 Lista de espera

Quando alguém cancela, o primeiro da lista de espera assume automaticamente a vaga.

---

## ▶️ Como executar o projeto

### 1. Clone este repositório
```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
```

### 2. Acesse a pasta do projeto
```bash
cd gitparty
```

### 3. Instale as dependências
```bash
npm install
```

### 4. Execute o servidor
```bash
npm start
```

Ou, se estiver usando nodemon:

```bash
npm run dev
```

---

## 🌐 Rotas da API

### 👥 Usuários

- POST /usuarios/cadastrar  
- GET /usuarios/listar  

---

### 📆 Eventos

- POST /eventos/cadastrar  
- GET /eventos/listar  

---

### 📝 Inscrições

- POST /inscricoes/cadastrar  
- GET /inscricoes/listar  
- PUT /inscricoes/atualizar/:id  
- DELETE /inscricoes/excluir/:id  
