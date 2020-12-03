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
 * Isotérmico.


  
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


![image](https://user-images.githubusercontent.com/70406366/100800929-07c91980-3406-11eb-9a0d-6cf6ec7a4e72.png)



Analisando a malha mais de perto para verificar se obedece a condição estipulada para Y+.

![image](https://user-images.githubusercontent.com/70406366/96936893-4e3d6700-149d-11eb-9460-4601acf3ab5f.png)

Visto que para o número de Reynolds estabelecido nesse projeto estabeleceram o valor de Y plus < 1. O Y+ fornece uma distância entre a superfície do aerofólio até a parede menor ou igual a 4.5e-6. Ele é necessário para essa simulação para avaliação da malha estabelecida.  Dessa forma como o Y+ foi satisfeito a malha gerada é de alta qualidade. 

### 2.3 Inputs 
* Re = 6000000;

* Massa específica do ar  de 1,2754 kg/m3;


 * Escoamento incompreensível (Ma<0.3);


*  u=88.65m/s;


* Ma = 0.258.

### 2.4 Escolhas do pré-processamento no Fluent
A partir do repositório da Nasa, utilizado na validação de resultados e comprovação dos métodos utilizados nessa simulação, tem-se a velocidade e ângulo de ataque da entrada de fluido. Estes valores são de  88,65m/s e 0ºgraus.Entretanto o objetivo desse projeto é obter os coeficientes de sustentação e arrasto para o ângulo de 12ºgraus além de obter Informações acerca do stall deste ângulo de ataque. O software é inicializado de forma hibrida e a simulação é realizada com 5000 iterações.
A seguir os principais valores de entrada:

| Número de Reynolds               	|6000000       |
|-----------------------------------|--------------|
| Massa específica do ar                   |1,2754 kg/m3  |
|Velocidade	                        |u=88.65m/s    |
|Escoamento incompressível (Ma<0.3)	|Ma = 0.258    |
|Viscosidade	                       |1.81E-5 Km /ms|

|Para traçar o domínio| | 
|-----------------------------------|--------------|	
|H			 |H1=10m|
|V	|V1=20m|


|Solver| |
|-----------------------------------|--------------|	
|Pressure-Based	|Velocity formulation:Absolute|
|Time : steady	|2D Space planer|
	
	
|Viscosus Model| |
|-----------------------------------|--------------|	
| 		         |Scarlat-Allaras ( 1 eqn)  |
|Scarlat-Allaras          |	Straing velocity based |
|Options	          |Curvature correction     |
	
	
| Inlet| |
|-----------------------------------|--------------|	
|Velocity Specification Method	|Magnitude and direction|
|Velocity magnitude	              |88.65 m/s                           |

|Turbulence | |	
|-----------------------------------|--------------|
|Specfication method	               |Turbulance Viscosity radio|
|Turbulence viscosity ratio	 |1                                             |
	
	
|Outlet||
|-----------------------------------|--------------|	
|Specfication method|	Turbulance Viscosity radio|
|Turbulence viscosity ratio|	1|
	
	
|Wall|	|
|-----------------------------------|--------------|
|Wall motion	|Stationary wall|
|Shear condition		|no slip|

|Wall roughness| |
|-----------------------------------|--------------|	
|Roughness models		|	standard|
|Roughness height(m)		|0|
|Roughness constant		|0.5|
	
	
|Reference Values|	|
|-----------------------------------|--------------|
|Area(m2)                                      |	1 |
|Density(kg/m3)	              |1.225      |
|Depth(m)	                            |              1|
|Enthalp(j/kg)	                            |0              |
|Lenght(m)	                            |1              |  
|Pressure(pa)	                            |0              |
|Temperature(K)	              |288.16    |
|Velocity(m/s)	                            |1              |
|Viscosity(kg/m-s)	              |1,79E-01|
|Ratio of specific heats	              |1.4           |
|Yplus for heat tran.coef 	|300          |



O modelo para escoamento SpalartAllmaras utiliza apenas 1 equação para descrever o problema ele é baseado em deformação e vorticidade. O escoamento estabelecido como 2D, em regime permanente, sendo incompreensível (Ma<0.3)e isotérmico. Os parâmetros de entrada utilizam o método magnitude and Direction que será utilizado para mudar o ângulo de ataque de 0º para 12º graus.

### 2.5 Recursos Computacionais
![image](https://user-images.githubusercontent.com/70406366/100551210-fb09c180-325d-11eb-86ee-62b25fcab986.png)

## 3. Processamento e Pós-Processamento:

### 3.1 histórico de convergência
Emprega-se um teste para o ângulo de ataque de 0° graus a fim de comparar a convergência obtida com o repositório da NASA ,seguindo os critérios de precisão estabelecidos nesse projeto.

![CD-grafico-1_angulo-0](https://user-images.githubusercontent.com/70406366/96936763-0ddde900-149d-11eb-8b8e-798a63cd93b4.png)

<p align="center"> Figura 5: cd para o ângulo de ataque de 0°graus <br/>
	
![CL-grafico-1_angulo-0](https://user-images.githubusercontent.com/70406366/96936764-0f0f1600-149d-11eb-99e3-b9d0045ee290.png)

<p align="center"> Figura 6: cl para o ângulo de ataque de 0°graus <br/>
	
	
No início do projeto foi estipulado um erro aceitável de até 5% para isso compara-se os valores obtidos de cl e cd  para o esse ângulo de ataque com o repositório de referência.


![image](https://user-images.githubusercontent.com/70406366/96937140-dfacd900-149d-11eb-8774-e524019273f1.png)

![naca tabela](https://user-images.githubusercontent.com/70406366/96937702-26e79980-149f-11eb-9f62-76edfe39d707.PNG)

Sendo a fórmula do erro:

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

Substituindo os valores

![image](https://user-images.githubusercontent.com/70406366/96937563-c8bab680-149e-11eb-95e4-00db29895dcb.png)



Para o cl de cordo com o repositório da NASA possui valor aproximadamente zero.  Nesse projeto obtém-se o valor cl = 1.470869e-06, muito próximo do que foi requerido. Como o erro foi menor que o estipulado para esse projeto o histórico de convergência do cálculo está adequado.

### 3.2 Residuais 

Os residuais precisam diminuir para 1e-3. Então, isso significa que não importa de onde o residual começa, ele deve finalmente diminuir para 1e-3. Como nessa simulação os resíduos se encontram em valores próximos a 1e-05, significando que o resultado convergiu bem. 

![Residuais_grafico-1_angulo-0_](https://user-images.githubusercontent.com/70406366/96936765-0f0f1600-149d-11eb-8c59-7857c2a815cf.png)


<p align="center"> Figura 7: residuais para o ângulo de ataque de 0°graus <br/>
	
	
### 3.4 Tempo de Processamento 


A inicialização ocorreu de forma hibrida com 5000 interações. Cada interação varia em 1e-4. Cada interação ocorreu média de 0,600s.Dessa forma o processo de simulação geral teve  aproximadamente 3000s  .


### 3.5 Gráficos das condições de contorno 

Observa-se que o ponto de maior pressão se encontra no bordo de ataque, enquanto no intradorso e extradorso possuem gradientes de pressão similares. Nota-se que os pontos de maior velocidade se encontram no intradorso e no extradorso do aerofólio.O que corresponde a uma representação satisfatória da realidade do escoamento. 

![image](https://user-images.githubusercontent.com/70406366/97062101-c96f4d80-156f-11eb-945d-b0ac3c6c4f43.png)

<p align="center"> Figura 8: Pressão para o ângulo de ataque de 0°graus <br/>
	
![image](https://user-images.githubusercontent.com/70406366/97062139-f4f23800-156f-11eb-8097-b5f48f22f366.png)

<p align="center"> Figura 9: velocidade para o ângulo de ataque de 0°graus <br/>
	
![image](https://user-images.githubusercontent.com/70406366/97062203-371b7980-1570-11eb-911e-497d41e36a2a.png)

<p align="center"> Figura 10:  Wall plus *vs* position para o ângulo de ataque de 0°graus <br/>
	
## 4. Análise para o ângulo de ataque de 12 graus
Como objetivo do projeto é realizar uma análise que permitirá avaliar parâmetros do escoamento como: de pressão, velocidade e turbulência ao redor das bordas do aerofólio a fim de determinar se estar ocorrendo o fenômeno de stall para o ângulo de ataque de 12 graus. Assim deverão substituir os valores de setup em relação ao ângulo de ataque assim utilizarão os valores de seno e cosseno para o ataque de 12 graus.

![image](https://user-images.githubusercontent.com/70406366/97062754-b447ee00-1572-11eb-8ec0-0403632ab75b.png)


![image](https://user-images.githubusercontent.com/70406366/97062796-e22d3280-1572-11eb-89d3-94652433dc4d.png)

Substitui-se os parâmetros de entrada nas condições de borda.

![image](https://user-images.githubusercontent.com/70406366/97062989-c0807b00-1573-11eb-8f2d-ba19044fc13d.png)

 o repositório de definições tanto do Drag quanto do lift ficam:

![image](https://user-images.githubusercontent.com/70406366/97063053-09d0ca80-1574-11eb-992a-9b5f82426cc7.png)
![image](https://user-images.githubusercontent.com/70406366/97063134-59af9180-1574-11eb-8b73-5e2fa8eac134.png)

É importante salientar que em relação ao valor de X do lift colocarão - sin(12), pois lift e drag são sempre relativos a movimentação do fluido. Sendo lift perpendicular ao drag enquanto o drag está na direção do movimento do fluido. 

### 4.1 Avaliando os valores obtidos

![image](https://user-images.githubusercontent.com/70406366/97064648-da26c000-157d-11eb-8934-7542d0799ec4.png)

<p align="center"> Figura 11: valores residuais para o ângulo de ataque de 12°graus <br/>

![image](https://user-images.githubusercontent.com/70406366/97064680-13f7c680-157e-11eb-87de-84fe9d804d92.png)

<p align="center"> Figura 12: valores de cl para o ângulo de ataque de 12°graus <br/>


![image](https://user-images.githubusercontent.com/70406366/97064688-2bcf4a80-157e-11eb-8920-ae0258cff523.png)
<p align="center"> Figura 13: valores de cd para o ângulo de ataque de 12°graus <br/>

Comparando os valores e calculando o erro:

![image](https://user-images.githubusercontent.com/70406366/97064634-b6637a00-157d-11eb-98cd-6c72a05e6022.png)

Utiliza como referência os valores tabelados no repositório da NASA. Obtém-se:

![image](https://user-images.githubusercontent.com/70406366/97063444-2ec63d00-1576-11eb-8104-8f1a56428b7a.png) 

Dessa maneira o erro do cl será de:

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

![image](https://user-images.githubusercontent.com/70406366/97064894-f3c90700-157f-11eb-9f95-6b013a4ee0e4.png)

enquanto o do cd:

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

![image](https://user-images.githubusercontent.com/70406366/97065041-f37d3b80-1580-11eb-81bd-98b3dc18d169.png)


### 4.2 Gráficos das condições de contorno

Percebe-se que com o aumento do ângulo de ataque houve, como esperado, uma mudança significativa entre as diferenças de pressão no intradorso quanto no extradorso. Observa-se que a pressão na parte inferior do perfil é maior que na parte superior. Nota-se com o aumento do ângulo de ataque as velocidades ao logo do perfil não estão mais constantes quanto guando estava posicionada em 0 graus.

![image](https://user-images.githubusercontent.com/70406366/97065217-8074c480-1582-11eb-8016-af6b422333f7.png)

<p align="center"> Figura 14: Pressão para o ângulo de ataque de 12°graus <br/>

![image](https://user-images.githubusercontent.com/70406366/97065230-92566780-1582-11eb-8eb3-1d98990b12f5.png)

<p align="center"> Figura 15: Velocidade para o ângulo de ataque de 12°graus <br/>



![image](https://user-images.githubusercontent.com/70406366/97065389-540d7800-1583-11eb-9c57-7021ed467847.png)
<p align="center"> Figura 16:Turbulence viscosity ratio para o ângulo de ataque de 12°graus <br/>



![image](https://user-images.githubusercontent.com/70406366/97065452-bcf4f000-1583-11eb-9fa5-abc870404094.png)

<p align="center"> Figura 16: Tubulence Wall pluss para o ângulo de ataque de 12°graus <br/>




# Conclusão

Pontanto ,de maneira geral,segundo os gráficos acima não está ocorendo o fenômeno de *stall* para o ángulo de ataque de 12 graus.A simulação apresentou resultados qualitativos,pois tivemos uma simulação gráfica aceitável tanto para velocidade quanto para pressão,condizentes com a realidade do escoamento.Como também quantitativos,pois tivemos erros para o calculo de cd e cl inferiores a 5%.

# Referências

Fox, R.W., McDonald, A.T. and Pritchard, P.J.; “ Introdução à Mecânica dos Fluidos”, LTC, 6a ed. (2004)


Anderson Jr., John D., Mateus, Fundamentos de Engenharia Aeronáutica: Introdução ao Voo 6aed.

