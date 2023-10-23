# Stock Price Prediction with Deep Learning and MLP: A Hybrid Approach
by David Panduro<br><br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/ea4a2b67-7dfa-43d6-9ef6-8d241eb1bd48)
<br><br>
CONTEXTO: <br>
Nos últimos meses temos acompanhado uma queda nas ações da Bolsa Brasileira, a mesma que vem diretamente proporcional a queda das ações da empresa Vale. Mas quem é a empresa Vale? <br>
A Vale é uma empresa mineradora multinacional brasileira. É uma das maiores empresas de mineração do mundo e também a maior produtora de minério de ferro. <br>Podemos definir, de maneira resumida, suas operações em duas alas de extrações: <br><br>
* Minerio de ferro das minas Brasileiras e a maior parte é importada para China.
* Metais básicos (níquel, cobre) para transição energética de carros elétricos.<br><br>

Já que o mercado dos metais básicos ainda é muito pequeno, então a Vale depende muito do minério de ferro e principalmente do preço de minério de ferrocotado na China.<br><br>
Disclaimer: Exitem básicamente 02 formas de vender aço:<br><br>
1. Crecimento populacional (+ nascem, - morrem).
2. Crecimento econômico.<br><br>

En contrapartida, a China tem mostrado Desacelaração no crecimento econômico e a taxa de natalidade vem caindo.<br><br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/b0f6f461-0827-4f29-b300-a0c8783102ba)<br><br>
Agora, consideraremos a rentabilidade da Vale3 (investindo R$. 100)<br><br>
* Sem reinvestimento dos dividendos ( últimos 10 anos): R$. 240.22
* Com reinvestimento dos dividendos ( últimos 10 anos): R$. 400.20<br><br>

Representando 65% A MAIS REINVESTINDO OS DIVIDENDOS.<br><br>

OBJETIVO:<br>
Nesse contexto, neste estúdo temos como objetivo, desenvolver a previsão de preços de ações da empresa Vale S.A.; da Bolsa de Valores Brasileira B3, mediante uma abordagem hibrida, combinando algoritmos de aprendizado profundo (LSTM) e multilayer perceptron (MLP). <br>Evaluaremos cada um dos resultados para concluir em qual dos cenários as previsões apresentam maior precisão.<br>
<br>
BASES:<br>
No estudo, consideramos dados de movimentações da Bolsa Brasileira, no período desde 2018-01-01 até 2023-06-30. Totalizando cinco (05) anos, mais os restantes seis (06) meses do 2023.
<br><br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/f794f9ed-efc7-4644-bf78-5a6ca1f6849e)<br>
Para o estudo utilizaremos o preço das ações no Fechamento diário.<br><br>

DISTRIBUIÇÂO DOS DADOS:<br>
A distribuição dos dados no periodo mostra seus picos de frequência mais altos ente o 40 e 60 de valor de fechamento.<br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/ab337980-e599-4c9e-b211-4f29e4b358f9)<br><br>

No histórico do preço das ações da Vale podemos observar que até o ano 2020 não tinha mostrado um crecimento substancial, e sem embargo, tinha conseguido uma estabilidade interessante.<br>
No periodo de pandemia, naturalmente apresentou uma queda no valor, mas imediatamente conseguiu se reeguer e mostrou um crecimento exponecial, para depois flutuar entre valores acima de 60 e 100.<br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/ce3a2ea8-0f0a-4581-bd09-8c39d37942cc)<br><br>

SIMULAÇÃO DE MONTE CARLO:<br>
Como ponto de partida aproveitamos para fazer uma Simulação de Monte Carlo, que pode servir como um baseline para determinar um range de cenários e com os que poderíamos trabalhar caso querramos nos localizar dentro de um melhor cenário e um pior cenário, para a partir disso gerar, definir ou planejar as nossas estrategias.<br>
A nossa simulação consiste em fazer a previsão dos proximos 70 passos (poco mais de 03 meses da Bolsa) e um range de 30 cenários.<br><br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/b8654c68-37d4-4503-9593-06210302fc48)<br><br>
O melhor cenário corresponde a um erro de 2.68 e o gráfico ficou como segue:<br><br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/96bf8e63-0434-48a8-a4b8-e112678d9678)<br><br>

PREVISÃO MULTILAYER PERCEPTRON (MLP):<br>
































