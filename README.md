
# 📅 Sistema de Agendamento SaaS para Clínicas de Estética

Este projeto é uma plataforma completa de agendamento e gestão para clínicas de estética e salões de beleza. O sistema funciona no modelo SaaS (Software as a Service), permitindo que clínicas se cadastrem, configurem seus serviços e recebam agendamentos de clientes com validação inteligente de horários.

## 🚀 Funcionalidades Principais

### 🏢 Para a Clínica (Painel Administrativo)
- **Gestão de Serviços:** Cadastro de serviços com definição personalizada de **duração (tempo)** e preço.
- **Gestão de Planos (SaaS):** Integração completa com **Stripe** para assinatura de planos:
  - **Plano Básico:** Recursos essenciais.
  - **Plano Profissional:** Recursos avançados e maior capacidade.
- **Controle de Agenda:** Visualização dos horários ocupados e disponíveis.

### 👤 Para o Cliente Final
- **Agendamento Online:** Interface intuitiva para seleção de serviços e profissionais.
- **Seleção Inteligente:** O sistema calcula automaticamente os horários disponíveis baseados na duração do serviço escolhido.

### ⚙️ Destaques Técnicos
- **Lógica Anti-Conflito:** Algoritmo robusto no backend que previne *overbooking* (dupla marcação). O sistema calcula o tempo de início + duração do serviço para bloquear a janela de tempo exata no banco de dados.
- **Pagamentos:** Integração via Webhooks com Stripe para gerenciar status de assinaturas (Ativo/Inativo/Cancelado).
- **Multi-Tenant:** Estrutura preparada para atender múltiplas clínicas simultaneamente.

## 🛠️ Tecnologias Utilizadas

- **Frontend:** Next.js (React), Tailwind CSS
- **Backend:** Node.js (API Routes do Next.js)
- **Banco de Dados:** PostgreSQL
- **Pagamentos:** Stripe API
- **ORM:** Prisma (opcional, se tiver usado)

## 📸 Screenshots

*(Coloque aqui prints das telas do seu projeto: Tela de Login, Dashboard da Clínica, Tela de Agendamento do Cliente)*
<img width="200" alt="ImageClinic_Agendar" src="https://github.com/user-attachments/assets/ba438afc-0c00-4ca6-8034-8b5342da5de6" />
<img width="300" alt="ImageClinic_Checkout" src="https://github.com/user-attachments/assets/5124ee89-70b4-447e-879b-34ab830d3fea" />


## 🔧 Como rodar o projeto

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

2. Instale as dependências:
```bash
npm install
```

3. Crie o arquivo de ambiente:
```bash
copy .env.example .env
```

4. Preencha as variáveis do arquivo `.env` com suas credenciais:
- `DATABASE_URL`
- `AUTH_SECRET`
- `AUTH_GITHUB_ID`
- `AUTH_GITHUB_SECRET`
- `AUTH_GOOGLE_ID`
- `AUTH_GOOGLE_SECRET`
- `NEXT_PUBLIC_URL`
- `NEXT_PUBLIC_STRIPE_PUBLIC_KEY`
- `STRIPE_SECRET_KEY`
- `STRIPE_SECRET_WEBHOOK_KEY`
- `STRIPE_PLAN_BASIC`
- `STRIPE_PLAN_PROFISSIONAL`
- `STRIPE_SUCCESS_URL`
- `STRIPE_CANCEL_URL`
- `CLOUDINARY_NAME`
- `CLOUDINARY_KEY`
- `CLOUDINARY_SECRET`

5. Prepare o banco de dados com Prisma:
```bash
npx prisma generate
npx prisma migrate dev
```

6. Inicie o servidor de desenvolvimento:
```bash
npm run dev
```

7. Acesse o projeto em:
```bash
http://localhost:3000
```

## 🚀 Outros comandos úteis

```bash
npm run build
npm start
npm run lint
npm run stripe:listen
```

## 📝 Observações

- Este projeto usa Next.js, Prisma, PostgreSQL, Auth.js e Stripe.
- O arquivo `.env.example` contém apenas os nomes das variáveis para facilitar a configuração no GitHub.
