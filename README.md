# Stock Price Prediction with Deep Learning and MLP: A Hybrid Approach
by David Panduro<br><br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/ea4a2b67-7dfa-43d6-9ef6-8d241eb1bd48)
<br><br>
CONTEXTO: <br><br>
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

OBJETIVO:<br><br>
Nesse contexto, neste estúdo temos como objetivo, desenvolver a previsão de preços de ações da empresa Vale S.A.; da Bolsa de Valores Brasileira B3, mediante uma abordagem hibrida, combinando algoritmos de aprendizado profundo (LSTM) e multilayer perceptron (MLP). <br>Evaluaremos cada um dos resultados para concluir em qual dos cenários as previsões apresentam maior precisão.<br>
<br>
BASES:<br><br>
No estudo, consideramos dados de movimentações da Bolsa Brasileira, no período desde 2018-01-01 até 2023-06-30. Totalizando cinco (05) anos, mais os restantes seis (06) meses do 2023.
<br><br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/f794f9ed-efc7-4644-bf78-5a6ca1f6849e)<br>
Para o estudo utilizaremos o preço das ações no Fechamento diário.<br><br>

DISTRIBUIÇÂO DOS DADOS:<br><br>
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

PREVISÃO DE PREÇOS COM MULTILAYER PERCEPTRON (MLP):<br><br>
Também conhecido como rede neural feedforward, é um tipo de rede neural artificial que consiste em múltiplas camadas de neurônios, ou unidades de processamento, dispostas em camadas interconectadas.<br>
Consiste em três tipos principais de camadas de neurônios: a camada de entrada, uma ou mais camadas ocultas e a camada de saída.<br><br>
A seguir as fórmulas matemáticas básicas para um neurônio em uma camada oculta de um MLP:<br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/0acf0ec2-63e4-4d83-bed8-8d1f772d518c)<br><br>

As previsões foram executadas, considerando os próximos 70 passos da série MLP. Obtendo os seguintes resultados:<br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/5e3cd7af-3cee-4189-ae97-17538e8b34d6)<br><br>

**MSE: 3.45**<br><br>

PREVISÃO DE PREÇOS COM LONG SHORT-TERM MEMORY LSTM: <BR><BR>
É um tipo especial de unidade recorrente em redes neurais artificiais, projetada para capturar e lembrar informações de longo prazo em sequências de dados. <br>
A principal vantagem das LSTMs é a capacidade de lidar com o problema do desaparecimento de gradientes que ocorre em redes neurais recorrentes tradicionais. Graças às portas de controle, as LSTMs podem aprender a reter informações úteis e ignorar informações irrelevantes ao longo do tempo.<br><br>
Matemáticamente, existem diferentes equações que explicam o fluxo de uma LSTM, como por exemplo:<br><br>
* Equação de combinação de Entrada.
* Equação de combinação da porta de aquecimento.
* Atualização da célula de memória.
* Equação de atualização de célula de memória.
* Saída da LSTM.

Mostraremos só as duas úlimas representações matemáticas.<br><br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/a84d4164-971d-4423-bbf7-caff0b0c8d70)<br><br>
As previsões resultaram assim: <br>
![image](https://github.com/DavidPanduro/stock_price_prediction/assets/45201867/30c3ac19-0bd2-4e47-8d51-0e5a09da8527)<br><br>
**MSE: 3.11**<br><br>
































