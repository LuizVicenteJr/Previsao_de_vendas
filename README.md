_______________________________________
# ROSSMANN STORE SALES PREDICTION


----------------------------
### Apresentação do Projeto:
----------------------------
 As lojas Rossmann são uma rede com mais de 3.000 drogarias espalhadas por 7 países europeus. A equipe de negócios sabe que as vendas podem ser influenciadas por fatores como:
 * promoções 
 * concorrentes próximos
 * feriados
 * sazonalidade

### Problema do negócio:
**A equipe de negócios afim de otimizar a operação,pede a equipe de dados um modelo com uma previsão das vendas de cada loja nas próximas 6 semanas**. Essa previsão será feita  a partir da base de dados histórica disponível em [kaggle](https://www.kaggle.com/c/rossmann-store-sales) .

### Ferramentas Utilizadas
* Python 3.8
* Principais pacotes : Jupyter, Pandas, Numpy, Matplotlib, Seaborn, Scikit-Learn

--------------------------------------------------------------------------------------------------------------------------------------------------------
 # A solução foi desenvolvida em 10 passos:
  -------------------------------------------------------------------------
  ### 1.0 DATA DESCRIPTION : Compreensão da base de dados, limpeza e tratamento dos dados faltantes e divisão entre variáveis numéricas e categóricas.
  
  ### 2.0 FEATURE ENGINEERING :Derivei novas variáveis a partir da variável data com o objetivo de compreender melhor como as vendas funcionavam no decorrer do tempo .
  
  ### 3.0 DATA FILTER : Filtrei atributos que não ajudariam na solução do problema e aprendizado do modelo como lojas fechadas e vendas iguais a zero.
  
  ### 4.0 Exploratory Data Analysis (EDA): Exploração visual dos dados em busca de compreender como cada variável impacta as vendas. 
  
  ![EDA](https://github.com/LuizVicenteJr/Rossman_Sales/blob/main/img/eda.png)
  
  ### 5.0 Hypotheses: Testei 11 hipóteses comuns em um negócio de vendas.O exemplo abaixo  desvalida a hipótese de que lojas com competidores mais próximos vendem menos .
  
  ![hipótese 2](https://github.com/LuizVicenteJr/Rossman_Sales/blob/main/img/competidores%20prox.png)
  
  
Outras hipóteses testadas no projeto:                                                            
                                                     
H1.Lojas com maior sortimentos deveriam vender mais                     

H3.Lojas com competidores à mais tempo deveriam vendem mais

H4.Lojas com promoções ativas por mais tempo deveriam vender mais

H5.Lojas com mais promoções consecutivas deveriam vender mais

H6.Lojas abertas durante o feriado de Natal deveriam vender mais         

H7.Lojas deveriam vender mais ao longo dos anos

H8.Lojas deveriam vender mais no segundo semestre do ano

H9.Lojas deveriam vender mais depois do dia 10 de cada mês

H10.Lojas deveriam vender menos aos finais de semana 

H11.Lojas deveriam vender menos durante os feriados escolares

### 6.0 DATA PREPARATION: Utilizei técnicas de pré processamento necessárias para a modelagem do aprendizado de máquina 

### 7.0 FEATURE SELECTION :Utilizei o algoritmo BORUTA para selecionar as variáveis mais significativas para o modelo 

### MACHINE LEARNING : Observei o desenvolvimento dos modelos:
 *Average Model
 *Linear Regression Model
 *Linear Regression Regularized Model - Lasso
 *Random Forest Regressor
 *XGBoost Regressor

### Após fazer a validação cruzada com 5  k-fold segui para a finalização do modelo com o XGBoost Regressor .
  
Model Name	        |    Mean Absolute Error	 |    Mean Absolute Percentage Error|       Root Mean Squared Error
------------------ |    -------------------  |    ---------------------------   |      -----------------------
XGBoost Regressor	 |       1030.28 +/-167.19 |    	0.14 +/- 0.02	               |         1478.26 +/- 229.79


### 9.0 HyperParameter Fine Tuning : Procurei os melhores valores para cada parâmetro testado ,aplicando no modelo final :

param_tuned = {
 'n_estimators':1000,
 'eta':0.01 ,
 'max_depth':5 ,
 'subsample': 0.1,
 'colsample_bytree':0.9 ,
 'min_child_weight':3 
 }
 
 ### e obtendo o resultado de :
 Model Name	     |    Mean Absolute Error	 | Mean Absolute Percentage Error 	    |    Root Mean Squared Error
---------------- | ----------------------  | ----------------------------------- |  ------------------------
XGBoost Regressor|    758.838068	          |          0.114224	                  |        1086.500289

### Business Performance: Após melhorar a performance do modelo,calculei o melhor e o pior cenário e a previsão de receita de cada loja.


Cenários:
|predictions|	:   R$287,220,224.00

|pior cenário|	:  R$286,370,792.50

|melhor cenário|:	R$288,069,647.95

------------------------------------------------
# Próximos passos :
 1- O modelo pode se tornar mais eficiente em um computador mais robusto .
 
 2- Deploy do modelo para produção 
 
 3- Com mais tempo é possível aperfeiçoar a sessão Feature Engineering, o que provavelmente resultaria na melhora do modelo .

---------------------------------------------------
 
