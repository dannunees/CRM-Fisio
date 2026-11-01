# 🌿 LANV Fisioterapia — Sistema de Gestão Clínica, Prontuário Eletrônico & Evolução com IA

![Next.js](https://img.shields.io/badge/Next.js-15-black?style=flat-square&logo=next.js)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4.1-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google_Gemini-2.5_Flash-4285F4?style=flat-square&logo=google&logoColor=white)

O **LANV Fisioterapia** é uma aplicação web completa de gestão clínica desenvolvida especificamente para fisioterapeutas e clínicas de reabilitação. O projeto une um **design clínico sofisticado e minimalista** a ferramentas práticas do dia a dia do consultório: prontuário eletrônico, avaliação ortopédica e goniometria (ADM), geração de evoluções clínicas formais com Inteligência Artificial (**Google Gemini 2.5 Flash**), impressão de relatórios em formato **A4** e controle financeiro com alertas de cobrança.

---

## 🎯 Finalidade e Motivação do Projeto

Na rotina clínica de fisioterapia, profissionais frequentemente enfrentam três grandes gargalos:
1. **Tempo gasto na burocracia do prontuário:** Transformar anotações rápidas feitas entre um paciente e outro em registros técnicos formais (exigidos pelos padrões do COFFITO) consome horas semanais.
2. **Fragmentação de dados clínicos:** Testes ortopédicos especiais, medidas de goniometria (ADM), escala de dor (EVA) e evolução diária muitas vezes ficam espalhados em fichas de papel ou planilhas desconectadas.
3. **Gestão financeira e cobranças delicadas:** Controlar pacotes mensais, sessões avulsas, reembolsos de convênios e lembrar pacientes sobre vencimentos de forma educada e humanizada.

O **LANV Fisioterapia** foi criado para resolver esses pontos em uma interface única, limpa e centrada na experiência real de atendimento em saúde.

---

## ✨ Funcionalidades Principais

### 1. 📋 Gestão de Pacientes (Prontuário Eletrônico)
- Cadastro completo de pacientes (Nome, WhatsApp/Telefone, E-mail, Data de Nascimento, Ocupação/Esporte, Diagnóstico/Queixa Principal).
- Classificação por modalidade (**Particular** ou **Convênio / Reembolso**) e status clínico (*Em Tratamento*, *Avaliação Inicial*, *Alta Clínica*, *Pausado*).
- Busca instantânea por nome, queixa, telefone ou convênio, além de filtros rápidos por pendências financeiras.

### 2. 🩺 Avaliação Fisioterapêutica, Testes Especiais e Goniometria (ADM)
- **Escala Visual Analógica de Dor (EVA 0 a 10):** Seletor interativo com classificação automática de intensidade (*Sem Dor*, *Dor Leve*, *Dor Moderada*, *Dor Intensa*) e mapeamento topográfico.
- **Testes Ortopédicos e Especiais:** Catálogo integrado com os principais testes clínicos (*Teste de Lasègue*, *Teste de Jobe*, *Teste de Neer*, *Teste de Hawkins-Kennedy*, *Teste de Lachman*, *Teste de Slump*, *Teste de Patrick/FABER*, *Teste de Spurling*, *Teste de Phalen*, entre outros) + suporte a testes personalizados, lateralidade e resultado (*Positivo*, *Negativo*, *Inconclusivo*).
- **Goniometria, ADM e Força Muscular (Escala de Oxford):** Registro de graus aferidos vs. graus de referência normal, presença de arco doloroso, força muscular (`1/5` a `5/5`) e barra visual comparativa de mobilidade articular.

### 3. ✨ Evolução Clínica Diária Assistida por IA (`gemini-2.5-flash`)
- Campo de **Observações Rápidas e Informais**, onde a fisioterapeuta digita em linguagem natural o que foi feito na sessão (ex: *"paciente relata melhora na lombar, mas dor ao flexionar, fizemos liberação miofascial e exercícios de estabilização"*).
- Seleção rápida de procedimentos realizados na sessão (*Liberação Miofascial*, *Terapia Manual Ortopédica*, *Mobilização Neural*, *Estabilização Segmentar*, *Pilates Clínico*, etc.) e registro de EVA inicial vs. EVA pós-sessão.
- Botão **"Gerar Evolução com IA"**: Conecta-se ao modelo **`gemini-2.5-flash`** (Google Gemini API) para estruturar automaticamente o relato em um **documento técnico, formal e ético padrão COFFITO**, dividido em:
  1. *Avaliação Subjetiva e Estado Funcional (S)*
  2. *Exame Objetivo e Conduta Fisioterapêutica Realizada (O)*
  3. *Resposta Terapêutica e Plano de Seguimento (A/P)*
- Possui também um **estruturador clínico COFFITO local (fallback inteligente)** caso o usuário queira testar a aplicação imediatamente sem configurar uma chave de API.

### 4. 🖨️ Impressão de Prontuário e Evolução em Folha A4 (Print / PDF)
- Visualizador de relatório formal com o **timbre oficial da LANV Fisioterapia** (Dados da clínica, Fisioterapeuta responsável, registro CREFITO, CNPJ e endereço).
- Permite escolher entre imprimir **todas as evoluções** do paciente ou **apenas uma sessão específica**, além de incluir ou ocultar o quadro de testes ortopédicos e goniometria.
- Estilização `@media print` dedicada para **Folha A4**, ocultando menus, botões e barras laterais na hora de imprimir ou salvar como PDF.

### 5. 💰 Controle Financeiro e Simulador de Cobrança Amigável
- Lançamento de receitas atreladas ao paciente (Descrição do pacote/sessão, Valor em R$, Data de Vencimento, Forma de Pagamento: PIX, Cartão, Transferência, Reembolso).
- **Status Manual em 1 Clique:** Alteração rápida entre `Pago`, `Pendente` e `Atrasado`.
- **Alerta Automático de Vencimento:** Sempre que um pagamento está `Pendente` (ou `Atrasado`) e a data de vencimento é **hoje ou anterior**, o sistema exibe um alerta visual claro no painel e no prontuário do paciente.
- **Simulador de Lembrete/Cobrança Amigável (WhatsApp e E-mail):** Gera automaticamente uma mensagem cordial e personalizada lembrando o vencimento, informando a chave PIX da clínica e pedindo gentilmente para desconsiderar caso o pagamento já tenha sido efetuado. Permite simular o disparo (registrando data/hora do último lembrete) ou abrir diretamente o WhatsApp Web / cliente de e-mail.

---

## 🎨 Diretrizes de Design (UI/UX)

- **Estética de Clínica de Alto Padrão:** Interface clara, limpa e acolhedora, fugindo de dashboards escuros genéricos.
- **Paleta de Cores:** Fundo em *Off-White* (`#F8FAFC`), cartões em branco puro (`#FFFFFF`) com bordas suaves (`border-slate-200/80`), destaques em **Azul Petróleo** (`#0F766E` / `teal-700`), **Verde Menta** (`#10B981` / `emerald-600`) para indicadores positivos e **Âmbar** para alertas financeiros.
- **Persistência de Dados:** Armazenamento completo via `localStorage` estruturado (`ClinicStorage`), garantindo que pacientes, testes, evoluções, configurações e lançamentos financeiros permaneçam salvos no navegador ao recarregar a página.

---

## 🛠️ Tecnologias Utilizadas

- **[Next.js 15 (App Router)](https://nextjs.org/)** — Framework React full-stack com rotas de API serverless.
- **[React 19](https://react.dev/) & [TypeScript](https://www.typescriptlang.org/)** — Tipagem estrita de entidades clínicas e componentes modulares.
- **[Tailwind CSS 4](https://tailwindcss.com/)** — Estilização utilitária responsiva e regras de impressão `@media print` A4.
- **[Google Gen AI SDK (`@google/genai`)](https://ai.google.dev/)** — Integração com o modelo `gemini-2.5-flash` para redação técnica de prontuários.
- **[Lucide React](https://lucide.dev/)** — Ícones clínicos e de interface modernos e minimalistas.

---

## 📂 Estrutura do Projeto

```text
├── src/
│   ├── app/
│   │   ├── api/
│   │   │   └── generate-evolution/
│   │   │       └── route.ts            # Rota de API integrada ao Google Gemini (gemini-2.5-flash)
│   │   ├── globals.css                 # Estilos globais e formatação @media print para folha A4
│   │   ├── layout.tsx                  # Layout raiz e configuração tipográfica (Inter)
│   │   └── page.tsx                    # Workspace principal da clínica e navegação de prontuários
│   ├── components/
│   │   ├── BillingReminderModal.tsx    # Simulador de disparo de cobrança amigável (WhatsApp / E-mail)
│   │   ├── ClinicSettingsModal.tsx     # Configurações do timbre da clínica, PIX e chave Gemini API
│   │   ├── ClinicalEvolutionTab.tsx    # Módulo de evolução diária com IA e histórico de sessões
│   │   ├── FinancialTab.tsx            # Controle financeiro, status manual e alertas de vencimento
│   │   ├── PatientModal.tsx            # Modal de cadastro e edição de pacientes
│   │   ├── PhysicalAssessmentTab.tsx   # Avaliação física, escala EVA, testes ortopédicos e ADM
│   │   └── PrintReportModal.tsx        # Relatório formal A4 com timbre para impressão / PDF
│   ├── lib/
│   │   ├── seed-data.ts                # Dados clínicos de demonstração e catálogos ortopédicos
│   │   └── storage.ts                  # Camada de persistência no localStorage
│   └── types/
│       └── clinic.ts                   # Interfaces TypeScript do domínio fisioterapêutico
├── package.json
├── tsconfig.json
└── README.md
```

---

## 🚀 Como Executar o Projeto Localmente

### 1. Pré-requisitos
- **Node.js** (versão 18 ou superior)
- **npm** (ou yarn / pnpm)

### 2. Instalação
Clone o repositório e instale as dependências:

```bash
git clone https://github.com/SEU-USUARIO/lanv-fisioterapia.git
cd lanv-fisioterapia
npm install
```

### 3. Configuração da Chave da API Google Gemini (Opcional)
Você pode configurar sua chave da API Gemini de duas maneiras:
- **Pela própria interface do sistema:** Clique no botão **"Clínica / IA"** no canto superior direito e insira sua chave do Google AI Studio.
- **Via variável de ambiente:** Crie um arquivo `.env.local` na raiz do projeto:

```env
GEMINI_API_KEY=sua_chave_aqui
```

> 💡 **Nota:** Mesmo que nenhuma chave seja informada, o sistema conta com um motor clínico de contingência que estrutura automaticamente as anotações no padrão COFFITO para que todas as funcionalidades possam ser testadas imediatamente.

### 4. Iniciando o Servidor de Desenvolvimento

```bash
npm run dev
```

Acesse **`http://localhost:3000`** no seu navegador.

---

## 📄 Licença

Este projeto foi desenvolvido para fins de portfólio e modernização da gestão em clínicas de fisioterapia (**LANV Fisioterapia**).

# CRM-Fisio
