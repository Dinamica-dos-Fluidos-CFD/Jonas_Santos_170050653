# Jonas_Santos_170050653

 ![logo unb](https://user-images.githubusercontent.com/70406366/96888717-4b6e5200-145c-11eb-8023-084131205094.png) 
 # Projeto de Dinâmica dos Fluidos Computacional em volta do perfil aerofólio da NACA0012
  
  
  


#  Objetivo e finalidade:
**Realizaremos uma análise bidimensional com o aerofólio da NACA0012 ultilizando como recurso o ANSYS Fluent Software.Determinaremos o Cl e o CD  para o âgulo de ataque de 0º graus para validação  do método ultilizado , além de obter os gráficos de pressão , velocidade e turbulência ao redor das bordas do aerofólio.Com a a finalidade de ser um estudo académico determinaremos  um valor de coeficiente de arrasto e sustentação para o aerofólio NACA 0012 para o ângulo de ataque de 12 graus.Ademais procuraremos determinar se está ocorrendo o fenômeno de *stall* neste ângulo de ataque.**

# Requisitos:

**O intuito desse projeto é obter um modelo de cálculo computacional que nos forneça:**
 * **valores de arrasto e de sustentação para o ângulo de ataque de 0 graus;**
 * **Comparar os valores obtidos com os encontrados no site https://turbmodels.larc.nasa.gov/naca0012_val.html;**
 * **validarmos o método**
 * **Determinar os valores de cd e cl para o ângulo de ataque de 12 graus;**
 * **Comparar os valores obtidos com os encontrados no site https://turbmodels.larc.nasa.gov/naca0012_val.html;**
 * **validarmos os resultados para o ângulo de ataque de 12 graus;**
 * **realizar um estudo paramétrico da velocidade de entrada do escoamento,afim de obter os cenários de desempenho aerodinâmico do perfil.Iremos anasisar as velocidades até o limite de  Ma=(0,3),pois estamos trabalhando com a hipotése de escoamento incompressível**


# Hipóteses 

**Usaresmo como hipóteses :
 * **que o escoamento seja 2D;**
 * **turbulento;**
 * **isotérmico**
 * **número de Reynolds**
 
 
![CodeCogsEqn](https://user-images.githubusercontent.com/70406366/96741737-873fe380-1398-11eb-9d46-aafaa55f6ffe.gif)
                                                                  
  **Re = 6000000**


* **densidade do ar  de 1,2754 kg/m3**


 * **escoamento incompreensível (Ma<0.3)**


*  **u=88.65m/s**


* **Ma = 0.258**


* **Em relação ao Y+ Utilizaremos calculadora online**

![CodeCogsEqn](https://user-images.githubusercontent.com/70406366/96739589-53fc5500-1396-11eb-99d6-962d58b81128.gif)




# Precisão
**Teremos uma precisão mínima de arrasto e sutentação de 5%.**
# Prazos: 
**O prazo de entrega para este trabalho será para o dia 04 de dezembro de 2020.Dessa forma segmentaremos as principais partes sendo :**

|Etapa do Projeto                            |Período   |
|--------------------------------------------|----------|
|1ª Etapa: Modelagem                         |10 dias   |
|2ª Etapa: Pré-Processamento                 |20 dias   |
|3ª Etapa: Processamento e Pós-Processamento |45 dias   |
|4ª Etapa: revisão                           |05 dias   |



# Opções além do CFD:

**Podemos ultilizar além do CFD uma simulação em um tunel de vento,cálculos númericos e tabelas no Exel.**

# Modelagem

![775px-Lift-force-pt svg](https://user-images.githubusercontent.com/70406366/96885440-f715a300-1458-11eb-9152-e54a76a23338.png)


**Temos um perfil de aerofólio NACA 0012,com um secção bidimensional projetada para provocar variação na direção da velocidade de um fluido,no nosso caso o ar.A reação do ar sobre o aerofólio ,devido a variação na quantidade de movimento, podemos decompor em ângulos normais a direção de seu movimento.**

**As principais forças atuantes no  aerofólio são:**

* **Sustentação ;**
* **Arrasto;**
* **Empuxo;**
* **Peso.**

* **A sustentação é a componente da resultante perpendicular ao vento relativo.Ela pode ser decomposta em dois vetores que são a força de sustentação e a força de arrasto.Ela é denominada pela sequinte fórmula:**

![image](https://user-images.githubusercontent.com/70406366/96925387-75d70400-148a-11eb-9cfe-80dfcc083bf3.png)

* **O arrasto é gerada pela resistência do ar e tende a puxar o avião para trás, uma força oposta ao sentido de movimento.Ela é calculada pela sequinte fórmula:**

![formula arrasto](https://user-images.githubusercontent.com/70406366/96927474-7c1aaf80-148d-11eb-9123-64d9124ef67f.gif)


* **Empuxo gerado pelo motor do avião e tem a finalidade de movimentar o avião para frente,produzida por uma turbina ou hélice.Representado na fórmula a seguir por 'T'.**


![image](https://user-images.githubusercontent.com/70406366/96926559-17128a00-148c-11eb-9952-ee535b4b21c2.png)

**onde:** ![image](https://user-images.githubusercontent.com/70406366/96926699-4aedaf80-148c-11eb-8817-7e7bdb31d536.png) **é a taxa de massa em relação ao tempo e 'v' é a velocidade dos gases de exaustão.**

* **Peso é uma força que atua sempre na direção vertical e é consequência da força da gravidade.Ela é calculada pela sequinte fórmula:**

![image](https://user-images.githubusercontent.com/70406366/96926199-a53a4080-148b-11eb-9c2f-ccc0217091f2.png)

# Geometria 

**Estamos ultilizando um perfil NACA 0012 com o tamanho da corda de 1000 milimetros,e com 200 pontos para traçarmos o perfil.Estabelecemos um domíno onde a parede horizontal esta a 10 vezes o tamanho da corda e a horizontal 20 vezes o tamanho da corda ,para avaliarmos durante a simulação  a influência dos efeitos de parede no nosso projeto.**

![numero de pontos](https://user-images.githubusercontent.com/70406366/95993724-d5d40780-0e05-11eb-9a12-c1b9fbad3d23.PNG) 
  
  Fig Números de pontos
  
  ![image](https://user-images.githubusercontent.com/70406366/96740463-3da2c900-1397-11eb-8ec6-671f10f38ecd.png)
  
  Fig Geometria Aerofólio

 ![geometria](https://user-images.githubusercontent.com/70406366/96736287-d71bac00-1392-11eb-9b26-1cd477ba4365.png)

  Fig   Geometria da malha 
  
  ![WhatsApp Image 2020-10-15 at 20 01 33](https://user-images.githubusercontent.com/70406366/96740905-aa1dc800-1397-11eb-86af-37e567161650.jpeg)
  
  Fig Geometria da malha 2
  
  ![image](https://user-images.githubusercontent.com/70406366/96741454-2dd7b480-1398-11eb-8d9d-58cc01001e5d.png)
  

  Fig Desenho esquemático da modelagem do problema
# Modelagem do problema 
![775px-Lift-force-pt svg](https://user-images.githubusercontent.com/70406366/96885440-f715a300-1458-11eb-9152-e54a76a23338.png)

- Desenhos CAD mostrando a geometria do problema.
- Desenho esquemático da modelagem do problema.

![perfil 2](https://user-images.githubusercontent.com/70406366/96884949-79ea2e00-1458-11eb-930b-517b70a2b72d.png)
![perfil](https://user-images.githubusercontent.com/70406366/96884871-62ab4080-1458-11eb-977a-b748181ac513.png)
![775px-Lift-force-pt svg](https://user-images.githubusercontent.com/70406366/96885440-f715a300-1458-11eb-9152-e54a76a23338.png)


### 2.	Pré-Processamento:

A segunda etapa deverá conter as respostas para as seguintes perguntas:

- Quanto detalhado o domínio de cálculo precisa ser?
**O domínio usado para o estudo é de 20 vezes o tamanho da corda na vertical e 10 vezes o tamanho da corda na horizontal nos proporcionando um Y+ de aproximadamente** ![y+](https://user-images.githubusercontent.com/70406366/96887655-2decb880-145b-11eb-9b05-8e8b6d971e6d.gif)
- A geometria está adequada?
A geometria está adequada para o estudo pois ultilizmos a quantidade máxima de pontos oriundos do  site http://airfoiltools.com/airfoil/naca4digit?MNaca4DigitForm%5Bcamber%5D=0&MNaca4 
![numero de pontos](https://user-images.githubusercontent.com/70406366/95993724-d5d40780-0e05-11eb-9a12-c1b9fbad3d23.PNG)


- Que tipo de malha e método usar? Estruturada ou não-estruturada? Volumes Finitos ou Elementos Finitos?
**não estruturada composta de elementos quadriláteros,o uso da malha não estruturada faz com que o código a ser programado seja mais complexo. Também impõe que se tenha que acessar a matriz de conectividade várias vezes, aumentando o número de operações na máquina em relação à malha estruturada.Com Volumes finitos**
- Quais são as informações de entrada (Input) do problema?
****
- Que escolhas devem ser feitas em relação ao processamento da solução?
- Quais são os prazos e disponibilidade de capacidade computacional para a análise em questão? 

O projeto deverá conter nesta etapa:

- Descrição do pré-processamento feito no ANSYS.
- Imagens da malha de cálculo do problema.

### 3.	Processamento e Pós-Processamento:

A terceira etapa deverá conter as respostas para as seguintes perguntas:

- O histórico de convergência do cálculo está adequado?
- Quanto tempo a simulação está levando para ser processada?
- Os resíduos estão em valores aceitáveis?
- A simulação fornece resultados qualitativos?
- É possível calcular resultados quantitativos e qualitativos com o que a simulação calculou?
- Os resultados estão de acordo com a realidade física do escoamento?

O projeto deverá conter nesta etapa:

- Análise dos resultados obtidos.
- Comparação dos resultados numéricos com os resultados analíticos de cada problema.
- Imagens de visualização do escoamento.
- Análise dos resultados obtidos pelo estudo paramétrico.

