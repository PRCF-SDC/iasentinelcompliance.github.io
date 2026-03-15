# AI-Sentinel Guard — Homepage

## Deploy no GitHub Pages (Passo a Passo)

### Pré-requisitos
- Conta no GitHub (gratuita): https://github.com/signup

---

### PASSO 1: Criar o Repositório

1. Acesse https://github.com/new
2. Em **Repository name**, digite exatamente:
   ```
   iasentinelcompliance.github.io
   ```
   > ⚠️ O nome DEVE ser `seuusuario.github.io` para funcionar como site principal.
   > Se seu username no GitHub for diferente, use `seuusername.github.io`
3. Marque **Public**
4. **NÃO** marque "Add a README file"
5. Clique em **Create repository**

---

### PASSO 2: Fazer Upload dos Arquivos

#### Opção A — Pelo navegador (mais fácil):
1. Na página do repositório recém-criado, clique em **"uploading an existing file"**
2. Arraste os arquivos:
   - `index.html` (o site)
   - `CNAME` (para domínio customizado — opcional)
3. Em "Commit changes", escreva: `Deploy inicial do site`
4. Clique em **Commit changes**

#### Opção B — Pelo Git (linha de comando):
```bash
# No PowerShell ou Terminal, navegue até a pasta com os arquivos
cd C:\Users\SeuUsuario\Downloads\ai-sentinel-site

# Inicialize o repositório
git init
git add .
git commit -m "Deploy inicial do site"

# Conecte ao GitHub (substitua pelo seu username)
git remote add origin https://github.com/SEU_USERNAME/iasentinelcompliance.github.io.git
git branch -M main
git push -u origin main
```

---

### PASSO 3: Ativar GitHub Pages

1. No repositório, vá em **Settings** (aba superior)
2. No menu lateral, clique em **Pages**
3. Em **Source**, selecione:
   - Branch: `main`
   - Folder: `/ (root)`
4. Clique em **Save**
5. Aguarde 2-3 minutos

✅ Seu site estará disponível em:
```
https://iasentinelcompliance.github.io
```

---

### PASSO 4 (Opcional): Domínio Customizado

Para usar `iasentinelcompliance.io` ou outro domínio próprio:

#### 4.1 — Comprar o domínio
- Registradores recomendados: Namecheap, Cloudflare, GoDaddy, Registro.br
- Para `.io`: Namecheap (~$30/ano) ou Cloudflare

#### 4.2 — Configurar DNS do domínio
No painel do registrador, adicione estes registros DNS:

| Tipo  | Nome | Valor                      |
|-------|------|----------------------------|
| A     | @    | 185.199.108.153            |
| A     | @    | 185.199.109.153            |
| A     | @    | 185.199.110.153            |
| A     | @    | 185.199.111.153            |
| CNAME | www  | iasentinelcompliance.github.io |

#### 4.3 — Configurar no GitHub
1. Vá em **Settings → Pages**
2. Em **Custom domain**, digite: `iasentinelcompliance.io`
3. Clique em **Save**
4. Marque **Enforce HTTPS** (após verificação DNS, ~24h)

---

### PASSO 5: Atualizar o Site

Para fazer alterações:

#### Pelo navegador:
1. No repositório, clique no arquivo `index.html`
2. Clique no ícone de lápis (✏️ Edit)
3. Faça as alterações
4. Clique em **Commit changes**
5. O site atualiza automaticamente em 1-2 minutos

#### Pelo Git:
```bash
# Edite o index.html localmente, depois:
git add .
git commit -m "Atualização do conteúdo"
git push
```

---

## Migração para Outro Provedor

Quando estiver pronto para migrar (Vercel, Netlify, ou VPS):

### Vercel (Recomendado — Gratuito)
1. Acesse https://vercel.com
2. Faça login com sua conta GitHub
3. Clique em "New Project"
4. Selecione o repositório `iasentinelcompliance.github.io`
5. Clique em Deploy
6. Configure o domínio customizado nas settings do projeto

### Netlify (Alternativa — Gratuito)
1. Acesse https://netlify.com
2. Arraste a pasta do site para o painel
3. Configure o domínio nas settings

### VPS (Produção)
1. Contrate um VPS (DigitalOcean, AWS, Azure)
2. Instale Nginx
3. Copie o `index.html` para `/var/www/html/`
4. Configure SSL com Let's Encrypt

---

## Estrutura de Arquivos

```
iasentinelcompliance.github.io/
├── index.html    ← Site completo (arquivo único)
├── CNAME         ← Domínio customizado (opcional)
└── README.md     ← Este arquivo
```

## Formulário de Contato

O formulário está configurado para usar Formspree. Para ativar:
1. Crie uma conta em https://formspree.io
2. Crie um novo form
3. Copie o endpoint (ex: `https://formspree.io/f/xabcdefg`)
4. No `index.html`, substitua `https://formspree.io/f/placeholder` pelo seu endpoint

---

© 2026 SDC — e-Preserve Governança de IA. Confidencial.
