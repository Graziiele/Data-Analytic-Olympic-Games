

![banner](https://user-images.githubusercontent.com/114547875/193154555-f1a34b04-3aa3-43c4-8251-30406623fd1f.jpg)

<h1>🥇🥈🥉 Data Analysis on the Tokyo Olympics in Python!</h1>

🟪 ***About:***                                                                        
  Esse repertório documenta dados públicos das olimpíadas de tokyo 2021 ([download](https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo)), baixado no [kaggle.com](https://www.kaggle.com/), onde avaliei o top 3 países que tiveram o maior desempenho nos jogos e a desigualdade de homens e mulheres em cada esporte. Foi administrado por [@gahogg](https://github.com/gahogg)
 
-------------------------------------------------------------------------------------------------------------------------------------------------------------
 🚀***Languages/Sites:***                                                                    
 * [Python](https://www.python.org/)
 * [SQL](https://www.microsoft.com/pt-br/sql-server/sql-server-downloads)
 * [Google Colab](https://colab.research.google.com/)
 * [kaggle](https://www.kaggle.com/)
 ------------------------------------------------------------------------------------------------------------------------------------------------------------
 📋***Datasets:***                                       
* Athletes
* Coaches 
* Gender
* Teams participating 
-------------------------------------------------------------------------------------------------------------------------------------------------------------
🔥***Configurando ambiente no Google Colab:***
~~~Python
!pip install kaggle #Instlando para baixar o dataset diretamento pelo google colab --
!pip install --upgrade plotly #Biblioteca Principal usada para criar os gráficos
!pip install pyspark #Biblioteca usada para grande quantidade de dados
import pyspark
import pandas as pd
~~~
-------------------------------------------------------------------------------------------------------------------------------------------------------------
📋***Exemplo de tabela***
~~~Python
#Mostrando tabela do rank organizado por ordem quantidade de medalhas por país
medals.sort_values('Rank by Total', inplace=True)
medals.head(5)
~~~

Rank      | Team/NOC | Gold | Silver | Bronze| Total |Rank by Total|
--------- | ---------|------|--------|-------|-------|-------------|
 1 | USA  | 39       | 41   | 33     | 113   | 1
 2 | China| 38       | 32   | 18     | 88	   | 2
5 | ROC   | 20       | 28   | 23     | 71    | 3 
4 | Great Britain|22 | 21   | 22     | 65    | 4 
3 | Japan | 27       | 14	  | 17     | 58    | 5
-------------------------------------------------------------------------------------------------------------------------------------------------------------
📊***Gráfio analisando o número de medalha por países:***
~~~python
#Criando gráfico com a biblioteca ploty
import plotly.express as px
fig = px.bar(medals, x='Team/NOC', y=['Gold', 'Silver', 'Bronze'],
color_discrete_sequence =['gold', 'silver', 
'black'],title='Number of medals won by each country')
fig.show()
~~~
![grafico das medalhas](https://user-images.githubusercontent.com/114547875/193152092-496512cf-6252-498f-b0d9-fd0b6fbffaea.png)
-------------------------------------------------------------------------------------------------------------------------------------------------------------
📊***Gráfico analisando a quantidade de treinadores por paises:***

~~~Python
fig = px.bar(pd_coaches_query, x='NOC', y='count', color='count',title='Number of coaches from each country')
fig.show()
~~~

![grafico de calor](https://user-images.githubusercontent.com/114547875/193154868-75e55872-0ec6-4a05-9e25-56ee9aae8bbe.png)

