# CTT09 - API FastAPI com CI

Este projeto e uma API simples feita com FastAPI. Ela possui rotas para testar o funcionamento da API, somar dois numeros e multiplicar dois numeros.

## Requisitos

- Python instalado
- Git instalado, caso queira enviar para o GitHub

## Como entrar na pasta do projeto

No PowerShell, execute:

```powershell
cd "C:\Users\2400836\Documents\Nova pasta\CTT09-repo"
```

## Como instalar as dependencias

Execute:

```powershell
python -m pip install -r requirements.txt
```

## Como rodar os testes

Execute:

```powershell
python -m pytest -q
```

Resultado esperado:

```text
3 passed
```

## Como rodar a API

Execute:

```powershell
python -m fastapi run main.py --port 8000
```

Depois acesse no navegador:

```text
http://localhost:8000/
```

Para parar a API, pressione `Ctrl + C` no terminal.

## Rotas disponiveis

Rota inicial:

```text
GET http://localhost:8000/
```

Resposta esperada:

```json
{"mensagem":"API funcionando!"}
```

Rota de soma:

```text
GET http://localhost:8000/somar/10/20
```

Resposta esperada:

```json
{"resultado":30}
```

Rota de multiplicacao:

```text
GET http://localhost:8000/multiplicar/2/2
```

Resposta esperada:

```json
{"resultado":4}
```

## Como testar a API pelo terminal

Com a API rodando, abra outro PowerShell e execute:

```powershell
curl http://localhost:8000/
curl http://localhost:8000/somar/10/20
curl http://localhost:8000/multiplicar/2/2
```

## GitHub Actions

O arquivo `.github/workflows/ci.yml` configura o pipeline de CI.

Ele roda automaticamente em:

- `push`
- `pull_request`

O pipeline faz:

- instalacao das dependencias
- execucao dos testes com `pytest`
- teste em Python `3.10`, `3.11` e `3.12`
- subida da API no runner
- requisicoes reais com `curl`

## Como enviar para o GitHub

Configure seu nome e email do Git, se ainda nao estiverem configurados:

```powershell
git config user.name "Seu Nome"
git config user.email "seu-email@example.com"
```

Depois execute:

```powershell
git add .
git commit -m "Implementa CI com FastAPI e testes"
git remote add origin LINK_DO_SEU_REPOSITORIO
git push -u origin main
```

Substitua `LINK_DO_SEU_REPOSITORIO` pelo link do repositorio criado no GitHub.
