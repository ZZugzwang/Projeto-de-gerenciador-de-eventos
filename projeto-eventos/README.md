# Showline — Gerenciamento de Shows

--------INTEGRANTES-----------
BRENNO JOSÉ DE AGUIAR SILVA
JOÃO ANTÔNIO MAIA PORTELLA DUBEUX

Front-end + back-end 
O back-end (FastAPI + SQLite), O front-end inspirado em
plataformas como Sympla / Eventbrite / Ticketmaster, com cards em formato de
"canhoto de ingresso", barra de lotação, fila de espera e busca.

```
projeto-eventos/
├── backend/
│   ├── main.py            # API 
│   └── requirements.txt
└── frontend/
    ├── index.html
    ├── style.css
    └── script.js
```

## 1. Rodando na sua máquina

### Pré-requisitos
- Python 3.10+ instalado (`python --version` no terminal)
- Não precisa de Node nem de nada além de um navegador para o front-end

### 1.1. Backend (API)

```powershell
# entre na pasta do backend
cd projeto-eventos/backend

# crie um ambiente virtual (recomendado)
python -m venv venv

# ative o ambiente virtual
# Windows (PowerShell):
venv\Scripts\Activate.ps1
# Windows (cmd):
venv\Scripts\activate.bat
# Linux/Mac:
source venv/bin/activate

# instale as dependências
pip install -r requirements.txt

# rode o servidor
uvicorn main:app --reload
```

Se tudo der certo, vai aparecer algo como:
```
Uvicorn running on http://127.0.0.1:8000
```

Deixe esse terminal aberto. Você pode testar a API sozinha abrindo
`http://127.0.0.1:8000/docs` no navegador (documentação automática do FastAPI).

O banco `eventos.db` (SQLite) é criado automaticamente na primeira execução,
na própria pasta `backend/`.

### 1.2. Frontend

Abra um **segundo terminal** (deixe o backend rodando no primeiro):

```powershell
cd projeto-eventos/frontend

# qualquer servidor estático funciona. Com Python já instalado:
python -m http.server 5500
```

Agora abra `http://127.0.0.1:5500` no navegador.

> Por que não abrir o `index.html` direto com duplo clique?
> Alguns navegadores bloqueiam `fetch()` em arquivos abertos via `file://`.
> Servir por `http.server` (ou a extensão "Live Server" do VS Code) evita esse problema.

Se o indicador no topo da página mostrar **"API conectada"** (ponto verde), está tudo certo.
Se mostrar **"API offline"**, confirme que o terminal do backend ainda está rodando.

---