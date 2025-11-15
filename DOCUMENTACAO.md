# 📚 Documentação Técnica - Portfólio Thaynara Silva

## 📋 Índice

1. [Visão Geral](#visão-geral)
2. [Arquitetura](#arquitetura)
3. [Estrutura de Ficheiros](#estrutura-de-ficheiros)
4. [Componentes](#componentes)
5. [Estilos e Design System](#estilos-e-design-system)
6. [Funcionalidades](#funcionalidades)
7. [Configuração e Deploy](#configuração-e-deploy)
8. [Manutenção](#manutenção)

---

## 🎯 Visão Geral

Portfólio profissional de página única (SPA) desenvolvido para apresentar a experiência e competências de Thaynara Silva no mercado europeu, com foco em Recursos Humanos e Logística.

### Tecnologias Utilizadas

- **HTML5**: Estrutura semântica
- **CSS3**: Estilos personalizados
- **Tailwind CSS**: Framework utility-first (via CDN)
- **JavaScript (Vanilla)**: Interatividade e lógica do formulário
- **Vite**: Servidor de desenvolvimento
- **Web3Forms**: Serviço de envio de emails

### Características Principais

✅ Design responsivo (mobile-first)
✅ Paleta de cores profissional (azul marinho/cinza)
✅ Animações suaves e transições
✅ Formulário de contacto funcional
✅ SEO otimizado
✅ Performance otimizada

---

## 🏗️ Arquitetura

### Estrutura de Página Única (SPA)

O site é composto por uma única página HTML dividida em secções:

```
┌─────────────────────────────────────┐
│          Header/Hero                │  ← Apresentação principal
├─────────────────────────────────────┤
│          Sobre Mim                  │  ← Introdução profissional
├─────────────────────────────────────┤
│         Competências                │  ← Hard & Soft Skills
├─────────────────────────────────────┤
│         Experiência                 │  ← Percurso profissional
├─────────────────────────────────────┤
│          Formação                   │  ← Educação e certificações
├─────────────────────────────────────┤
│          Contacto                   │  ← Formulário e links
├─────────────────────────────────────┤
│           Footer                    │  ← Copyright e informações
└─────────────────────────────────────┘
```

### Fluxo de Navegação

1. **Smooth Scroll**: Navegação suave entre secções via âncoras
2. **Responsividade**: Layout adaptável (mobile → tablet → desktop)
3. **Interatividade**: Hover states, focus states, loading states

---

## 📁 Estrutura de Ficheiros

```
Thaynara_Silva/
│
├── index.html                    # Página principal (SPA)
├── package.json                  # Dependências do projeto
├── package-lock.json             # Lock de dependências
├── vite.config.js                # Configuração do Vite
├── vercel.json                   # Configuração da Vercel
├── .gitignore                    # Ficheiros ignorados pelo Git
├── .env                          # Variáveis de ambiente (não commitado)
├── .env.example                  # Exemplo de variáveis de ambiente
│
├── README.md                     # Documentação principal
├── DOCUMENTACAO.md               # Esta documentação técnica
├── CONFIGURACAO_WEB3FORMS.md     # Guia de configuração do formulário
│
└── node_modules/                 # Dependências (não commitado)
```

### Descrição dos Ficheiros

#### `index.html`
Ficheiro principal contendo toda a estrutura, estilos e scripts do portfólio.

**Secções:**
- `<head>`: Meta tags, fontes, Tailwind config, estilos personalizados
- `<header>`: Hero section com apresentação principal
- `<main>`: Conteúdo principal (Sobre, Competências, Experiência, Formação, Contacto)
- `<footer>`: Copyright e informações
- `<script>`: Lógica do formulário e interatividade

#### `package.json`
Gestão de dependências e scripts do projeto.

```json
{
  "scripts": {
    "dev": "vite",           // Servidor de desenvolvimento
    "build": "vite build",   // Build para produção
    "preview": "vite preview" // Preview do build
  }
}
```

#### `vite.config.js`
Configuração do servidor de desenvolvimento Vite.

```javascript
{
  server: {
    port: 3000,    // Porta do servidor
    open: true     // Abre o browser automaticamente
  }
}
```

#### `vercel.json`
Configuração para deploy na Vercel.

```json
{
  "rewrites": [
    { "source": "/", "destination": "/index.html" }
  ]
}
```

---

## 🧩 Componentes

### 1. Header/Hero Section

**Localização**: Linhas 70-174 (index.html)

**Estrutura**:
```html
<header class="hero-bg">
  <nav>...</nav>           <!-- Navegação principal -->
  <div class="grid">
    <div>                  <!-- Coluna esquerda: Texto -->
      <h1>...</h1>         <!-- Título principal -->
      <p>...</p>           <!-- Subtítulo -->
      <div>...</div>       <!-- CTAs -->
    </div>
    <div>                  <!-- Coluna direita: Resultados -->
      <ul>...</ul>         <!-- Cards de resultados -->
    </div>
  </div>
</header>
```

**Características**:
- Background gradiente radial
- Layout responsivo (2 colunas em desktop, 1 em mobile)
- Tipografia hierárquica (font-light para elegância)
- CTAs com hover states

### 2. Sobre Mim

**Localização**: Linhas 176-209

**Estrutura**:
```html
<section id="sobre">
  <div class="lg:w-2/3">...</div>    <!-- Texto principal -->
  <div class="lg:w-1/3">...</div>    <!-- Destaques rápidos -->
</section>
```

**Características**:
- Card branco com sombra
- Layout 2/3 - 1/3 em desktop
- Lista de destaques rápidos

### 3. Competências

**Localização**: Linhas 211-369

**Estrutura**:
```html
<section id="competencias">
  <div class="grid md:grid-cols-2">
    <div>                           <!-- Hard Skills -->
      <ul>
        <li>                        <!-- Skill com ícone -->
          <svg>...</svg>
          <span>...</span>
        </li>
      </ul>
    </div>
    <div class="bg-slate-900">      <!-- Soft Skills (fundo escuro) -->
      <ul>
        <li>                        <!-- Skill numerada -->
          <span>1</span>
          <span>...</span>
        </li>
      </ul>
    </div>
  </div>
</section>
```

**Características**:
- Grid de 2 colunas
- Hard Skills: fundo branco com ícones SVG
- Soft Skills: fundo escuro com numeração
- Contraste visual para diferenciação

### 4. Experiência

**Localização**: Linhas 366-515

**Estrutura**:
```html
<section id="experiencia" class="bg-slate-900">
  <article>                         <!-- Experiência 1 (RH) -->
    <header>
      <p>2018 — 2021</p>
      <h3>Recursos Humanos / Administração</h3>
      <p>KGG Distribuidor de Papel de Parede</p>
    </header>
    <ul>
      <li>                          <!-- Resultado com ícone check -->
        <svg>...</svg>
        <span>...</span>
      </li>
    </ul>
  </article>
  <article>...</article>            <!-- Experiência 2 (Logística) -->
</section>
```

**Características**:
- Fundo escuro (bg-slate-900)
- Cards com backdrop-blur
- Ícones de check para resultados
- Hover states nos cards

### 5. Formação

**Localização**: Linhas 517-552

**Estrutura**:
```html
<section id="formacao" class="bg-slate-900 md:grid-cols-2">
  <div>                             <!-- Texto introdutório -->
    <h2>...</h2>
    <p>...</p>
  </div>
  <div>                             <!-- Cards de formação -->
    <div>                           <!-- Licenciatura -->
      <p>Licenciatura</p>
      <h3>Gestão de Recursos Humanos</h3>
      <p>Universidade Estadual · 2014 — 2017</p>
    </div>
    <div>                           <!-- Certificação -->
      <p>Certificação Profissional</p>
      <h3>Técnico de Contabilidade — IEFP</h3>
      <p>Instituto do Emprego e Formação Profissional · 2022</p>
    </div>
  </div>
</section>
```

**Características**:
- Fundo escuro consistente
- Grid 2 colunas (texto + cards)
- Cards com bg-white/5

### 6. Contacto

**Localização**: Linhas 554-680

**Estrutura**:
```html
<section id="contacto">
  <div>                             <!-- Informações -->
    <h2>Vamos Conversar?</h2>
    <p>...</p>
    <div>                           <!-- Links diretos -->
      <a href="mailto:...">...</a>
      <a href="https://linkedin.com/...">...</a>
    </div>
  </div>
  <form id="contact-form">          <!-- Formulário -->
    <input type="hidden" name="access_key" value="..." />
    <div>                           <!-- Campo Nome -->
      <label>...</label>
      <input name="nome" />
    </div>
    <div>                           <!-- Campo Email -->
      <label>...</label>
      <input name="email" />
    </div>
    <div>                           <!-- Campo Mensagem -->
      <label>...</label>
      <textarea name="mensagem"></textarea>
    </div>
    <button type="submit">          <!-- Botão submit -->
      <span id="submit-text">Enviar Mensagem</span>
      <span id="submit-loading" class="hidden">A enviar...</span>
    </button>
    <p id="form-feedback" class="hidden"></p>
  </form>
</section>
```

**Características**:
- Layout 2 colunas (info + formulário)
- Validação HTML5
- Estados de loading
- Feedback visual (sucesso/erro)
- Integração com Web3Forms

### 7. Footer

**Localização**: Linhas 682-688

**Estrutura**:
```html
<footer class="bg-slate-900">
  <div>
    <p>© <span id="year"></span> Thaynara Silva. Todos os direitos reservados.</p>
    <p>Disponível para projetos em Portugal e União Europeia.</p>
  </div>
</footer>
```

**Características**:
- Ano dinâmico (JavaScript)
- Layout flexível responsivo

---

## 🎨 Estilos e Design System

### Paleta de Cores

```css
:root {
  --brand: #0F172A;        /* Azul marinho escuro */
  --accent: #0EA5E9;       /* Azul claro (accent) */
  --accentDark: #0369A1;   /* Azul médio (hover) */
  
  /* Escala de cinzas (Tailwind) */
  --slate-50: #f8fafc;
  --slate-100: #f1f5f9;
  --slate-200: #e2e8f0;
  --slate-300: #cbd5e1;
  --slate-400: #94a3b8;
  --slate-600: #475569;
  --slate-700: #334155;
  --slate-900: #0f172a;
}
```

### Tipografia

**Fonte**: Inter (Google Fonts)
**Pesos**: 300 (light), 400 (regular), 500 (medium), 600 (semibold), 700 (bold)

```css
/* Hierarquia tipográfica */
h1: text-4xl md:text-5xl lg:text-6xl font-light
h2: text-3xl font-semibold
h3: text-xl font-semibold
p: text-base (16px)
small: text-sm (14px)
```

### Espaçamento

```css
/* Sistema de espaçamento (baseado em Tailwind) */
gap-4: 1rem (16px)
gap-6: 1.5rem (24px)
gap-8: 2rem (32px)
gap-10: 2.5rem (40px)
gap-12: 3rem (48px)

/* Padding de secções */
py-16: 4rem (64px)
py-24: 6rem (96px)
```

### Componentes Reutilizáveis

#### Card
```css
.card {
  border-radius: 1.5rem;        /* rounded-3xl */
  box-shadow: 0 25px 45px -20px rgba(15, 23, 42, 0.25);
  padding: 2rem;                /* p-8 */
  background: white;
  border: 1px solid #f1f5f9;    /* ring-1 ring-slate-100 */
}
```

#### Skill Icon
```css
.skill-icon {
  width: 2.75rem;
  height: 2.75rem;
  border-radius: 9999px;
  background: linear-gradient(135deg, #0ea5e920, #0ea5e960);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  color: #0369a1;
}
```

#### Hero Background
```css
.hero-bg {
  background: 
    radial-gradient(circle at top left, rgba(14, 165, 233, 0.25), rgba(14, 165, 233, 0)),
    radial-gradient(circle at 20% 80%, rgba(14, 165, 233, 0.35), rgba(14, 165, 233, 0)),
    #0f172a;
}
```

### Breakpoints (Tailwind)

```css
sm: 640px   /* Tablets pequenos */
md: 768px   /* Tablets */
lg: 1024px  /* Desktops */
xl: 1280px  /* Desktops grandes */
```

---

## ⚙️ Funcionalidades

### 1. Smooth Scroll

**Implementação**: CSS nativo
```css
html {
  scroll-behavior: smooth;
}
```

**Uso**: Links de navegação com âncoras
```html
<a href="#sobre">Sobre Mim</a>
```

### 2. Formulário de Contacto

**Localização**: Linhas 689-743 (JavaScript)

**Fluxo**:
```
1. Utilizador preenche formulário
2. Clica em "Enviar Mensagem"
3. JavaScript intercepta o submit
4. Desabilita botão e mostra "A enviar..."
5. Envia dados para Web3Forms via fetch API
6. Recebe resposta
7. Mostra feedback (sucesso/erro)
8. Reabilita botão
9. Limpa formulário (se sucesso)
```

**Código**:
```javascript
form.addEventListener("submit", async (event) => {
  event.preventDefault();
  
  // Loading state
  submitBtn.disabled = true;
  submitText.classList.add("hidden");
  submitLoading.classList.remove("hidden");
  
  try {
    const formData = new FormData(form);
    const response = await fetch(form.action, {
      method: "POST",
      body: formData,
      headers: { Accept: "application/json" }
    });
    
    const result = await response.json();
    
    if (response.ok && result.success) {
      // Sucesso
      feedback.textContent = "Mensagem enviada!";
      feedback.className = "success-class";
      form.reset();
    } else {
      throw new Error(result.message);
    }
  } catch (error) {
    // Erro
    feedback.textContent = "Erro ao enviar mensagem.";
    feedback.className = "error-class";
  } finally {
    // Restaurar botão
    submitBtn.disabled = false;
    submitText.classList.remove("hidden");
    submitLoading.classList.add("hidden");
  }
});
```

**Validação**:
- HTML5 native validation (`required`, `type="email"`)
- Feedback visual em tempo real
- Mensagens de erro/sucesso

### 3. Ano Dinâmico no Footer

**Código**:
```javascript
const year = document.getElementById("year");
year.textContent = new Date().getFullYear();
```

---

## 🚀 Configuração e Deploy

### Desenvolvimento Local

1. **Instalar dependências**:
```bash
npm install
```

2. **Iniciar servidor de desenvolvimento**:
```bash
npm run dev
```

3. **Aceder**:
```
http://localhost:3000
```

### Build para Produção

```bash
npm run build
```

Gera ficheiros otimizados na pasta `dist/`.

### Deploy na Vercel

#### Opção 1: Via Interface Web

1. Aceder a https://vercel.com
2. Clicar em "Add New Project"
3. Conectar repositório GitHub
4. Deploy automático

#### Opção 2: Via CLI

```bash
npm i -g vercel
vercel
```

### Variáveis de Ambiente

**Desenvolvimento**:
- Criar ficheiro `.env` na raiz
- Adicionar: `WEB3FORMS_ACCESS_KEY=sua_chave`

**Produção (Vercel)**:
1. Dashboard da Vercel → Settings → Environment Variables
2. Adicionar: `WEB3FORMS_ACCESS_KEY` = `sua_chave`

**Nota**: A API key está hardcoded no HTML por simplicidade. Para maior segurança em projetos maiores, considere usar variáveis de ambiente com um backend.

---

## 🔧 Manutenção

### Atualizar Conteúdo

#### Adicionar Nova Experiência

1. Localizar secção `#experiencia` (linha 366)
2. Duplicar estrutura `<article>`
3. Atualizar:
   - Datas
   - Título do cargo
   - Nome da empresa
   - Bullet points de resultados

#### Adicionar Nova Competência

**Hard Skills** (linha 233):
```html
<li class="flex items-start gap-4">
  <svg>...</svg>  <!-- Ícone -->
  Nova competência aqui
</li>
```

**Soft Skills** (linha 338):
```html
<li class="flex items-start gap-4">
  <span>5</span>  <!-- Número -->
  Nova soft skill aqui
</li>
```

#### Atualizar Formação

Localizar secção `#formacao` (linha 517) e editar os cards.

### Atualizar Estilos

**Cores**:
- Editar configuração Tailwind (linhas 15-28)

**Tipografia**:
- Alterar fonte no link Google Fonts (linha 10)
- Atualizar `font-family` no CSS (linha 38)

### Otimização de Performance

#### Imagens (se adicionar)
```html
<img 
  src="imagem.jpg" 
  alt="Descrição" 
  loading="lazy"
  width="800" 
  height="600"
/>
```

#### Fontes
- Usar `font-display: swap` (já implementado)
- Preconnect aos domínios (já implementado)

#### Scripts
- Manter JavaScript inline para reduzir requests
- Minificar em produção (Vite faz automaticamente)

### SEO

#### Meta Tags Recomendadas (adicionar ao `<head>`):

```html
<!-- Open Graph -->
<meta property="og:title" content="Thaynara Silva | RH & Logística" />
<meta property="og:description" content="Profissional multifuncional em Braga, Portugal" />
<meta property="og:type" content="website" />
<meta property="og:url" content="https://seu-dominio.com" />
<meta property="og:image" content="https://seu-dominio.com/og-image.jpg" />

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Thaynara Silva | RH & Logística" />
<meta name="twitter:description" content="Profissional multifuncional em Braga, Portugal" />
<meta name="twitter:image" content="https://seu-dominio.com/twitter-image.jpg" />

<!-- Canonical -->
<link rel="canonical" href="https://seu-dominio.com" />
```

### Acessibilidade

**Checklist**:
- ✅ Contraste de cores adequado (WCAG AA)
- ✅ Navegação por teclado funcional
- ✅ Labels em todos os inputs
- ✅ Estrutura semântica HTML5
- ✅ Alt text em imagens (quando adicionar)

**Melhorias futuras**:
- Adicionar `aria-label` em links de ícones
- Implementar skip links
- Adicionar `aria-live` para feedback do formulário

---

## 📊 Análise de Código

### Métricas

- **Total de linhas**: ~750
- **HTML**: ~680 linhas
- **CSS**: ~40 linhas
- **JavaScript**: ~55 linhas
- **Dependências**: 1 (Vite para dev)

### Qualidade

✅ **Código limpo**: Indentação consistente, nomes descritivos
✅ **Modular**: Secções bem definidas
✅ **Responsivo**: Mobile-first approach
✅ **Performático**: Poucos requests, assets otimizados
✅ **Manutenível**: Estrutura clara, comentários onde necessário

### Boas Práticas Implementadas

1. **HTML Semântico**: `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`
2. **CSS Utility-First**: Tailwind para consistência
3. **JavaScript Moderno**: `async/await`, `fetch API`, `FormData`
4. **Acessibilidade**: Labels, contraste, navegação por teclado
5. **SEO**: Meta tags, estrutura semântica
6. **Performance**: Lazy loading, preconnect, minificação

---

## 🔐 Segurança

### API Key

⚠️ **Nota de Segurança**: A API key do Web3Forms está exposta no código frontend. Isto é aceitável porque:

1. Web3Forms permite keys públicas
2. A key está limitada ao domínio
3. Não há dados sensíveis expostos

**Para maior segurança** (opcional):
- Implementar backend proxy
- Usar variáveis de ambiente
- Adicionar rate limiting

### Formulário

✅ **Proteções implementadas**:
- Validação client-side (HTML5)
- Validação server-side (Web3Forms)
- Proteção contra spam (Web3Forms)
- HTTPS obrigatório (Vercel)

---

## 📝 Changelog

### v1.0.0 (2024)
- ✅ Estrutura inicial do portfólio
- ✅ Design responsivo
- ✅ Integração com Web3Forms
- ✅ Deploy na Vercel
- ✅ Documentação completa

---

## 🤝 Contribuir

Para contribuir com melhorias:

1. Fork do repositório
2. Criar branch: `git checkout -b feature/nova-funcionalidade`
3. Commit: `git commit -m 'Adiciona nova funcionalidade'`
4. Push: `git push origin feature/nova-funcionalidade`
5. Abrir Pull Request

---

## 📧 Suporte

Para questões ou suporte:
- Email: thaynara.ds@hotmail.com
- LinkedIn: https://www.linkedin.com/in/thaynaradsilva

---

**Última atualização**: Novembro 2024
**Versão**: 1.0.0
**Autor**: Thaynara Silva

