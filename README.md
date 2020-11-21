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
Realizaremos uma análise bidimensional com o aerofólio da NACA0012 ultilizando como recurso o ANSYS Fluent Software.Determinaremos o Cl e o CD  para o âgulo de ataque de 0º graus para validação  do método ultilizado , além de obter os gráficos de pressão , velocidade e turbulência ao redor das bordas do aerofólio.Com a a finalidade de ser um estudo académico determinaremos  um valor de coeficiente de arrasto e sustentação para o aerofólio NACA 0012 para o ângulo de ataque de 12 graus.Ademais procuraremos determinar se está ocorrendo o fenômeno de *stall* neste ângulo de ataque.

## Requisitos:

O intuito desse projeto é obter um modelo de cálculo computacional que nos forneça:
 * valores de arrasto e de sustentação para o ângulo de ataque de 0 graus;
 * Comparar os valores obtidos com os encontrados no site https://turbmodels.larc.nasa.gov/naca0012_val.html para on ângulo de ataque de 0 graus;
 * Determinar os valores de cd e cl para o ângulo de ataque de 12 graus;
 * Comparar os valores obtidos com os encontrados no site https://turbmodels.larc.nasa.gov/naca0012_val.html para o ângulo de ataque de 12 graus;
 * Determinar se está ocorrendo o fenômeno de stall neste ângulo de ataque.

## Hipóteses 

Usaresmo como hipóteses :
 * que o escoamento seja 2D;
 * turbulento;
 * isotérmico
 * número de Reynolds
 
 
![CodeCogsEqn](https://user-images.githubusercontent.com/70406366/96741737-873fe380-1398-11eb-9d46-aafaa55f6ffe.gif)
                                                                  
 * Re = 6000000


* densidade do ar  de 1,2754 kg/m3


 * escoamento incompreensível (Ma<0.3)


*  u=88.65m/s


* Ma = 0.258


* Em relação ao Y+ Utilizaremos calculadora online

![CodeCogsEqn](https://user-images.githubusercontent.com/70406366/96739589-53fc5500-1396-11eb-99d6-962d58b81128.gif)




# Precisão

Teremos uma precisão mínima de arrasto e sutentação de 5%.


# Prazos: 
O prazo de entrega para este trabalho será para o dia 04 de dezembro de 2020.Dessa forma segmentaremos as principais partes sendo :

|Etapa do Projeto                            |Período   |
|--------------------------------------------|----------|
|1ª Etapa: Modelagem                         |10 dias   |
|2ª Etapa: Pré-Processamento                 |20 dias   |
|3ª Etapa: Processamento e Pós-Processamento |45 dias   |
|4ª Etapa: revisão                           |05 dias   |



# Opções além do CFD:

Podemos ultilizar além do CFD uma simulação em um tunel de vento,cálculos númericos e tabelas no Exel.



### Passo 1: Obteção do perfil NACA 0012

**Para obtermos o perfil NACA 0012 entraremos no site http://airfoiltools.com/airfoil/naca4digit, Estamos ultilizando um perfil com o tamanho da corda de 1000 milimetros e para traçarmos o perfil selecionamos 200 para traçarmos o perfil com o máximo de pontos que conseguimos e habilitamos Close Trailing edge para que nosso perfil venha fechado.**

![image](https://user-images.githubusercontent.com/70406366/96929732-fef13980-1490-11eb-9ab3-e6584f599537.png)

![numero de pontos](https://user-images.githubusercontent.com/70406366/95993724-d5d40780-0e05-11eb-9a12-c1b9fbad3d23.PNG)

### Passo 1.1: Geração de um arquivo do tipo texto com as cordenadas do perfil NACA 0012
**Em seguida apertamos o botão de *plot* e selecionamos a opção *Send to airfoil plotterAdd*.Que nos envia um arquivo do tipo texto que possamos abrir no Exel,Matlab,Octave...**
**O importate nesse arquivo será a obtenção das cordenadas em x,y,z para gerar o perfil no ANSYS Fluent Software.O arquivo que modificaremos tera que ter o seguinte cabeçalho:**

   **#group	Point	X_cord	Y_cord	Z_cord**
   
   
**Ao final desse procedimento teremos um arquivo txt equivalente a esse**[Naca0012v01_sala.txt](https://github.com/Dinamica-dos-Fluidos-CFD/Jonas_Santos_170050653/files/5425863/Naca0012v01_sala.txt).

### Passo 1.2 :Inserimos o perfil NACA 0012 no ANSYS (Fluent ou no CFX ) Software

* **Abrimos o ANSYS na parte de Analise de sistemas e escolhemos ultilizar  o ANSYS Fluent para essa simulação.**

* **Selecionamos a geometria** 

![image](https://user-images.githubusercontent.com/70406366/96931848-5644d900-1494-11eb-9563-12e645eb4ea3.png)

* **Abrimos o Software com Design Modeler e logo em seguida em Concept > 3D curve**

![image](https://user-images.githubusercontent.com/70406366/96932328-13373580-1495-11eb-8956-2eae25397dd9.png)

* **Aparecerá essa janela e deveremos alterar as unidades de medidas de metro para mílimetro,ultilizar a Base Plane em XY Plane.Em COordinates Files inserimos nosso arquivo de cordenadas txt** [Naca0012v01_sala.txt](https://github.com/Dinamica-dos-Fluidos-CFD/Jonas_Santos_170050653/files/5425863/Naca0012v01_sala.txt).

![image](https://user-images.githubusercontent.com/70406366/96933180-63fb5e00-1496-11eb-9122-d04bf4221c04.png)


* **Em seguida , editamos uma malha com domínio em que suas medidas são H1=10m (10 vezes o tamanho da corda),V1= 20m(20 vezes o tamanho da corda).Afim de  avaliarmos durante a simulação  a influência dos efeitos de parede no nosso projeto.**

![image](https://user-images.githubusercontent.com/70406366/96933626-2d721300-1497-11eb-9849-f8aecc1e266c.png)

* **Apertamos Generate produzindo:**

![malha_1](https://user-images.githubusercontent.com/70406366/96933754-6c07cd80-1497-11eb-91ac-47b9c41f0d59.PNG)


### Passo 1.3: Avaliação da malha 

**O domínio usado para o estudo é de 20 vezes o tamanho da corda na vertical e 10 vezes o tamanho da corda na horizontal nos proporcionando um Y+ de aproximadamente** ![y+](https://user-images.githubusercontent.com/70406366/96887655-2decb880-145b-11eb-9b05-8e8b6d971e6d.gif)

**Avaliando a malha de perto (nas bordas do aerofólio ) o nosso Y+ tem um valor de  aproximadamente** ![y+](https://user-images.githubusercontent.com/70406366/96887655-2decb880-145b-11eb-9b05-8e8b6d971e6d.gif)


![malha perto do aerofolio](https://user-images.githubusercontent.com/70406366/96934086-0405b700-1498-11eb-808e-e8f6fc0845f1.PNG)
![image](https://user-images.githubusercontent.com/70406366/96936893-4e3d6700-149d-11eb-9460-4601acf3ab5f.png)



**Dessa maneira concluimos que nossa malha está adequada para prosseguirmos na simulação**

**O tipo de malha usada é do tipo não estruturada composta de elementos quadriláteros,o uso da malha não estruturada faz com que o código a ser programado seja mais complexo. Também impõe que se tenha que acessar a matriz de conectividade várias vezes, aumentando o número de operações na máquina em relação à malha estruturada.Com Volumes finitos**

# Setups

**Nesse ponto da simulação deveremos considerar alguns inputs para obter nossos resultados pretendidos**

 ![image](https://user-images.githubusercontent.com/70406366/96934894-69a67300-1499-11eb-8cc6-da5c1dfd8698.png)
 
**A seguir segue uma tabela detalhada dos principais  Setups**
![setups](https://user-images.githubusercontent.com/70406366/96935217-02d58980-149a-11eb-8a48-e1ba31d8a1d2.jpg)

# capacidade computacional

![image](https://user-images.githubusercontent.com/70406366/96936153-ed615f00-149b-11eb-9535-44f8c48843ff.png)


