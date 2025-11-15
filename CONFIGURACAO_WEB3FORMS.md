# Configuração do Formulário com Web3Forms

## ✅ Solução SEM Cadastro Necessário!

O Web3Forms é um serviço gratuito que **não requer cadastro**. Apenas precisa gerar uma chave de acesso.

## Passos para Configurar (2 minutos):

### 1. Obter a Chave de Acesso

1. Aceda a: **https://web3forms.com/**
2. Preencha o formulário simples:
   - **Email:** `thaynara.ds@hotmail.com` (onde quer receber os emails)
   - Clique em "Get Your Access Key"
3. **Copie a chave gerada** (exemplo: `a1b2c3d4-e5f6-7890-abcd-ef1234567890`)

### 2. Atualizar o Código

1. Abra o ficheiro `index.html`
2. Encontre a linha com: `value="YOUR_ACCESS_KEY"`
3. Substitua `YOUR_ACCESS_KEY` pela chave que copiou
4. Exemplo: `value="a1b2c3d4-e5f6-7890-abcd-ef1234567890"`

### 3. Testar

1. Faça commit e push para o GitHub
2. Deploy na Vercel
3. Teste o formulário no site ao vivo

## Formato do Email Recebido:

Quando alguém preencher o formulário, receberá um email assim:

```
Assunto: Nova mensagem do portfólio - Thaynara Silva

Nome: [Nome da pessoa]
Email: [Email da pessoa]
Mensagem: [Mensagem enviada]
```

## Vantagens do Web3Forms:

✅ **Gratuito** - Até 250 submissões/mês
✅ **Sem cadastro** - Apenas gera uma chave
✅ **Sem backend** - Funciona direto do frontend
✅ **Spam protection** - Proteção automática contra spam
✅ **Email direto** - Recebe os emails diretamente na sua caixa de entrada

## Deploy na Vercel:

1. Faça push do código para o GitHub
2. Aceda a: https://vercel.com
3. Conecte o repositório GitHub
4. A Vercel detecta automaticamente e faz o deploy
5. Pronto! O site estará online

## Nota:

O ficheiro `vercel.json` já está configurado para garantir que o `index.html` seja servido corretamente.

