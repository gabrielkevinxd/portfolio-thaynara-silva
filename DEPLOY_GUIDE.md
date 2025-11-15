# 🚀 Guia de Deploy - GitHub e Vercel

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter:
- ✅ Conta no GitHub (https://github.com)
- ✅ Conta na Vercel (https://vercel.com) - pode usar login do GitHub
- ✅ Git instalado no computador
- ✅ Código pronto e testado localmente

---

## 📦 Passo 1: Preparar o Projeto

### 1.1 Verificar ficheiros importantes

Certifique-se de que estes ficheiros existem:
- ✅ `index.html` - Página principal
- ✅ `package.json` - Dependências
- ✅ `vercel.json` - Configuração da Vercel
- ✅ `.gitignore` - Ficheiros a ignorar
- ✅ `README.md` - Documentação

### 1.2 Testar localmente

```bash
npm run dev
```

Aceda a `http://localhost:3000` e teste todas as funcionalidades:
- ✅ Navegação entre secções
- ✅ Formulário de contacto
- ✅ Links externos (LinkedIn, email)
- ✅ Responsividade (mobile, tablet, desktop)

---

## 🐙 Passo 2: Enviar para o GitHub

### 2.1 Criar repositório no GitHub

1. Aceda a: https://github.com/new
2. Preencha:
   - **Nome**: `portfolio-thaynara-silva` (ou outro nome)
   - **Descrição**: "Portfólio profissional - RH e Logística"
   - **Visibilidade**: Público ou Privado
3. **NÃO** marque "Add a README file" (já temos um)
4. Clique em "Create repository"

### 2.2 Inicializar Git localmente

Abra o terminal na pasta do projeto e execute:

```bash
# Inicializar repositório Git
git init

# Adicionar todos os ficheiros
git add .

# Fazer primeiro commit
git commit -m "Initial commit: Portfólio profissional Thaynara Silva"

# Renomear branch para main
git branch -M main

# Adicionar repositório remoto (substitua SEU_USUARIO pelo seu username do GitHub)
git remote add origin https://github.com/SEU_USUARIO/portfolio-thaynara-silva.git

# Enviar para o GitHub
git push -u origin main
```

### 2.3 Verificar no GitHub

1. Aceda ao seu repositório no GitHub
2. Verifique se todos os ficheiros foram enviados
3. Confirme que o `.gitignore` está funcionando (pasta `node_modules` não deve aparecer)

---

## ☁️ Passo 3: Deploy na Vercel

### 3.1 Conectar GitHub à Vercel

1. Aceda a: https://vercel.com
2. Clique em "Sign Up" ou "Log In"
3. Escolha "Continue with GitHub"
4. Autorize a Vercel a aceder aos seus repositórios

### 3.2 Importar Projeto

1. No dashboard da Vercel, clique em "Add New..."
2. Selecione "Project"
3. Encontre o repositório `portfolio-thaynara-silva`
4. Clique em "Import"

### 3.3 Configurar Deploy

A Vercel detecta automaticamente a configuração. Confirme:

**Build & Development Settings:**
- Framework Preset: `Other` (ou `Vite` se disponível)
- Build Command: `npm run build` (ou deixe vazio)
- Output Directory: `dist` (ou deixe vazio)
- Install Command: `npm install`

**Root Directory:** `.` (raiz do projeto)

### 3.4 Deploy

1. Clique em "Deploy"
2. Aguarde 1-2 minutos (a Vercel irá:
   - Instalar dependências
   - Fazer build do projeto
   - Publicar o site)
3. Quando concluir, verá "Congratulations!" 🎉

### 3.5 Aceder ao Site

A Vercel gera automaticamente uma URL:
- **Formato**: `https://portfolio-thaynara-silva.vercel.app`
- **Personalizado**: Pode configurar domínio próprio depois

Clique em "Visit" para ver o site online!

---

## ⚙️ Passo 4: Configurações Adicionais (Opcional)

### 4.1 Domínio Personalizado

1. No dashboard da Vercel, vá em "Settings" → "Domains"
2. Adicione o seu domínio (ex: `thaynarasilva.com`)
3. Siga as instruções para configurar DNS

### 4.2 Variáveis de Ambiente (se necessário)

1. Vá em "Settings" → "Environment Variables"
2. Adicione variáveis se precisar (ex: API keys)
3. Formato: `NOME_VARIAVEL` = `valor`

### 4.3 Configurar Builds Automáticos

✅ **Já configurado automaticamente!**

Sempre que fizer push para o GitHub:
- A Vercel detecta automaticamente
- Faz novo build
- Publica a nova versão

---

## 🔄 Passo 5: Atualizações Futuras

### 5.1 Fazer alterações localmente

1. Edite os ficheiros necessários
2. Teste localmente: `npm run dev`
3. Confirme que tudo funciona

### 5.2 Enviar para o GitHub

```bash
# Ver ficheiros alterados
git status

# Adicionar ficheiros alterados
git add .

# Fazer commit com mensagem descritiva
git commit -m "Atualiza secção de experiência"

# Enviar para o GitHub
git push
```

### 5.3 Deploy Automático

✅ **Automático!** A Vercel detecta o push e faz deploy automaticamente.

Acompanhe o progresso em: https://vercel.com/dashboard

---

## 🐛 Resolução de Problemas

### Problema: "Permission denied" ao fazer push

**Solução**: Configure autenticação SSH ou use Personal Access Token

```bash
# Usar HTTPS com token
git remote set-url origin https://TOKEN@github.com/SEU_USUARIO/portfolio-thaynara-silva.git
```

### Problema: Deploy falhou na Vercel

**Soluções**:
1. Verifique os logs de build na Vercel
2. Confirme que `package.json` está correto
3. Teste `npm run build` localmente
4. Verifique se `vercel.json` está na raiz

### Problema: Formulário não envia emails

**Soluções**:
1. Verifique se a API key do Web3Forms está correta (linha 621 do `index.html`)
2. Teste o formulário localmente primeiro
3. Verifique console do browser para erros
4. Confirme que o email de destino está correto

### Problema: Site não carrega estilos

**Soluções**:
1. Verifique se Tailwind CDN está carregando
2. Limpe cache do browser (Ctrl+Shift+R)
3. Verifique console do browser para erros

---

## 📊 Checklist Final

Antes de considerar o deploy completo, verifique:

### Funcionalidades
- [ ] Todas as secções carregam corretamente
- [ ] Navegação smooth scroll funciona
- [ ] Formulário envia emails
- [ ] Links externos funcionam (LinkedIn, email)
- [ ] Responsivo em mobile, tablet e desktop

### Performance
- [ ] Site carrega em < 3 segundos
- [ ] Imagens otimizadas (se houver)
- [ ] Sem erros no console do browser

### SEO
- [ ] Título da página correto
- [ ] Meta description presente
- [ ] Links funcionam
- [ ] Estrutura semântica HTML5

### Segurança
- [ ] HTTPS ativo (Vercel faz automaticamente)
- [ ] Sem informações sensíveis expostas
- [ ] `.gitignore` configurado corretamente

---

## 🎉 Próximos Passos

Após o deploy bem-sucedido:

1. **Compartilhe o link**:
   - LinkedIn
   - CV
   - Email de candidaturas

2. **Monitore**:
   - Analytics (adicione Google Analytics se quiser)
   - Formulário (verifique se recebe emails)

3. **Mantenha atualizado**:
   - Adicione novas experiências
   - Atualize competências
   - Melhore continuamente

---

## 📧 Suporte

Se tiver problemas:
- 📖 Consulte: [DOCUMENTACAO.md](DOCUMENTACAO.md)
- 🐛 Issues: GitHub Issues do projeto
- 💬 Vercel Support: https://vercel.com/support

---

## 🔗 Links Úteis

- **GitHub Docs**: https://docs.github.com
- **Vercel Docs**: https://vercel.com/docs
- **Git Cheat Sheet**: https://education.github.com/git-cheat-sheet-education.pdf
- **Web3Forms Docs**: https://docs.web3forms.com

---

**Boa sorte com o seu portfólio! 🚀**

