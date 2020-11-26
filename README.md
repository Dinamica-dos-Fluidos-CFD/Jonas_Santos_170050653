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
Realizaremos uma análise bidimensional com o aerofólio da NACA0012 utilizando como recurso o ANSYS Fluent Software. Determinaremos o Cl e o CD  para o ângulo de ataque de 0º graus para validação  do método utilizado , além de obter os gráficos de pressão , velocidade e turbulência ao redor das bordas do aerofólio.Com a a finalidade de ser um estudo académico determinaremos  um valor de coeficiente de arrasto e sustentação para o aerofólio NACA 0012 para o ângulo de ataque de 12 graus. Ademais procuraremos determinar se está ocorrendo o fenômeno de *stall* neste ângulo de ataque.

## Requisitos:

O intuito desse projeto é obter um modelo de cálculo computacional que nos forneça:
 * valores de arrasto e de sustentação para o ângulo de ataque de 12 graus;
 * Determinar se está ocorrendo o fenômeno de stall neste ângulo de ataque.

## Hipóteses 

Usaremos como hipóteses :
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

Teremos uma precisão mínima de 5%.Dessa maneira trabalharemos com uma geometria de 200 pontos com um domínio de 20 vezes o tamanho da corda ,de 1 metro, na vertical e 10 vezes o tamanho da corda na horizontal.


## Prazos: 
O prazo de entrega para este trabalho será para o dia 04 de dezembro de 2020.Dessa forma segmentaremos as principais partes sendo :

|Etapa do Projeto                            |Período   |
|--------------------------------------------|----------|
|1ª Etapa: Modelagem                         |10 dias   |
|2ª Etapa: Pré-Processamento                 |20 dias   |
|3ª Etapa: Processamento e Pós-Processamento |45 dias   |
|4ª Etapa: revisão                           |05 dias   |



## Opções além do CFD:

Podemos empregar além do CFD uma simulação em um túnel de vento, cálculos numéricos e tabelas no Excel. A principal vantagem do CFD entre as demais está na facilidade da simulação visto que para realizar o mesmo estudo, como por exemplo, testes em túnel de vento de modelos reduzidos geralmente envolvem a forte interação entre a estrutura do modelo e o escoamento. O significado imediato desta é que não apenas a estrutura deve ser corretamente modelada, mas também o escoamento, suas características próprias de acordo com o ambiente no qual será utilizada.

# Pré-Processamento:
### Domínio e geometria da malha 
Utilizamos um domínio ao redor do aerofólio de 20 vezes o tamanho da corda na vertical e 10 vezes o tamanho da corda na horizontal com um perfil traçado a partir de 200 pontos. A fim de satisfazer nossa precisão requerida. Segmentaremos o domínio em 6 partes gerando uma malha hexaédrica a partir do modelo SpalartAllmaras ,ao redor do perfil (y+ menor do que 5) .Geraremos uma malha não estruturada composta de elementos quadriláteros com volumes finitos.
Para verificarmos se a malha esta adequada  Utilizaremos calculadora online para o Y+

![CodeCogsEqn](https://user-images.githubusercontent.com/70406366/96739589-53fc5500-1396-11eb-99d6-962d58b81128.gif)
  verificaremos se esta próximo do valor estipulado analisando a malha mais de perto .
![image](https://user-images.githubusercontent.com/70406366/96936893-4e3d6700-149d-11eb-9460-4601acf3ab5f.png)

### Inputs e considerações 
Utilizaremos 88,65 m/s como velocidade para o ângulo de ataque de 0 graus e compararemos com os resultados obtidos no repositório da NASA. Se os resultados estiverem na margem requerida da precisão seguiremos com o intuito de obtermos os valores de cl e cd para o ângulo de 12 e nesse ponto verificaremos  a existência ou não o fenômeno de stall.
O software  é inicializado de forma hibrida e a simulação é realizada com 5000 iterações.
![setups](https://user-images.githubusercontent.com/70406366/96935217-02d58980-149a-11eb-8a48-e1ba31d8a1d2.jpg)


### Capacidade computacional

![image](https://user-images.githubusercontent.com/70406366/96936153-ed615f00-149b-11eb-9535-44f8c48843ff.png)

# Processamento e Pós-Processamento:

### Abordagem 
Com o intuito de validarmos a metodologia utilizada iremos realizar um teste para o ângulo de ataque de 0 graus. Se os resultados forem menores ou iguais ao nosso critério de precisão prosseguiremos com a simulação para o ângulo de ataque de 12 graus. Caso contrário refaremos a modelagem.

### Validação para o ângulo de ataque de 0 graus.

**Para o cd obtemos :**
![CD-grafico-1_angulo-0](https://user-images.githubusercontent.com/70406366/96936763-0ddde900-149d-11eb-8b8e-798a63cd93b4.png) 


Podemos observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cd.

**Para o cl obtemos :**
![CL-grafico-1_angulo-0](https://user-images.githubusercontent.com/70406366/96936764-0f0f1600-149d-11eb-99e3-b9d0045ee290.png)
Podemos observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cl.

**Em relação aos residuais obtemos :**


![Residuais_grafico-1_angulo-0_](https://user-images.githubusercontent.com/70406366/96936765-0f0f1600-149d-11eb-8c59-7857c2a815cf.png)

Podemos observar um resultado satisfatório pois vemos o valor tendendo a zero.

**Analisando os resultados de cd e cl :**


![image](https://user-images.githubusercontent.com/70406366/96937140-dfacd900-149d-11eb-8774-e524019273f1.png)

No início do projeto estipulamos um erro aceitável de até 5%
para isso vamos primeiramente comparar os nossos valores obtidos para o ângulo de ataque de 0 graus com os resultados que podemos obter acessando: https://turbmodels.larc.nasa.gov/naca0012_val.html.

![naca tabela](https://user-images.githubusercontent.com/70406366/96937702-26e79980-149f-11eb-9f62-76edfe39d707.PNG)

Sendo a fórmula do erro :

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

Substituindo os valores

![image](https://user-images.githubusercontent.com/70406366/96937563-c8bab680-149e-11eb-95e4-00db29895dcb.png)

Enquanto isso para cl segundo o site https://turbmodels.larc.nasa.gov/naca0012_val.html possuem valor de aproximadamente zero enquanto na nossa simulação optemos um valor muito pequeno sendo próximo de zero (cl = 1.470869e-06)

O erro obtido foi menor que o esperado validando assim o método. Assim o histórico de convergência do cálculo está adequado.

### Tempo de resposta 
 Nessa simulação utilizamos como parâmetros de  5000 interações ,um reporting interval de 10 tempos e um profile update de 10 intervalos.Para esta simulação, cada iteração ocorreu em uma média de 0,600s, dessa forma ao total foram aproximadamente 3000s para a realização das 5000 iterações para cada caso.









