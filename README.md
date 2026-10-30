# Detecção de DDoS com Aprendizado de Máquina sob Deriva Temporal

Projeto de Iniciação Científica em desenvolvimento na Universidade Federal de Uberlândia (UFU), que tem como objetivo investigar a aplicação de técnicas de Aprendizado de Máquina na detecção de ataques DDoS, considerando os desafios relacionados às mudanças temporais no comportamento do tráfego de rede.

## Sobre a Pesquisa

A pesquisa aborda a utilização de modelos de Aprendizado de Máquina para distinguir tráfego benigno de tráfego malicioso, utilizando o conjunto de dados CIC-DDoS2019 como base experimental.

O estudo contempla diferentes abordagens de representação do tráfego de rede, buscando analisar a influência da seleção de características no desempenho dos modelos de detecção.

Outro aspecto central é a deriva temporal (*Temporal Drift*), que pode afetar a capacidade de generalização dos modelos diante de mudanças no comportamento do tráfego ao longo do tempo.

## Base de Dados

A pesquisa utiliza o **CIC-DDoS2019**, conjunto de dados que reúne registros de tráfego benigno e diferentes categorias de ataques DDoS.

Entre os cenários considerados estão:

- DNS
- LDAP
- MSSQL
- NetBIOS
- NTP
- SNMP
- SSDP
- SYN
- UDP
- TFTP

## Organização da Pesquisa

### 1. Preparação dos Dados

Etapa dedicada à análise e preparação dos conjuntos de dados utilizados nos experimentos, contemplando:

- Análise exploratória dos dados.
- Auditoria da qualidade dos dados.
- Identificação de inconsistências, valores ausentes e infinitos.
- Seleção e análise de características.
- Tratamento dos dados.
- Geração e balanceamento dos conjuntos de dados.

### 2. Treinamento e Avaliação dos Modelos

A pesquisa contempla duas abordagens de representação do tráfego de rede:

- **Modelo Cheio:** utiliza um conjunto mais amplo de características disponíveis no dataset.
- **Modelo Fluxo:** utiliza um conjunto reduzido de características comportamentais dos fluxos de rede.

A comparação entre as abordagens busca investigar a influência da seleção de características no desempenho dos modelos de detecção.

Os experimentos também consideram a organização cronológica dos dados, permitindo analisar o comportamento dos modelos diante de mudanças temporais no tráfego de rede.

### 3. Explicabilidade dos Modelos

A pesquisa explora técnicas de explicabilidade, com destaque para SHAP (*SHapley Additive exPlanations*), buscando compreender a contribuição das características nas decisões dos modelos.

Essa análise permite investigar quais atributos possuem maior influência nas classificações e comparar o comportamento dos modelos Cheio e Fluxo.

### 4. Deriva Temporal

A pesquisa também investiga os efeitos da deriva temporal (*Temporal Drift*) sobre o desempenho dos modelos de detecção.

Nesse contexto, considera-se o ADWIN (*Adaptive Windowing*), mecanismo de detecção de mudanças que poderá auxiliar na identificação de alterações no comportamento dos dados e na investigação de estratégias de atualização e retreinamento dos modelos.

## Métricas de Avaliação

Entre as métricas consideradas para avaliação dos modelos estão:

- Acurácia (*Accuracy*)
- Precisão (*Precision*)
- Revocação (*Recall*)
- F1-Score
- Matriz de Confusão (*Confusion Matrix*)

## Estrutura do Repositório

```text
├── datasets/
│   ├── CICDDOS2019/
│   │   ├── 01-12/
│   │   └── 03-11/
│   │
│   ├── balanceados/
│   ├── classe_unica/
│   └── tratados/
│
└── notebooks/
    ├── 01_preparacao_dados/
    │   ├── exploratorio/
    │   └── tratamento_geracaoDataset/
    │       ├── classe_unica/
    │       ├── total_fluxo/
    │       └── tratamento/
    │
    ├── 02_treinamento/
    │   ├── modelos_cheio.ipynb
    │   └── modelos_fluxo.ipynb
    │
    └── 03_explicabilidade/
        ├── cheio/
        └── fluxo/
```

## Tecnologias e Bibliotecas

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib
- Seaborn

---
