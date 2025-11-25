# Guia de Solução de Problemas - FireDeluxe

## Problema: Script não funciona no Tampermonkey

### Passo 1: Verificar se o script está ativado
1. Clique no ícone do Tampermonkey no navegador
2. Vá em "Painel de Controle"
3. Verifique se o script "FireDeluxe" está com o status **ATIVO** (toggle verde)
4. Se estiver desativado, clique para ativar

### Passo 2: Verificar a URL do site
- O script só funciona em: `https://animefire.plus/*`
- Verifique se você está acessando o site correto
- O @match no script é: `*://*.animefire.plus/*`

### Passo 3: Verificar erros no Console
1. Pressione `F12` para abrir o DevTools
2. Vá na aba "Console"
3. Procure por erros em vermelho
4. Se houver erros, anote-os

### Passo 4: Verificar se o script está sendo executado
1. No Console, digite: `document.cookie`
2. Procure por: `firedeluxe_versao=2.18`
3. Se não encontrar, o script não está rodando

### Passo 5: Verificar download do script externo
O `fire.js` tenta baixar o script externo de:
`https://raw.githubusercontent.com/Mikill73/FireDeluxe/main/Mod/Userscript.js`

Se essa URL não estiver acessível, o script não funcionará.

### Passo 6: Verificar se você está logado
O script verifica se existe um link de perfil:
```javascript
const profileLink = document.querySelector('a.meu-perfil[href^="/users/"]');
```
Se você não estiver logado, algumas funcionalidades podem não aparecer.

## Solução Rápida

Se nada funcionar, tente:
1. Desativar e reativar o script no Tampermonkey
2. Recarregar a página (F5)
3. Limpar o cache do navegador
4. Verificar se há bloqueadores de anúncios interferindo

