# Jonas_Santos_170050653

**não apagar!**

**Problema 3**: No projeto de uma asa de uma aeronave, deseja-se saber o melhor aerofólio para este perfil. No entanto, deseja-se um valor de coeficiente de sustentação em torno de 0,8 para um ângulo de ataque de 12 graus. Para avaliação do aerofólio, escolheu-se o perfil NACA 0012. O projeto de CFD deve:

- Determinar, com a simulação, um valor de coeficientes de arrasto e sustentação para o aerofólio NACA 0012 para o ângulo de ataque de 12 graus.
- Determinar se está ocorrendo o fenômeno de *stall* neste ângulo de ataque.
- Usando a simulação apresentada, realizar um estudo paramétrico da modelagem da turbulência para determinar cenários de desempenho aerodinâmico do perfil

**não apagar!**


 # Projeto de Dinâmica dos Fluidos Computacional em volta do perfil aerofólio da NACA0012
  
  
  
## 1. Modelagem

### 1.1 Objetivo
O objetivo é a análise bidimensional do escoamento ao redor do aerofólio da NACA0012 utilizando como recurso o ANSYS Fluent Software. Utilizando como referência o repositório da Nasa. Tal análise permitirá avaliar parâmetros do escoamento como: de pressão, velocidade e turbulência ao redor das bordas do aerofólio a fim de determinar se estar ocorrendo o fenômeno de stall para o ângulo de ataque de 12 graus.

   
  ### 1.2 Requisitos de Solução
O intuito desse projeto é obter um modelo de cálculo computacional que nos forneça:
 * Valores de arrasto e de sustentação para o ângulo de ataque de 12 graus;
 * Obter informações acerca do stall deste ângulo de ataque.

  
  ### 1.3 Finalidade do Projeto
  O projeto possui finalidade acadêmica com o intuito de trabalhar habilidades requeridas para realizar um estudo paramétrico de simulação em Dinâmica dos Fluidos Computacional (CFD). Requerido tanto no meio acadêmico quanto na indústria.
  
  ### 1.4 Hipótese de Simplificações 
  Com o intuito de simplificar a modelagem do problema, facilitar as definições das condições de contorno, serão adotadas as seguintes hipóteses: 

 * Que o escoamento seja 2D;
 * Que o escoamento seja turbulento;
 * Isotérmico


  
  ### 1.5 Precisão dos Resultados 
Como as simulações em CFD é influenciada pela precisão dos resultados. A fim de obter resultados que convergem a uma margem aceitável determina-se um domínio ‘D’ de tal forma que seja 20 vezes o tamanho da corda a partir de um perfil do aerofólio com 200 pontos. Dessa forma estabelece como precisão mínima de 5%.

### 1.6 Geometria do Problema

![image](https://user-images.githubusercontent.com/70406366/100468027-50a16b00-30b2-11eb-9fd3-6be6d7592258.png)

<p align="center"> Figura 1: Domínio D <br/>
       

![image](https://user-images.githubusercontent.com/70406366/100468166-a2e28c00-30b2-11eb-90d7-ccc0395c2284.png)

<p align="center"> Figura 2: Perfil do aerofólio com 200 ponto <br/>
     
  ### 1.7 Metodologia
   A melhor metodologia a ser aplicada nesse caso é o estudo CFD pois tem como principal vantagem a facilidade da simulação visto que para realizar o mesmo estudo, como por exemplo, em túnel de vento normalmente envolvem a forte interação entre a estrutura do modelo e o escoamento. O que significa que não apenas a estrutura deve ser corretamente modelada, mas também o escoamento além de suas características especificas de acordo com o ambiente no qual será utilizada. Uma modelagem correta em túnel de vento resulta que os parâmetros adimensionais de semelhança sejam exatamente os mesmos na estrutura real e no modelo. Entretanto a duplicação completa desses parâmetros é impraticável ou na maioria das vezes impossível.

  
  ### 1.8 Prazo de Entrega
   O projeto é dividido em três etapas, sendo elas: Modelagem; Pré-Processamento e Processamento. O prazo de entrega para este trabalho será para o dia 04 de dezembro de 2020.Dessa forma a segmentação das principais partes sendo:


|Etapa do Projeto                            |Período   |
|--------------------------------------------|----------|
|1ª Etapa: Modelagem                         |10 dias   |
|2ª Etapa: Pré-Processamento                 |20 dias   |
|3ª Etapa: Processamento e Pós-Processamento |45 dias   |
|4ª Etapa: revisão                           |05 dias   |
    
## 2. Pré-Processamento

### 2.1 Domínio e Geometria
O domínio, nesse projeto, é uma região na qual será realizado os cálculos numéricos essa região contínua é discretizada por uma malha que representa pequenos volumes de controle.A geração de malha é um processo de transformação de um domínio contínuo para um domínio discreto.O domínio ao redor do aerofólio é de 20 vezes o tamanho da corda na vertical e 10 na horizontal. O perfil é traçado a partir de 200 pontos de modo a satisfazer a precisão requerida. 

![malha_1](https://user-images.githubusercontent.com/70406366/96933754-6c07cd80-1497-11eb-91ac-47b9c41f0d59.PNG)
### 2.2 Malha
A malha foi obtida a partir da segmentação do domínio em 6 partes gerando uma malha hexaédrica a partir do modelo SpalartAllmaras, ao redor do perfil (y+ menor do que 5). Sendo essa uma malha não estruturada composta de elementos quadriláteros com volumes finitos. Na condição da malha está adequada utilizam um software de calculadora online para o Y+.
![CodeCogsEqn](https://user-images.githubusercontent.com/70406366/96739589-53fc5500-1396-11eb-99d6-962d58b81128.gif)
Analisando a malha mais de perto para verificar se obedece a condição estipulada para Y+.

![image](https://user-images.githubusercontent.com/70406366/96936893-4e3d6700-149d-11eb-9460-4601acf3ab5f.png)

### 2.3 Inputs 
* número de Reynolds
![CodeCogsEqn](https://user-images.githubusercontent.com/70406366/96741737-873fe380-1398-11eb-9d46-aafaa55f6ffe.gif)
                                                                  
 * Re = 6000000


* Massa específica do ar  de 1,2754 kg/m3


 * Escoamento incompreensível (Ma<0.3)


*  u=88.65m/s


* Ma = 0.258

### 2.4 Escolhas do pré-processamento no Fluent
![setups](https://user-images.githubusercontent.com/70406366/96935217-02d58980-149a-11eb-8a48-e1ba31d8a1d2.jpg)


### 2.5 Recursos Computacionais
![image](https://user-images.githubusercontent.com/70406366/100551210-fb09c180-325d-11eb-86ee-62b25fcab986.png)

