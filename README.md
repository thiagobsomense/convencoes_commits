# 📋 Convenções de Commit - Padrão Semântico

Este projeto segue o padrão de **Conventional Commits** para manter um histórico de commits organizado e semântico.

## ✨ Índice
- [Formato do Commit](#-formato-do-commit)
- [Tipos de Commit](#-tipos-de-commit)
- [Por que usar Commits Semânticos?](#por-que-usar-commits-semânticos)
- [Escopos](#escopos)
- [Boas Práticas](#boas-práticas)
- [Configuração do Git](#configuração-do-git)
- [Principais Comandos do Git](#principais-comandos-do-git)
- [Checklist do Commit](#checklist-do-commit)
- [Exemplos de Fluxo Completo](#exemplos-de-fluxo-completo)
- [Dicas para a Equipe](#dicas-para-a-equipe)

## 📚 Formato do Commit

```
<tipo>(<escopo>): <descrição>

<corpo>

<rodapé>
```

## 🏷️ Tipos de Commit

- **init**: Primeiro commit
  - Exemplo: `init: setup inicial do projeto`

- **feat**: Uma nova funcionalidade
  - Exemplo: `feat(auth): adicionar autenticação com JWT`

- **fix**: Correção de um bug
  - Exemplo: `fix(login): corrigir validação de email`

- **docs**: Mudanças apenas em documentação
  - Exemplo: `docs(readme): atualizar instruções de instalação`

- **style**: Mudanças que não afetam o código (formatação, pontuação, etc)
  - Exemplo: `style(eslint): configurar regras de formatação`

- **refactor**: Alteração de código que não corrige bugs nem adiciona funcionalidades
  - Exemplo: `refactor(api): simplificar lógica de requisições`

- **perf**: Mudanças para melhorar desempenho
  - Exemplo: `perf(cache): implementar cache de dados`

- **test**: Adição ou modificação de testes
  - Exemplo: `test(auth): adicionar testes de login`

- **ci**: Alterações em configurações de CI/CD
  - Exemplo: `ci(github): configurar workflows de teste`

- **chore**: Tarefas que não modificam código de produção
  - Exemplo: `chore(dependencies): atualizar dependências`

## 📝 Exemplos de Commits

### Bom ✅
```
feat(user): criar sistema de perfil de usuário

Adiciona página de perfil com:
- Exibição de dados do usuário
- Edição de informações pessoais
- Upload de foto de perfil

Closes #123
```

### Bom ✅
```
fix(modal): fechar modal ao clicar fora

Corrige comportamento da modal para fechar quando o usuário clica
na área externa do componente.
```

### Ruim ❌
```
alterações no código
```

### Ruim ❌
```
fix: arrumei um negócio
```

## 🎯 Por que usar Commits Semânticos?

Commits semânticos trazem diversos benefícios para o desenvolvimento:

| Benefício | Descrição |
|-----------|-----------|
| 📖 **Legibilidade** | Histórico claro e fácil de entender |
| 🔍 **Rastreabilidade** | Identifica rapidamente quando mudanças foram feitas |
| 🤖 **Automação** | Permite gerar CHANGELOGs automaticamente |
| 👥 **Colaboração** | Facilita compreensão por novos membros da equipe |
| 🐛 **Debugging** | Encontra commits relacionados a bugs mais rapidamente |
| 📊 **Análise** | Gera estatísticas sobre desenvolvimento |
| 🔄 **Versionamento** | Suporta semantic versioning automático |

## 🎯 Escopos

O escopo deve especificar a área do projeto afetada. Use escopos consistentes em seu projeto:

### Escopos Comuns

- **auth**: Autenticação e autorização
- **user**: Gerenciamento de usuários e perfis
- **api**: Endpoints e integrações da API
- **ui**: Componentes e interface de usuário
- **database**: Banco de dados e migrations
- **config**: Configurações do projeto
- **build**: Sistema de build e compilação
- **docs**: Documentação
- **performance**: Otimizações
- **security**: Segurança

### Usando Escopos Corretamente

```
feat(api): adicionar endpoint de listar usuários
fix(ui): corrigir alinhamento do botão
refactor(database): melhorar índices de consulta
```

## ✅ Boas Práticas

1. Use o imperativo: "adicionar" em vez de "adicionado" ou "adiciona"
2. Não use ponto final (.) na descrição
3. Limite a descrição a 50 caracteres
4. Separe o assunto do corpo com uma linha em branco
5. Quebre o corpo em 72 caracteres
6. Use o corpo para explicar o **quê** e o **por quê**, não o **como**
7. Referencie issues com `Closes #número` ou `Fixes #número`

## 🔧 Configuração do Git

### Configurar seu Perfil

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@empresa.com"
```

### Configurar Editor Padrão (Opcional)

```bash
# Windows - VSCode
git config --global core.editor "code --wait"

# Windows - Notepad
git config --global core.editor "notepad"
```

### Verificar Configurações

```bash
git config --list
```

## 🛠️ Principais Comandos do Git

### Básicos

```bash
# Clonar repositório
git clone <url-repositorio>

# Ver status do repositório
git status

# Ver diferenças das mudanças
git diff

# Adicionar arquivos para stage
git add <arquivo>
git add .  # Adicionar todos

# Remover arquivo do stage
git restore --staged <arquivo>
```

### Commits

```bash
# Criar commit com mensagem
git commit -m "feat(user): adicionar página de perfil"

# Commit com corpo detalhado (abre editor)
git commit

# Corrigir último commit
git commit --amend --no-edit

# Ver histórico de commits
git log --oneline
git log --graph --all --decorate --oneline
```

### Branches

```bash
# Criar nova branch
git checkout -b feature/nova-funcionalidade

# Listar branches
git branch -a

# Trocar de branch
git checkout <nome-branch>

# Deletar branch
git branch -d <nome-branch>
```

### Sincronização

```bash
# Buscar atualizações
git fetch origin

# Atualizar branch com remote
git pull origin <nome-branch>

# Enviar commits
git push origin <nome-branch>
```

## 📋Checklist do Commit

Antes de fazer um commit, verifique:

- ✅ Minha mudança segue o padrão semântico?
- ✅ Meu escopo está correto e consistente?
- ✅ Minha descrição está clara e em imperativo?
- ✅ A descrição tem menos de 50 caracteres?
- ✅ Meu código foi testado?
- ✅ Não há arquivos desnecessários adicionados?
- ✅ Minhas mudanças estão relacionadas a um único objetivo?
- ✅ Referenciei issues relacionadas no corpo?
- ✅ Não quebrei nenhum teste existente?

## 🎉 Exemplos de Fluxo Completo

### Cenário 1: Nova Funcionalidade

```bash
# Desenvolvendo uma nova feature
git checkout -b feat/user-profile-page

# Após implementar
git add .
git commit -m "feat(users): adiciona página de perfil do usuário

- Cria template profile.html com informações básicas
- Implementa view UserProfileView com mixin de autenticação
- Adiciona testes para acesso e renderização

Resolves: #45"

git push origin feat/user-profile-page
```

### Cenário 2: Correção de Bug

```bash
# Corrigindo um bug reportado
git checkout -b fix/email-validation

# Após corrigir
git add .
git commit -m "fix(auth): corrige validação de domínio de email

- Ajusta regex para aceitar domínios com hífen
- Adiciona teste para emails com subdomínio
- Atualiza mensagem de erro para ser mais clara

Fixes: #78"

git push origin fix/email-validation
```

## 🤝 Dicas para a Equipe

### 📝 Dica 1: Commits Atômicos
Faça commits pequenos e focados. Um commit = uma mudança lógica.

```bash
# ❌ Ruim: múltiplas mudanças em um commit
git commit -m "feat: vários ajustes no projeto"

# ✅ Bom: commits separados
git commit -m "feat(auth): adicionar token refresh"
git commit -m "fix(api): corrigir erro de validação"
git commit -m "docs(readme): atualizar instruções"
```

### 📝 Dica 2: Rebase ao invés de Merge
Mantenha o histórico limpo:

```bash
git fetch origin
git rebase origin/main
git push origin feature/minha-feature --force-with-lease
```

### 📝 Dica 3: Revisar antes de Push
Sempre revise seus commits:

```bash
git log origin/main..HEAD --oneline
```

### 📝 Dica 4: Mensagens de Commit no Editor
Para mensagens com corpo detalhado:

```bash
git commit  # Sem -m, abre editor
```

### 📝 Dica 5: Stash para Mudanças Temporárias
Salve trabalho sem commitar:

```bash
git stash
git checkout outra-branch
# ...fazer algo...
git checkout sua-branch
git stash pop
```

### 📝 Dica 6: Evitar Commits Acidentais
Crie um `.gitignore` robusto:

```
# Node
node_modules/
*.log

# IDEs
.vscode/
.idea/

# Ambiente
.env
.env.local

# Build
dist/
build/
```

### 📝 Dica 7: Integração com Hooks
Use ferramentas como `husky` e `commitlint` para validar:

```bash
npm install husky commitlint @commitlint/config-conventional --save-dev
npx husky install
npx husky add .husky/commit-msg 'npx --no -- commitlint --edit "$1"'
```

### 📝 Dica 8: Equipe em Sincronia
Estabeleça padrões:
- Escopos consistentes em todo o projeto
- Revisor valida padrão semântico no PR
- Squash/rebase em PRs para manter histórico limpo
- Bloqueie pushes diretos na main (proteja a branch)

## Benefícios
✨ Histórico mais legível e organizado
🔍 Facilita a busca de mudanças específicas
📝 Auxilia na geração automática de CHANGELOGs
🔄 Melhora a compreensão do projeto por novos desenvolvedores
🚀 Acelera onboarding de novos membros
