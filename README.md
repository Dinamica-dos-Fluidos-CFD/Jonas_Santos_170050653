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

**Usaresmo como hipóteses :**
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

### Introdução:

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

# TESTE 01 : Validação para o ângulo de ataque de 0 graus.

### Para o cd obtemos :
![CD-grafico-1_angulo-0](https://user-images.githubusercontent.com/70406366/96936763-0ddde900-149d-11eb-8b8e-798a63cd93b4.png) 


**Podemos observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cd.**

### Para o cl obtemos :
![CL-grafico-1_angulo-0](https://user-images.githubusercontent.com/70406366/96936764-0f0f1600-149d-11eb-99e3-b9d0045ee290.png)
**Podemos observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cl.**

### Em relação aos residuais obtemos :
![Residuais_grafico-1_angulo-0_](https://user-images.githubusercontent.com/70406366/96936765-0f0f1600-149d-11eb-8c59-7857c2a815cf.png)
**Podemos observar um resultado satisfatório pois vemos o valor tentendo a zero.**

### Analisando os resultados de cd e cl :
![image](https://user-images.githubusercontent.com/70406366/96937140-dfacd900-149d-11eb-8774-e524019273f1.png)

**No início do projeto estipulamos um erro aceitável de até 5%**
**para isso vamos primeiramente comparar os nossos valores obtidos para o ângulo de ataque de 0 graus com os resultados que podemos obter acessando: https://turbmodels.larc.nasa.gov/naca0012_val.html.**

![naca tabela](https://user-images.githubusercontent.com/70406366/96937702-26e79980-149f-11eb-9f62-76edfe39d707.PNG)

**Sendo a fórmula do erro :**

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

**Substituindo os valores** 

![image](https://user-images.githubusercontent.com/70406366/96937563-c8bab680-149e-11eb-95e4-00db29895dcb.png)

**Enquanto isso para cl segundo o site https://turbmodels.larc.nasa.gov/naca0012_val.html possue valor de aproximadamente zero enquanto na nossa simulação optemos um valor muito pequeno sendo próximo de zero (cl = 1.470869e-06)**

**O erro obtido foi menor que o esperado validando assim o método.Assim o histórico de convergência do cálculo está adequado**

### Tempo de resposta 
 **Nessa simulação ultilizamos como parametros 5000 interações ,um reporting interval de 10 tempos e um profile update de 10 intervalos.**
 **Resultando por volta de 10 minutos o tempo de processamento.**

# Análise dos gráficos de contorno

### Pressão

![image](https://user-images.githubusercontent.com/70406366/97062101-c96f4d80-156f-11eb-945d-b0ac3c6c4f43.png)


**Podemos observar que o ponto de maior pressão se encontra no bordo de ataque ,enquanto no intradoso e extradoso posuem gradientes de pressão similares.**

### velocidade

![image](https://user-images.githubusercontent.com/70406366/97062139-f4f23800-156f-11eb-8097-b5f48f22f366.png)


**Nota-se que os pontos de maior velocidade se encontram no intradoso e no extradoso do perfil.**

### Wall plus *vs* position

![image](https://user-images.githubusercontent.com/70406366/97062203-371b7980-1570-11eb-911e-497d41e36a2a.png)


# TESTE 2 : Análise para o ângulo de ataque de 12 graus

**Precisamos dos valores do seno e cosseno para o ataque de 12 graus.**

![image](https://user-images.githubusercontent.com/70406366/97062754-b447ee00-1572-11eb-8ec0-0403632ab75b.png)


![image](https://user-images.githubusercontent.com/70406366/97062796-e22d3280-1572-11eb-89d3-94652433dc4d.png)

**Depois, mudamos os Parâmetros de entrada nas condições de borda.**

![image](https://user-images.githubusercontent.com/70406366/97062989-c0807b00-1573-11eb-8f2d-ba19044fc13d.png)

**Muldamos o repositório de definições tanto do Drag quanto do lift.**

![image](https://user-images.githubusercontent.com/70406366/97063053-09d0ca80-1574-11eb-992a-9b5f82426cc7.png)
![image](https://user-images.githubusercontent.com/70406366/97063134-59af9180-1574-11eb-8b73-5e2fa8eac134.png)

**Lembrando que no valor de X do lift colocamos o - sin(12), pois lift e drag são sempre relativos a movimentação do fluido. Sendo lift perpendicular ao drag enquanto o drag está na direção do movimento do fluido.**

### Avaliando os valores obtidos

**A pertir dessa simulação obtemos para os valores residuais:**

![image](https://user-images.githubusercontent.com/70406366/97064648-da26c000-157d-11eb-8934-7542d0799ec4.png)

**Podemos observar um resultado satisfatório pois vemos os valores dos residuais tentendo a valores próximos de zero.**


**Para os valores de cl:**

![image](https://user-images.githubusercontent.com/70406366/97064680-13f7c680-157e-11eb-87de-84fe9d804d92.png)

**Podemos observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cl.**

**Para os valores de cd:**

![image](https://user-images.githubusercontent.com/70406366/97064688-2bcf4a80-157e-11eb-8920-ae0258cff523.png)

**Podemos observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cd.**

### Comparando os valores e calculando o erro:

![image](https://user-images.githubusercontent.com/70406366/97064634-b6637a00-157d-11eb-98cd-6c72a05e6022.png)

**Ultilizando como referência os valores tabelados no site https://turbmodels.larc.nasa.gov/NACA0012_validation/CLCD_Ladson_expdata.dat .Obtemos :**

![image](https://user-images.githubusercontent.com/70406366/97063444-2ec63d00-1576-11eb-8104-8f1a56428b7a.png) 

**Dessa maneira o erro do cl será de :**

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

![image](https://user-images.githubusercontent.com/70406366/97064894-f3c90700-157f-11eb-9f95-6b013a4ee0e4.png)

**enquanto o do cd:**

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

![image](https://user-images.githubusercontent.com/70406366/97065041-f37d3b80-1580-11eb-81bd-98b3dc18d169.png)

# Gráficos das condições de contorno

### Pressão

![image](https://user-images.githubusercontent.com/70406366/97065217-8074c480-1582-11eb-8016-af6b422333f7.png)

### Velocidade

![image](https://user-images.githubusercontent.com/70406366/97065230-92566780-1582-11eb-8eb3-1d98990b12f5.png)

### Turbulence viscosity ratio

![image](https://user-images.githubusercontent.com/70406366/97065389-540d7800-1583-11eb-9c57-7021ed467847.png)

### Tubulence Wall pluss

![image](https://user-images.githubusercontent.com/70406366/97065452-bcf4f000-1583-11eb-9fa5-abc870404094.png)

# Conclusão
**Pontanto ,de maneira geral,segundo os gráficos acima não está ocorendo o fenômeno de *stall* para o ángulo de ataque de 12 graus.A simulação apresentou resultados qualitativos para fazermos análises de cada parte,como também quantitativos.O comportamento apresentado nos gráficos de velocidade e pressão estão de acordo com a realidade do escoamento**

# Referências

Fox, R.W., McDonald, A.T. and Pritchard, P.J.; “ Introdução à Mecânica dos Fluidos”, LTC, 6a ed. (2004)


Anderson Jr., John D., Mateus, Fundamentos de Engenharia Aeronáutica: Introdução ao Voo 6aed.


White, F.M., "Viscous Flow", McGraw Hill, 3rd ed., 2006.

**sites:**

https://turbmodels.larc.nasa.gov/naca0012_val.html


https://www.youtube.com/watch?v=TAqhMwm4mLg&t=2615s&ab_channel=AnthonyT

https://referenciabibliografica.net/a/pt-br/ref/abnt

