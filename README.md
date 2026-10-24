# Titan Card — GitHub e Vercel

Site demonstrativo independente. O visual, as animações e os botões foram preservados. Não solicita dados pessoais nem crédito. Não precisa de chaves, banco de dados ou conta Lovable para funcionar.

## 1. Enviar ao GitHub

1. Extraia este ZIP no computador. Não envie o ZIP fechado ao repositório.
2. Crie um repositório no GitHub e escolha **Add file → Upload files**.
3. Envie todos os arquivos e a pasta `src` e `public`. `package.json`, `package-lock.json`, `vite.config.ts` e `vercel.json` devem ficar na raiz do repositório, não dentro de outra pasta.
4. Salve com **Commit changes**. Arquivos ocultos `.gitignore` e `.nvmrc` também estão no ZIP; envie-os usando Git se seu navegador não os mostrar.

## 2. Conectar na Vercel

1. Na Vercel, escolha **Add New → Project** e importe o repositório.
2. Use **Framework Preset: Other**.
3. **Root Directory:** raiz do repositório (deixe como está se você enviou os arquivos diretamente).
4. **Install Command:** `npm ci`.
5. **Build Command:** `npm run build`.
6. **Output Directory:** não habilite Override e não escreva `dist`. A configuração gera automaticamente `.vercel/output`, com os arquivos e a função necessários.
7. **Node.js Version:** 22.x. Não é necessário configurar variáveis de ambiente.
8. Clique em **Deploy**.

As configurações de instalação e compilação já estão em `vercel.json`. Não selecione Next.js, não substitua a pasta de saída e não publique somente a pasta `src`.

## Executar no computador

Instale Node.js 22 e execute:

```sh
npm ci
npm run dev
```

Use o endereço mostrado no terminal. Não abra arquivos TSX ou o HTML por duplo clique.

## Verificação de produção local

```sh
npm test
npm run build
npm run build:local
npm run start:local
```

`npm run build` gera o formato de publicação da Vercel. `build:local` gera uma versão de produção com servidor Node para testar no computador, no endereço mostrado pelo servidor. Não use `build:local` como comando de publicação da Vercel.

## Se aparecer tela branca

Confira os logs de implantação: instalação e compilação devem terminar com sucesso. Verifique se os arquivos estão na raiz, se o preset é Other, se Node é 22.x e se Output Directory Override está desativado. Depois faça uma nova implantação. Este pacote não contém `node_modules`, arquivos de compilação, segredos ou dependências privadas da Lovable.

## Limite da verificação

A instalação, a compilação para Vercel e a execução de produção local são verificadas antes da entrega. A publicação real na sua conta Vercel só pode ser confirmada após você conectar o repositório e implantar.
