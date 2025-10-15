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

## 3️⃣ Verificar o status das mudanças

Antes de enviar as mudanças, veja o que foi alterado:

```bash
git status
```

## 4️⃣ Adicionar os arquivos ao commit

Adicione os arquivos modificados à "área de stage":

```bash
git add exemplo.txt
```

Ou para adicionar todos os arquivos modificados:

```bash
git add .
```

## 5️⃣ Fazer um commit (salvar a versão local)

Crie um commit com uma mensagem explicando o que mudou:

```bash
git commit -m "Adiciona arquivo exemplo.txt"
```

## 6️⃣ Enviar as mudanças para o GitHub

Se o repositório já tem um remoto configurado (chamado `origin`), envie assim:

```bash
git push origin main
```

⚠️ **Atenção:** Às vezes a branch principal pode se chamar `master` em vez de `main`. Verifique com:

```bash
git branch
```

Utilize o comando abaixo para renomear a branch

```bash
git branch -M main
```

## 7️⃣ (Opcional) Criar uma nova branch

Para trabalhar em algo sem afetar o código principal:

```bash
git checkout -b minha-nova-branch
```

Depois, envie essa branch para o GitHub:

```bash
git push origin minha-nova-branch
```

## 8️⃣ Atualizar o projeto com as últimas mudanças

Antes de começar novas alterações, é bom atualizar o código:

```bash
git pull origin main
```

## ✅ Resumo dos principais comandos 

| Ação | Comando |
|------|---------|
| Clonar repositório | `git clone URL` |
| Entrar na pasta | `cd nome-do-repo` |
| Ver status | `git status` |
| Adicionar arquivos | `git add .` |
| Criar commit | `git commit -m "mensagem"` |
| Enviar ao GitHub | `git push origin main` |
| Atualizar repositório | `git pull origin main` |

## 🌟 Tipo e descrição

O commit semântico possui os elementos estruturais abaixo (tipos), que informam a intenção do seu commit ao utilizador(a) de seu código.

- `feat`- Commits do tipo feat indicam que seu trecho de código está incluindo um **novo recurso** (se relaciona com o MINOR do versionamento semântico).

- `fix` - Commits do tipo fix indicam que seu trecho de código commitado está **solucionando um problema** (bug fix), (se relaciona com o PATCH do versionamento semântico).

- `docs` - Commits do tipo docs indicam que houveram **mudanças na documentação**, como por exemplo no Readme do seu repositório. (Não inclui alterações em código).

- `test` - Commits do tipo test são utilizados quando são realizadas **alterações em testes**, seja criando, alterando ou excluindo testes unitários. (Não inclui alterações em código)

- `build` - Commits do tipo build são utilizados quando são realizadas modificações em **arquivos de build e dependências**.

- `perf` - Commits do tipo perf servem para identificar quaisquer alterações de código que estejam relacionadas a **performance**.

- `style` - Commits do tipo style indicam que houveram alterações referentes a **formatações de código**, semicolons, trailing spaces, lint... (Não inclui alterações em código).

- `refactor` - Commits do tipo refactor referem-se a mudanças devido a **refatorações que não alterem sua funcionalidade**, como por exemplo, uma alteração no formato como é processada determinada parte da tela, mas que manteve a mesma funcionalidade, ou melhorias de performance devido a um code review.

- `chore` - Commits do tipo chore indicam **atualizações de tarefas** de build, configurações de administrador, pacotes... como por exemplo adicionar um pacote no gitignore. (Não inclui alterações em código)

- `ci` - Commits do tipo ci indicam mudanças relacionadas a **integração contínua** (_continuous integration_).

- `raw` - Commits do tipo raw indicam mudanças relacionadas a arquivos de configurações, dados, features, parâmetros.

- `cleanup` - Commits do tipo cleanup são utilizados para remover código comentado, trechos desnecessários ou qualquer outra forma de limpeza do código-fonte, visando aprimorar sua legibilidade e manutenibilidade.

- `remove` - Commits do tipo remove indicam a exclusão de arquivos, diretórios ou funcionalidades obsoletas ou não utilizadas, reduzindo o tamanho e a complexidade do projeto e mantendo-o mais organizado.
