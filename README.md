# Projeto_Integrador_Faculdade
# SteamDatabase

## Sobre o projeto

O **SteamDatabase** é um projeto desenvolvido em Python com o objetivo de explorar, consultar e analisar informações sobre jogos disponíveis na plataforma Steam.

O sistema utiliza um conjunto de dados disponibilizado pelo Kaggle para oferecer funcionalidades de pesquisa, organização de jogos, visualização de dados e recomendação de títulos semelhantes.

O projeto também explora conceitos de análise de dados, visualização gráfica, programação orientada a objetos e aprendizado de máquina (*Machine Learning*).

## Funcionalidades

Atualmente, o sistema apresenta as seguintes funcionalidades:

- **Pesquisa de jogos:** permite localizar jogos por meio de seus identificadores únicos (AppID).
- **Lista personalizada:** permite adicionar jogos a uma lista, evitando duplicações.
- **Limpeza da lista:** remove todos os jogos selecionados.
- **Visualização gráfica:** apresenta os jogos mais populares da Steam com base no pico de jogadores simultâneos (*Peak CCU*).
- **Sistema de recomendação:** identifica jogos semelhantes com base em seus gêneros, categorias e tags.

## Tecnologias e bibliotecas utilizadas

| Tecnologia | Finalidade |
|---|---|
| Python | Linguagem de programação utilizada no desenvolvimento. |
| Pandas | Manipulação, filtragem e organização dos dados. |
| KaggleHub | Download do conjunto de dados hospedado no Kaggle. |
| Google Colab | Ambiente de desenvolvimento e execução. |
| Matplotlib | Construção de gráficos para visualização dos dados. |
| Scikit-learn | Implementação do sistema de recomendação. |
| TfidfVectorizer | Transformação de características textuais em representações numéricas. |
| NearestNeighbors | Identificação de jogos com características semelhantes. |

## Fonte dos dados

O projeto utiliza o conjunto de dados:

**Steam Games Dataset**

- Autor: fronkongames
- Plataforma: Kaggle
- Dataset: [Steam Games Dataset](https://www.kaggle.com/datasets/fronkongames/steam-games-dataset)

O arquivo principal utilizado é `games.csv`, que contém informações sobre os jogos, incluindo identificadores, nomes, gêneros, categorias, tags e pico de jogadores simultâneos.

## Sistema de recomendação

O sistema de recomendação utiliza duas ferramentas do Scikit-learn:

### TF-IDF

O `TfidfVectorizer` transforma informações textuais dos jogos em vetores numéricos, considerando características como:

- Gêneros (*Genres*);
- Categorias (*Categories*);
- Tags (*Tags*).

Essa transformação permite representar matematicamente as características dos jogos e compará-las.

### Nearest Neighbors

O algoritmo `NearestNeighbors` utiliza a distância cosseno (*Cosine Distance*) para identificar jogos com características semelhantes.

A similaridade é apresentada em porcentagem, calculada a partir da distância cosseno:

**Similaridade = (1 − Distância Cosseno) × 100**

O usuário pode adicionar jogos a uma lista personalizada e utilizar esses títulos como referência para receber recomendações.

A porcentagem representa a proximidade entre as características textuais dos jogos, não uma probabilidade de preferência do usuário.

## Visualização de dados

A visualização gráfica utiliza a biblioteca Matplotlib para apresentar os jogos com maior pico de jogadores simultâneos.

O usuário pode escolher a quantidade de jogos que deseja visualizar, e o sistema organiza os resultados em um gráfico de barras horizontais.

A métrica utilizada é `Peak CCU` (*Peak Concurrent Users*), que representa o pico de usuários simultâneos.

## Como executar

O projeto foi desenvolvido para execução no Google Colab.

### 1. Instalação das dependências

Execute a primeira célula.

### 2. Configuração do Kaggle

É necessário possuir um token de autenticação do Kaggle.

No Google Colab, configure o token `KAGGLE_API_TOKEN` na área de Secrets e habilite o acesso pelo notebook.

### 3. Execução

Após configurar as dependências e a autenticação, execute as células do projeto e inicialize o sistema, as células já estão em ordem de execução.

```python
steam = SteamVendas()
steam.executar()
```

## Estrutura do sistema

A implementação utiliza programação orientada a objetos, organizando as funcionalidades em métodos dentro da classe `SteamVendas`.

| Método | Responsabilidade |
|---|---|
| `carregar_dados()` | Autenticação e carregamento do dataset. |
| `menu()` | Apresentação das opções disponíveis. |
| `executar()` | Controle do fluxo principal do programa. |
| `Procurar_Jogos()` | Pesquisa de jogos pelo AppID. |
| `Adicionar_Jogos()` | Adição de jogos à lista personalizada. |
| `Limpar_Lista()` | Remoção dos jogos selecionados. |
| `Grafico_Jogos_Populares()` | Visualização dos jogos mais populares. |
| `Treinar_Recomendador()` | Preparação e treinamento do sistema de recomendação. |
| `Jogos_Recomendados()` | Geração de recomendações a partir da lista personalizada. |

## Objetivos acadêmicos

O projeto busca aplicar conhecimentos de programação e análise de dados em um cenário real, explorando:

- Programação orientada a objetos;
- Manipulação e análise de dados;
- Manipulação de listas e DataFrames;
- Visualização gráfica;
- Vetorização de dados textuais;
- Aprendizado de máquina.
