# BluePriori - Dashboard de Priorização de Vulnerabilidades

BluePriori é uma aplicação web full-stack para gerenciamento e priorização de vulnerabilidades. Consiste em uma API backend em Flask que processa dados de vulnerabilidades e um dashboard frontend em React que visualiza pontuações de prioridade por tipo de ativo, ajudando os usuários a decidir quais vulnerabilidades abordar primeiro.

## Funcionalidades

- **API Backend**: API RESTful construída com Flask e SQLAlchemy
- **Processamento de Dados**: Carrega dados de vulnerabilidades de arquivos JSON para banco SQLite
- **Dashboard Frontend**: Aplicação React interativa com gráficos e tabelas ordenáveis
- **Pontuação de Prioridade**: Visualiza priorização de ativos baseada em pontuações de vulnerabilidades
- **Atualizações em Tempo Real**: Atualiza dados do backend

## Tecnologias

- **Backend**: Python 3.12, Flask, SQLAlchemy, SQLite
- **Frontend**: React 19, Vite, Recharts, Axios
- **Banco de Dados**: SQLite (desenvolvimento) / PostgreSQL (produção)

## Pré-requisitos

- Python 3.12 ou superior
- Node.js 18 ou superior
- npm ou yarn

## Instalação e Configuração

### 1. Clonar o Repositório

```bash
git clone https://github.com/RodrigoAlban/Hackathon-SBSeg-2025.git
cd Hackathon-SBSeg-2025
```

### 2. Configuração do Backend

1. Criar e ativar ambiente virtual:
   ```bash
   python -m venv .venv
   # Windows:
   .venv\Scripts\activate
   # macOS/Linux:
   source .venv/bin/activate
   ```

2. Instalar dependências Python:
   ```bash
   pip install -r backend/requirements.txt
   ```

3. Carregar dados de vulnerabilidades no banco:
   ```bash
   python backend/load_data.py
   ```

4. Executar o backend Flask:
   ```bash
   python backend/app.py
   ```
   O backend estará disponível em `http://127.0.0.1:5000`

### 3. Configuração do Frontend

1. Navegar para o diretório frontend:
   ```bash
   cd frontend
   ```

2. Instalar dependências Node.js:
   ```bash
   npm install
   ```

3. Iniciar servidor de desenvolvimento:
   ```bash
   npm run dev
   ```
   O frontend estará disponível em `http://localhost:5173`

## Uso

1. Certifique-se de que backend e frontend estão rodando
2. Abra o navegador e acesse `http://localhost:5173`
3. O dashboard exibirá:
   - Gráfico de barras com pontuações médias de prioridade por tipo de ativo
   - Tabela ordenável com detalhes dos ativos
   - Botão de atualização para buscar dados do backend

## Endpoints da API

### Ativos
- `GET /assets` - Obter todos os ativos ordenados por pontuação de prioridade (decrescente)
- `GET /assets/<id>` - Obter ativo específico com suas vulnerabilidades

### Vulnerabilidades
- `GET /vulnerabilities` - Obter todas as vulnerabilidades
- `GET /vulnerabilities/<id>` - Obter vulnerabilidade específica por ID

## Estrutura do Projeto

```
Hackathon-SBSeg-2025/
├── README.md
├── backend/
│   ├── app.py                 # Aplicação Flask
│   ├── config.py             # Configurações
│   ├── models.py             # Modelos do banco
│   ├── load_data.py          # Script de carregamento de dados
│   ├── requirements.txt      # Dependências Python
│   └── data_JSON/            # Arquivos de dados de vulnerabilidades
├── frontend/
│   ├── src/
│   │   ├── App.jsx           # Componente principal do dashboard
│   │   ├── index.css         # Estilos do dashboard
│   │   └── main.jsx          # Ponto de entrada React
│   ├── package.json          # Dependências Node
│   └── vite.config.js        # Configuração Vite
└── instance/
    └── vulnerabilities.db    # Banco SQLite
```

## Desenvolvimento

### Backend
- Usa Flask com SQLAlchemy para ORM
- CORS habilitado para comunicação com frontend
- Modelos definidos em `models.py`

### Frontend
- Construído com React e Vite para desenvolvimento rápido
- Recharts para visualização de dados
- Axios para comunicação com API
- Design responsivo com CSS

## Contribuição

1. Fork o repositório
2. Crie uma branch de funcionalidade
3. Faça suas alterações
4. Teste backend e frontend
5. Envie um pull request

## Licença

Este projeto está licenciado sob a Licença MIT.
