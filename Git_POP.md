1. Criar o repositório local

Na pasta do projeto:

```bash 
git init
```

2. Configurar seu nome e e-mail (só na primeira vez no computador)

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

3. Ver o estado dos arquivos

```bash
git status
```

4. Adicionar arquivos à área de preparação (staging)

```bash
git add .
```

O ponto adiciona todos os arquivos. Para adicionar só um: git add arquivo.sql.

5. Fazer o commit (com mensagem!)

```bash
git commit -m "Primeiro commit"
```

6. Nomear a branch principal (se ainda não for main)

```bash
git branch -M main
```

7. Criar o repositório no GitHub

No site do GitHub, clique em New repository, dê um nome e crie (sem marcar README, para não dar conflito).

8. Conectar o repositório local ao remoto

```bash
git remote add origin https://github.com/seu-usuario/seu-repositorio.git
```

9. Enviar (push)

```bash
git push -u origin main
```

O -u só é necessário na primeira vez; depois basta git push.

Rotina do dia a dia (depois de tudo configurado):

```bash
git add .
git commit -m "Descrição do que mudou"
git push
```

Resumo visual:

Etapa	Comando	Para quê
Iniciar	git init	Cria o repositório
Preparar	git add .	Marca o que vai no commit
Gravar	git commit -m "..."	Salva uma versão
Conectar	git remote add origin URL	Liga ao GitHub
Enviar	git push	Sobe para o GitHub

Para atualizar sua pasta local com o que está no remoto, use o git pull.



1\. Entre na pasta do repositório:



powershell
```bash
cd C:\\Users\\marcelo.margreiter\\Desktop\\tendencia\_turnover
```


2\. Atualize:



powershell
```bash
git pull
```


Isso baixa as mudanças do remoto e já aplica no branch em que você está.



Se quiser ver antes de aplicar, faça em dois passos:



powershell
```bash
git fetch

git status

git diff HEAD origin/main
```


O git fetch só baixa as novidades, sem mexer nos seus arquivos. Depois, git merge (ou git pull) aplica. Troque main por master se for o nome do seu branch.



Se tiver alterações locais não commitadas, o pull pode reclamar de conflito. Duas opções:



powershell

`git stash`        # guarda suas alterações temporariamente

``git pull``

`git stash pop`    # devolve suas alterações



ou faça commit delas antes do pull:



powershell
```bash
git add .

git commit -m "minhas alterações"

git pull
```


Se quiser descartar tudo o que mudou localmente e deixar idêntico ao remoto (cuidado, isso apaga suas alterações não salvas):



powershell

```bash
git fetch

git reset --hard origin/main
```


Se o git pull der erro de “no tracking information”, defina o branch remoto assim:



powershell
```bash
git branch --set-upstream-to=origin/main main
```
