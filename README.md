# Jonas_Santos_170050653

**não apagar!**

**Problema 3**: No projeto de uma asa de uma aeronave, deseja-se saber o melhor aerofólio para este perfil. No entanto, deseja-se um valor de coeficiente de sustentação em torno de 0,8 para um ângulo de ataque de 12 graus. Para avaliação do aerofólio, escolheu-se o perfil NACA 0012. O projeto de CFD deve:

- Determinar, com a simulação, um valor de coeficientes de arrasto e sustentação para o aerofólio NACA 0012 para o ângulo de ataque de 12 graus.
- Determinar se está ocorrendo o fenômeno de *stall* neste ângulo de ataque.
- Usando a simulação apresentada, realizar um estudo paramétrico da modelagem da turbulência para determinar cenários de desempenho aerodinâmico do perfil

**não apagar!**


 # Projeto de Dinâmica dos Fluidos Computacional em volta do perfil aerofólio da NACA0012
  
  
  
# Modelagem

## Objetivo e finalidade:
Realizam uma análise bidimensional com o aerofólio da NACA0012 utilizam como recurso o ANSYS Fluent Software. Determinarão o Cl e o CD  para o ângulo de ataque de 0º graus para validação  do método utilizado , adquirirão os gráficos de pressão , velocidade e turbulência ao redor das bordas do aerofólio.Com a finalidade de ser um estudo académico que  determina um valor de coeficiente de arrasto e sustentação para o aerofólio NACA 0012 para o ângulo de ataque de 12 graus. Assim ,aferirão  se está ocorrendo o fenômeno de *stall* neste ângulo de ataque.

## Requisitos:

O intuito desse projeto é obter um modelo de cálculo computacional que nos forneça:
 * valores de arrasto e de sustentação para o ângulo de ataque de 12 graus;
 * Determinar se está ocorrendo o fenômeno de stall neste ângulo de ataque.

## Hipóteses 

Usarão como hipóteses:
 * que o escoamento seja 2D;
 * turbulento;
 * isotérmico
 * número de Reynolds
 
 
![CodeCogsEqn](https://user-images.githubusercontent.com/70406366/96741737-873fe380-1398-11eb-9d46-aafaa55f6ffe.gif)
                                                                  
 * Re = 6000000


* Massa específica do ar  de 1,2754 kg/m3


 * Escoamento incompreensível (Ma<0.3)


*  u=88.65m/s


* Ma = 0.258


* Em relação ao Y+ Utilizaremos calculadora online

![CodeCogsEqn](https://user-images.githubusercontent.com/70406366/96739589-53fc5500-1396-11eb-99d6-962d58b81128.gif)




## Precisão

Terão como  precisão mínima de 5%.Dessa maneira trabalharão com uma geometria de 200 pontos com um domínio de 20 vezes o tamanho da corda ,de 1 metro, na vertical e 10 vezes o tamanho da corda na horizontal.


## Prazos: 
O prazo de entrega para este trabalho será para o dia 04 de dezembro de 2020.Dessa forma segmentarão as principais partes sendo :

|Etapa do Projeto                            |Período   |
|--------------------------------------------|----------|
|1ª Etapa: Modelagem                         |10 dias   |
|2ª Etapa: Pré-Processamento                 |20 dias   |
|3ª Etapa: Processamento e Pós-Processamento |45 dias   |
|4ª Etapa: revisão                           |05 dias   |



## Opções além do CFD:

Poderiam  empregar além do CFD uma simulação em um túnel de vento, cálculos numéricos e tabelas no Excel. A principal vantagem do CFD entre as demais está na facilidade da simulação visto que para realizar o mesmo estudo, como por exemplo, testes em túnel de vento de modelos reduzidos geralmente envolvem a forte interação entre a estrutura do modelo e o escoamento. O significado imediato desta é que não apenas a estrutura deve ser corretamente modelada, mas também o escoamento, suas características próprias de acordo com o ambiente no qual será utilizada.


