# ⭐ Tutorial Básico - Git e GitHub 

## 1️⃣ Pré-requisitos

Antes de começar, você precisa:

- Ter o Git instalado → https://git-scm.com/downloads
- Criar uma conta no GitHub → https://github.com
- Configurar seu nome e e-mail (para identificar seus commits):

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@example.com"
```

## 2️⃣ Clonar um repositório existente do GitHub

Se você quer trabalhar em um projeto que já existe, primeiro precisa cloná-lo.

1. No GitHub, vá até o repositório que você quer clonar. Exemplo: `https://github.com/usuario/repositorio.git`

2. No terminal (ou Git Bash), rode:

```bash
git clone https://github.com/usuario/repositorio.git
```

Isso cria uma cópia local do projeto na sua máquina.

3. Entre na pasta do projeto:

```bash
cd repositorio
```

## 3️⃣ Fazer alterações no código

Agora você pode editar arquivos, criar novos, etc.

Por exemplo:

```bash
echo "Meu primeiro arquivo" > exemplo.txt
```

## 4️⃣ Verificar o status das mudanças

Antes de enviar as mudanças, veja o que foi alterado:

```bash
git status
```

## 5️⃣ Adicionar os arquivos ao commit

Adicione os arquivos modificados à "área de stage":

```bash
git add exemplo.txt
```

Ou para adicionar todos os arquivos modificados:

```bash
git add .
```

## 6️⃣ Fazer um commit (salvar a versão local)

Crie um commit com uma mensagem explicando o que mudou:

```bash
git commit -m "Adiciona arquivo exemplo.txt"
```

## 7️⃣ Enviar as mudanças para o GitHub

Se o repositório já tem um remoto configurado (chamado `origin`), envie assim:

```bash
git push origin main
```

⚠️ **Atenção:** Às vezes a branch principal pode se chamar `master` em vez de `main`. Verifique com:

```bash
git branch
```

## 8️⃣ (Opcional) Criar uma nova branch

Para trabalhar em algo sem afetar o código principal:

```bash
git checkout -b minha-nova-branch
```

Depois, envie essa branch para o GitHub:

```bash
git push origin minha-nova-branch
```

## 9️⃣ Atualizar o projeto com as últimas mudanças

Antes de começar novas alterações, é bom atualizar o código:

```bash
git pull origin main
```

## ✅ Resumo dos comandos principais

| Ação | Comando |
|------|---------|
| Clonar repositório | `git clone URL` |
| Entrar na pasta | `cd nome-do-repo` |
| Ver status | `git status` |
| Adicionar arquivos | `git add .` |
| Criar commit | `git commit -m "mensagem"` |
| Enviar ao GitHub | `git push origin main` |
| Atualizar repositório | `git pull origin main` |

# 🌟 Guia de Soluções - Problemas Comuns do Git e GitHub 

## 1️⃣ Problemas de autenticação (login/token)

### 🚫 Erro comum:

```bash
fatal: Authentication failed for 'https://github.com/usuario/repositorio.git/'
```

### 💡 Causa:
O GitHub não aceita mais senhas diretamente — você precisa usar um Personal Access Token (PAT).

### ✅ Solução:

1. Vá em GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Gere um token com permissões de `repo` e `workflow`.
3. Ao fazer `git push`, use:
   - Usuário: seu nome de usuário do GitHub
   - Senha: o token gerado

Ou configure uma vez com:

```bash
git remote set-url origin https://<TOKEN>@github.com/usuario/repositorio.git
```

---

## 2️⃣ Estar fora da pasta correta

### 🚫 Erro comum:

```bash
fatal: not a git repository (or any of the parent directories): .git
```

### 💡 Causa:
Você está tentando rodar comandos Git fora do repositório clonado.

### ✅ Solução:
Entre na pasta certa:

```bash
cd nome-do-repositorio
```

---

## 3️⃣ Branch errada (main vs master)

### 🚫 Erro comum:

```bash
error: src refspec main does not match any
```

### 💡 Causa:
O nome da branch principal mudou de `master` → `main`. O comando `git push origin main` não funciona se a branch for `master`.

### ✅ Solução:
Verifique a branch atual:

```bash
git branch
```

Se estiver em `master`, use:

```bash
git push origin master
```

---

## 4️⃣ Conflitos ao dar pull ou merge

### 🚫 Erro comum:

```bash
CONFLICT (content): Merge conflict in arquivo.txt
```

### 💡 Causa:
Você e outra pessoa alteraram o mesmo trecho de um arquivo.

### ✅ Solução:

1. Abra o arquivo indicado.
2. Procure linhas assim:

```bash
<<<<<<< HEAD
seu código
=======
código do outro
>>>>>>> main
```

3. Escolha o trecho que deve ficar e salve o arquivo.
4. Depois:

```bash
git add arquivo.txt
git commit -m "Resolve conflito em arquivo.txt"
```

---

## 5️⃣ Esquecer de adicionar antes de fazer commit

### 🚫 Erro comum:

```bash
nothing to commit, working tree clean
```

### 💡 Causa:
Você modificou arquivos, mas não fez `git add`.

### ✅ Solução:

```bash
git add .
git commit -m "Mensagem do commit"
```

---

## 6️⃣ Repositório remoto não configurado

### 🚫 Erro comum:

```bash
fatal: No configured push destination.
```

### 💡 Causa:
O Git não sabe para onde enviar o código.

### ✅ Solução:
Adicionar o repositório remoto:

```bash
git remote add origin https://github.com/usuario/repositorio.git
```

E depois:

```bash
git push -u origin main
```

---

## 7️⃣ Falta de permissão no repositório

### 🚫 Erro comum:

```bash
Permission denied (publickey).
```

### 💡 Causa:
Você está tentando fazer `push` em um repositório que não é seu (ou não tem acesso).

### ✅ Solução:

- Verifique se é colaborador do repositório.
- Ou faça um fork no GitHub e envie para o seu próprio repositório.

---

## 8️⃣ Alterações locais não salvas antes do pull

### 🚫 Erro comum:

```bash
error: Your local changes to the following files would be overwritten by merge
```

### 💡 Causa:
Você tem alterações locais que conflitam com o que está no GitHub.

### ✅ Soluções:

- Se quiser guardar suas mudanças primeiro:

```bash
git add .
git commit -m "Salva mudanças locais"
git pull origin main
```

- Se quiser descartar tudo localmente:

```bash
git restore .
git pull origin main
```

---

## 9️⃣ Confundir `clone` com `pull`

- `git clone` → copia um repositório inteiro pela primeira vez.
- `git pull` → atualiza o que já foi clonado.

### 🚫 Erro comum:
Rodar `git clone` várias vezes, criando várias cópias do mesmo projeto.

### ✅ Solução:
Depois de clonar uma vez, use apenas:

```bash
git pull origin main
```

---

## 1️⃣0️⃣ "Commitar" arquivos desnecessários (como logs ou dependências)

### 💡 Causa:
Não usar um `.gitignore` adequado.

### ✅ Solução:
Crie um arquivo chamado `.gitignore` e adicione o que não deve ser versionado, por exemplo:

```
node_modules/
.env
*.log
__pycache__/
```
