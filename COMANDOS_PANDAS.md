# python_pandas
Comandos em python com pandas


#importa pandas que a ser usado com pd
import pandas as pd

#ler csv
df = pd.read_csv("nome.csv")

#mostra estrutura dos dados, defoult eh 5
df.head()

#salvar csv
novo_df.to_csv("nome.csv")

# isto retorna os tipos de dados das colunas
df.dtypes

#tupla com as dimensoes do dataFrame
df.shape

#lista os dados, incluindo valores  nulos
df.info

#tira uma media da coluna
media = df["coluna"].mean()

#tipo da coluna diagnosis linha 0
type(df['diagnosis'][0])

# isto retorna o número de valores únicos em cada coluna
df.nunique()

# isto retorna estatísticas descritivas úteis para cada coluna de dados
df.describe()

# isso também se aplicar ao comando `.tail()` que retorna as últimas linhas do dataframe
df.tail(2)

# Exibir o índice e rótulo de cada coluna
for i, v in enumerate(df.columns):
    print(i, v)

# selecionar todas as colunas desde 'id' até a última coluna relacionada à média
df_means = df.loc[:,'id':'fractal_dimension_mean']
df_means = df.iloc[:,:11]

#retorna quais valores sao nulos ou nao
df.isnull()

#substitui valores nulos da coluna pelo valor passado(inplace true diz para ele atualizar a mesma coluna, senao ele creia uma nova coluna)
df["coluna"].fillna(valor,inplace=True)

#verifica se existem linhas duplicadas
df.duplicated()

#apaga linhas duplicadas
df.drop_duplicates(inplace=True)

###########################
#GRAFICOS

#deixar ver os graficos em blocos
%matplotlib inline

# hist = colunas
# bar = barras
# pie = pizza
# box  = caixa
#scatter = dispersai
#funcao geral de graficos e kind eh o tipo de grafico
df.plot(kind="hist")

#funcao cria grafico de coluna pra cada coluna
df.hist()
#definindo altura e largura dos graficos
df.hist(figsize=(10,10))

#faz grafico apenas da coluna
df["coluna"].hist()

#grafico de dispersao
df.plot(x="colunax",y="colunay",kind="scatter")

#remove linhas com valores nulos
df_08 = df_08.dropna(axis=0, how='any')
