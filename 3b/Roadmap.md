# Roadmap — Mini Sistema de Gerenciamento de Games

Este documento registra todas as etapas de planejamento, desenvolvimento, testes e implantação do sistema. O progresso é atualizado em tempo real conforme as tarefas são validadas.

---

## 1. Planejamento e Análise
- [x] Analisar requisitos e regras de negócio
- [x] Definir arquitetura (separação Backend Node.js/Mongoose e Frontend Vanilla HTML/CSS/JS)
- [x] Definir modelo de dados com Mongoose (campos, tipos, validações e timestamps)
- [x] Definir contrato de endpoints REST e códigos HTTP
- [x] Criar estrutura inicial e arquivos de documentação (`Roadmap.md`, `Contexto.md`, `api.md`, `README.md`, `.gitignore`)

## 2. Backend (Node.js + Express + MongoDB)
- [ ] Inicializar projeto Node.js (`package.json` e dependências: `express`, `mongoose`, `cors`, `dotenv`)
- [ ] Configurar conexão com MongoDB compatível com Vercel Serverless (cache de conexão)
- [ ] Criar model `Game` com validações estritas (nome obrigatório, preço numérico e não negativo, etc.)
- [ ] Implementar middleware de tratamento de erros e validação de JSON mal formatado
- [ ] Criar controllers para CRUD de games (`listar`, `obterPorId`, `criar`, `atualizar`, `excluir`)
- [ ] Criar rotas da API (`GET /games`, `GET /games/:id`, `POST /games`, `PUT /games/:id`, `DELETE /games/:id`)
- [ ] Configurar CORS com suporte a origens locais e produção
- [ ] Criar script de seed (`seed.js`) com games populares para teste inicial
- [ ] Configurar `.env.example` e `vercel.json` para deploy serverless na Vercel

## 3. Frontend (HTML5 + CSS3 + Vanilla JavaScript)
- [ ] Criar layout semântico `index.html` com tema gamer moderno e responsivo
- [ ] Desenvolver `style.css` com paleta neon gamer (dark theme, glassmorphism, badges, animações sutis)
- [ ] Implementar `app.js` com requisições `fetch()` à API REST
- [ ] Implementar listagem dinâmica de games em cards com fallback de foto
- [ ] Implementar modal/formulário de cadastro de novo game com pré-visualização de imagem
- [ ] Implementar fluxo de edição de game com preenchimento automático do formulário
- [ ] Implementar exclusão com diálogo de confirmação gamer
- [ ] Adicionar sistema de notificações visuais (Toasts de sucesso e erro)
- [ ] Adicionar filtro/busca em tempo real por nome e plataforma

## 4. Testes e Validação
- [ ] Testar conexão com banco de dados MongoDB
- [ ] Testar requisições da API via cURL / scripts de teste automatizado:
  - [ ] `POST /games` (sucesso e validação de campos obrigatórios/inválidos)
  - [ ] `GET /games` (listagem completa)
  - [ ] `GET /games/:id` (id válido existente, id inexistente e id mal formatado)
  - [ ] `PUT /games/:id` (atualização válida e campos inválidos)
  - [ ] `DELETE /games/:id` (exclusão de game existente e inexistente)
- [ ] Testar tratamento de JSON corrompido / erros de validação com retorno `{ erro, detalhes }`
- [ ] Testar interface visual no frontend (fluxos de usuário, responsividade mobile/desktop)
- [ ] Validar comportamento sem quebra quando a URL da imagem falhar (fallback visual)

## 5. Preparação para Deploy & Entrega
- [ ] Validar arquivos de configuração da Vercel (`vercel.json`, `backend/api/index.js`)
- [ ] Garantir que `.gitignore` exclua `.env` e `node_modules`
- [ ] Finalizar `api.md` com exemplos práticos em cURL e respostas HTTP
- [ ] Finalizar `Contexto.md` com o estado final e decisões técnicas
- [ ] Finalizar `README.md` com instruções detalhadas de instalação e execução
