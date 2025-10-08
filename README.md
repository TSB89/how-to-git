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
