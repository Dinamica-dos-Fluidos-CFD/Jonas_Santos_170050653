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

# Pré-Processamento:
### Domínio e geometria da malha 
Utilizarão um domínio ao redor do aerofólio de 20 vezes o tamanho da corda na vertical e 10 na horizontal, com um perfil traçado a partir de 200 pontos. A fim de satisfazer a precisão requerida. Segmentarão o domínio em 6 partes gerando uma malha hexaédrica a partir do modelo SpalartAllmaras ,ao redor do perfil (y+ menor do que 5) . Geraram uma malha não estruturada composta de elementos quadriláteros com volumes finitos.

![malha_1](https://user-images.githubusercontent.com/70406366/96933754-6c07cd80-1497-11eb-91ac-47b9c41f0d59.PNG)

Para verificam-se na hipótese da malha está adequada utilizaram um software de calculadora online para o Y+.

![CodeCogsEqn](https://user-images.githubusercontent.com/70406366/96739589-53fc5500-1396-11eb-99d6-962d58b81128.gif)
Verificaram que  estava  próximo do valor estipulado ,analisando a malha mais de perto .
![image](https://user-images.githubusercontent.com/70406366/96936893-4e3d6700-149d-11eb-9460-4601acf3ab5f.png)

### Inputs e considerações 
Utilizaram 88,65 m/s como velocidade para o ângulo de ataque de 0 graus e compararam com os resultados obtidos no repositório da NASA. Como os resultados estiverem na margem requerida da precisão seguiram com o intuito de obtermos os valores de cl e cd para o ângulo de 12 e nesse ponto verificarão   a existência ou não o fenômeno de stall.
O software  é inicializado de forma hibrida e a simulação é realizada com 5000 iterações.
![setups](https://user-images.githubusercontent.com/70406366/96935217-02d58980-149a-11eb-8a48-e1ba31d8a1d2.jpg)


### Capacidade computacional

![image](https://user-images.githubusercontent.com/70406366/96936153-ed615f00-149b-11eb-9535-44f8c48843ff.png)

# Processamento e Pós-Processamento:

### Abordagem 
Validam a metodologia utilizada ,empregam  um teste para o ângulo de ataque de 0 graus. Se os resultados forem menores ou iguais ao nosso critério de precisão prosseguirão com a simulação para o ângulo de ataque de 12 graus. Caso contrário retrocederão a modelagem.

### Validação para o ângulo de ataque de 0 graus.

**Para o cd obtêm**
![CD-grafico-1_angulo-0](https://user-images.githubusercontent.com/70406366/96936763-0ddde900-149d-11eb-8b8e-798a63cd93b4.png) 


Podem observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cd.

**Para o cl obtêm:**
![CL-grafico-1_angulo-0](https://user-images.githubusercontent.com/70406366/96936764-0f0f1600-149d-11eb-99e3-b9d0045ee290.png)
Podem observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cl.

**Em relação aos residuais obtêm :**


![Residuais_grafico-1_angulo-0_](https://user-images.githubusercontent.com/70406366/96936765-0f0f1600-149d-11eb-8c59-7857c2a815cf.png)

Podem observar um resultado satisfatório pois vemos o valor tendendo a zero.

** analisam-se os resultados de cd e cl :**


![image](https://user-images.githubusercontent.com/70406366/96937140-dfacd900-149d-11eb-8774-e524019273f1.png)

No início do projeto estipularam um erro aceitável de até 5%
Desse modo  compararão os  valores obtidos para o ângulo de ataque de 0 graus com os resultados que obtiveram no repositória da NACA . 

![naca tabela](https://user-images.githubusercontent.com/70406366/96937702-26e79980-149f-11eb-9f62-76edfe39d707.PNG)

Sendo a fórmula do erro :

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

Substituindo os valores

![image](https://user-images.githubusercontent.com/70406366/96937563-c8bab680-149e-11eb-95e4-00db29895dcb.png)

Da mesma maneira para o  cl segundo o site possui um valor de aproximadamente zero enquanto na  simulação obterão um valor muito pequeno sendo próximo de zero (cl = 1.470869e-06)

O erro obtido foi menor que o esperado validando assim o método. Assim o histórico de convergência do cálculo está adequado.

### Tempo de resposta 
 Nessa simulação utilizaram como parâmetros de  5000 interações ,um reporting interval de 10 tempos e um profile update de 10 intervalos. Para esta simulação, cada iteração ocorreu em uma média de 0,600s, dessa forma ao total foram aproximadamente 3000s para a realização das 5000 iterações para cada caso.

# Análise dos gráficos de contorno

### Pressão

![image](https://user-images.githubusercontent.com/70406366/97062101-c96f4d80-156f-11eb-945d-b0ac3c6c4f43.png)

Observam-se que o ponto de maior pressão se encontra no bordo de ataque, enquanto no intradorso e extradorso possuem gradientes de pressão similares.

### velocidade

![image](https://user-images.githubusercontent.com/70406366/97062139-f4f23800-156f-11eb-8097-b5f48f22f366.png)



Nota-se que os pontos de maior velocidade se encontram no intradorso e no extradorso do perfil.


### Wall plus *vs* position

![image](https://user-images.githubusercontent.com/70406366/97062203-371b7980-1570-11eb-911e-497d41e36a2a.png)
