# Sales Prediction (Regression Project)

Projeto criado com o objetivo de desenvolver **um modelo de predição de preço de barcos baseado nas características do mesmo**, como: ano, tamanho, tipo de barco, tempo de uso (novo ou usado), material usado, etc. Novamente, segue-se a aplicação do passo a passo inicial para compreensão do desafio proposto <br/>

Para tanto, os seguintes passos listados abaixo foram adotados:
<br/>
Passo 1: Entendimento do Desafio<br/>
Passo 2: Entendimento da Área/Empresa<br/>
Passo 3: Extração/Obtenção de Dados<br/>
Passo 4: Ajuste de Dados (Tratamento/Limpeza)<br/>
Passo 5: Análise Exploratória<br/>
Passo 6: Modelagem + Algoritmos (Aqui que entra a Inteligência Artificial, se necessário)<br/>
Passo 7: Interpretação de Resultados<br/>

Com a lista de passos em mãos, o desenvolvimento do código seguiu o seguinte raciocínio:<br/>
I) importação das bibliotecas necessárias para a análise: Scikit-learn, Pandas, Matplotlib e Seaborn<br/>
II) leitura do arquivo .csv<br/>
III) visualização da tabela <br/>
IV) identificação da necessidade de remoção de valores vazios ou correção de tipo de valor incorreto<br/>
V) início da análise exploratória com a **visualização da correlação entre as colunas de características do barco com a de preço** por meio das bibliotecas Seaborn e Matplolib<br/>
VI) com o auxílio do **mapa de calor**, observa-se que a correlação é maior entre o preço e a largura (56%) e comprimento (58%) do barco do que com as demais características.e<br/>

<table border="1">
    <tr>
        <th>&nbsp;</th>
        <th>Correlação com o preço</th>
    </tr>
    <tr>
         <th>Largura</th>
        <td>0.56</td>
    </tr>
     <tr>
         <th>Tipo de barco</th>
        <td>0.29</td>
    </tr>
     <tr>
         <th>Ano</th>
        <td>0.11</td>
    </tr>
    <tr>
        <th>Comprimento</th>
        <td>0.58</td>
</table>
VII) separação dos dados em treino e teste, sendo 70% de treino para os modelos aprenderem e 30% de teste para testar se o modelo aprendeu corretamente<br/>
XI) por se tratar de um **desafio de regressão**, uma vez que os de valores de preço são contínuos, os modelos selecionados para o teste foram:  LinearRegression, RandomForestRegressor, KNeighborsRegressor e GradientBoostingRegressor<br/>
XII) treinamentos dos modelos<br/>
XIII) cálculo das previsões<br/>
XIV) comparação das previsões com o y_teste (venda) por meio da **métrica de R²** da biblioteca metrics do scikit-learn que indica o quão assertivo é o modelo empregado na explicação para o problema <br/>
XVI) resultado: melhor modelo para esse projeto é o **Random Forest, com 85,30% de R²**, enquanto os modelos de KNN, regressão linear e Gradient Boosting Regressor obtiveram, respectivamente, 81,28%, 44,90% e 84,30% <br/>

<table border="1">
    <tr>
        <th>&nbsp;</th>
        <th>R²</th>
    </tr>
    <tr>
        <th>Random Forest</th>
        <td>85.30%</td>
    </tr>
    <tr>
         <th>KNN</th>
        <td>81.28%</td>
    </tr>
     <tr>
         <th>Gradient Boosting Regressor</th>
        <td>84.30%</td>
    </tr>
    <tr>
        <th>Regressão linear</th>
        <td>44.90%</td>
</table>

XVII) execução de previsões com a base com novos dados<br/>
XVIII) a partir das características dos barcos fornecidas na nova base, observa-se que os **preços previstos para os três é de R$ 5.831,00, R$ 8.702,62 e R$ 18.362,35**, como pode ser visto pelas tabelas abaixo:

<br/>

<table border="1">
    <caption><b>Predição de Preços em R$</b></caption>
    <tr>
        <th>Barco 1</th>
        <th>Barco 2</th>
        <th>Barco 3</th>
    </tr>
    <tr>
        <td>5.831,00</td>
        <td>8.702,62</td>
        <td>18.362,35</td>
    </tr>
</table>

XIX) por fim, a criação do gráfico de barras indica que a **largura do barco foi a característica mais influente na determinação do preço para o modelo de Random Forest testado, com 52,59% de importância**, seguida pelo comprimento (23,53%) e pelo ano de fabricação (19,45%) <br/>
 <table border="1">
    <tr>
        <th>&nbsp;</th>
        <th>Importância para o R²</th>
    </tr>
    <tr>
        <th>Largura</th>
        <td>52.59%</td>
    </tr>
    <tr>
         <th>Comprimento</th>
        <td>23.53%</td>
    </tr>
    <tr>
        <th>Ano de fabricação</th>
        <td>19.45%</td>
</table>
