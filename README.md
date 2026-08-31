# ACHOU+ — Publicar no GitHub Pages

Esta pasta já vem pronta para virar um repositório: `index.html` na raiz é o site,
`admin.html` é o painel administrativo.

⚠️ **O GitHub Pages só hospeda os arquivos estáticos.** O Firebase (Firestore,
Authentication, Cloud Functions das assinaturas) continua sendo configurado à parte,
exatamente como no README do pacote `achou-plus-firebase.zip` — isso não muda com
GitHub Pages. Antes de publicar, garanta que já colou o `firebaseConfig` real (não
o `COLE_AQUI`) em `index.html` e `admin.html`.

## Passo a passo

**1. Criar o repositório**

No GitHub, crie um repositório novo (ex: `achou-plus`). Pode ser público ou privado
— GitHub Pages funciona nos dois (privado exige GitHub Pro).

**2. Subir os arquivos**

Pelo terminal, dentro desta pasta:

```
git init
git add .
git commit -m "Primeira versão do ACHOU+"
git branch -M main
git remote add origin https://github.com/addrosales/achou-plus.git
git push -u origin main
```

(troque a URL pelo endereço do repositório que você criou)

**3. Ativar o GitHub Pages**

No repositório → **Settings → Pages** → em "Build and deployment":
- Source: **Deploy from a branch**
- Branch: **main** / pasta **/ (root)**
- Save

Em alguns minutos o GitHub mostra a URL pública, algo como:
`https://addrosales.github.io/achou-plus/`

O site principal fica em `.../achou-plus/`
O painel administrativo fica em `.../achou-plus/admin.html`

## Atualizando o site depois

Sempre que editar os arquivos:

```
git add .
git commit -m "Atualização"
git push
```

O GitHub Pages republica sozinho em 1–2 minutos.

## Sobre o backend (Firebase)

Isso é independente de onde o site está hospedado. Siga o README que veio no
`achou-plus-firebase.zip`:
1. Criar o projeto Firebase (Auth + Firestore)
2. Colar as credenciais em `index.html` e `admin.html`
3. Publicar as regras (`firestore.rules` / `firestore.indexes.json`)
4. Criar o primeiro usuário admin
5. Configurar o Mercado Pago e publicar as Cloud Functions (`functions/index.js`)
   — lembre de trocar `BACK_URL` pela URL do GitHub Pages depois do passo 3
