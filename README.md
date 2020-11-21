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




## Precisão

Teremos uma precisão mínima de arrasto e sutentação de 5%.


## Prazos: 
O prazo de entrega para este trabalho será para o dia 04 de dezembro de 2020.Dessa forma segmentaremos as principais partes sendo :

|Etapa do Projeto                            |Período   |
|--------------------------------------------|----------|
|1ª Etapa: Modelagem                         |10 dias   |
|2ª Etapa: Pré-Processamento                 |20 dias   |
|3ª Etapa: Processamento e Pós-Processamento |45 dias   |
|4ª Etapa: revisão                           |05 dias   |



## Opções além do CFD:

Podemos ultilizar além do CFD uma simulação em um tunel de vento,cálculos númericos e tabelas no Exel.


# Pré-processamento

## Domínio e geometria:
Em relação a geometria ultilizamos 200 pontos para um bom detalhamento,em um perfil com 1 metro de corda.Precisamos ter um dominio de tal forma que não a vizinhança e os efeitos de borda não tenha muita influência na nossa simulação.Dessa forma ultilizaremos um domínio que seja 20 vezes o tamanho da corda na vertical, e 10 vezes o tamanho da corda na horizontal.

![y+](https://user-images.githubusercontent.com/70406366/96887655-2decb880-145b-11eb-9b05-8e8b6d971e6d.gif)

## Avaliação da malha 

O tipo de malha usada é do tipo não estruturada composta de elementos quadriláteros,o uso da malha não estruturada faz com que o código a ser programado seja mais complexo. Também impõe que se tenha que acessar a matriz de conectividade várias vezes, aumentando o número de operações na máquina em relação à malha estruturada.Com Volumes finitos.

Avaliando a malha de perto (nas bordas do aerofólio ) o nosso Y+ tem um valor de  aproximadamente
![y+](https://user-images.githubusercontent.com/70406366/96887655-2decb880-145b-11eb-9b05-8e8b6d971e6d.gif)
![malha perto do aerofolio](https://user-images.githubusercontent.com/70406366/96934086-0405b700-1498-11eb-808e-e8f6fc0845f1.PNG)
![image](https://user-images.githubusercontent.com/70406366/96936893-4e3d6700-149d-11eb-9460-4601acf3ab5f.png)

Dessa maneira concluimos que nossa malha está adequada para prosseguirmos na simulação.

## Inputs
![setups](https://user-images.githubusercontent.com/70406366/96935217-02d58980-149a-11eb-8a48-e1ba31d8a1d2.jpg)

## Considerações
O interesse do trabalho é a obtenção dos coeficientes de ataque e de sustentação para o ângulo de ataque de 12 graus.Dessa maneira assumiremos algumas considerações visando um bom requisito de solução.Tais como :
* O escoamento em 2D;
* Ocorre em regime permanete ;
* O escoamento é turbulento (ultilizamos o modelo de Spalart-Allmaras baseado em deformação/vorticidade);
* Ultilizaremos a inicialização hibrida com 5000 interações .

## capacidade computacional

![image](https://user-images.githubusercontent.com/70406366/96936153-ed615f00-149b-11eb-9535-44f8c48843ff.png)


# Processamento 
## TESTE 01 : Validação para o ângulo de ataque de 0 graus.

### Para o cd obtemos :
![CD-grafico-1_angulo-0](https://user-images.githubusercontent.com/70406366/96936763-0ddde900-149d-11eb-8b8e-798a63cd93b4.png) 


Podemos observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cd.

### Para o cl obtemos :
![CL-grafico-1_angulo-0](https://user-images.githubusercontent.com/70406366/96936764-0f0f1600-149d-11eb-99e3-b9d0045ee290.png)
Podemos observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cl.

### Em relação aos residuais obtemos :
![Residuais_grafico-1_angulo-0_](https://user-images.githubusercontent.com/70406366/96936765-0f0f1600-149d-11eb-8c59-7857c2a815cf.png)
Podemos observar um resultado satisfatório pois vemos o valor tentendo a zero.

### Analisando os resultados de cd e cl :
![image](https://user-images.githubusercontent.com/70406366/96937140-dfacd900-149d-11eb-8774-e524019273f1.png)

No início do projeto estipulamos um erro aceitável de até 5%
**para isso vamos primeiramente comparar os nossos valores obtidos para o ângulo de ataque de 0 graus com os resultados que podemos obter acessando: https://turbmodels.larc.nasa.gov/naca0012_val.html.

![naca tabela](https://user-images.githubusercontent.com/70406366/96937702-26e79980-149f-11eb-9f62-76edfe39d707.PNG)

Sendo a fórmula do erro :

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

Substituindo os valores

![image](https://user-images.githubusercontent.com/70406366/96937563-c8bab680-149e-11eb-95e4-00db29895dcb.png)

Enquanto isso para cl segundo o site https://turbmodels.larc.nasa.gov/naca0012_val.html possue valor de aproximadamente zero enquanto na nossa simulação optemos um valor muito pequeno sendo próximo de zero (cl = 1.470869e-06)

O erro obtido foi menor que o esperado validando assim o método.Assim o histórico de convergência do cálculo está adequado

### Tempo de resposta 
 Nessa simulação ultilizamos como parametros 5000 interações ,um reporting interval de 10 tempos e um profile update de 10 intervalos.
 Resultando por volta de 10 minutos o tempo de processamento.

# Análise dos gráficos de contorno

### Pressão

![image](https://user-images.githubusercontent.com/70406366/97062101-c96f4d80-156f-11eb-945d-b0ac3c6c4f43.png)


Podemos observar que o ponto de maior pressão se encontra no bordo de ataque ,enquanto no intradoso e extradoso posuem gradientes de pressão similares.

### velocidade

![image](https://user-images.githubusercontent.com/70406366/97062139-f4f23800-156f-11eb-8097-b5f48f22f366.png)


Nota-se que os pontos de maior velocidade se encontram no intradoso e no extradoso do perfil.

### Wall plus *vs* position

![image](https://user-images.githubusercontent.com/70406366/97062203-371b7980-1570-11eb-911e-497d41e36a2a.png)


# TESTE 2 : Análise para o ângulo de ataque de 12 graus

Precisamos dos valores do seno e cosseno para o ataque de 12 graus.Depois, mudamos os Parâmetros de entrada nas condições de borda.Muldamos o repositório de definições tanto do Drag quanto do lift.Lembrando que no valor de X do lift colocamos o - sin(12), pois lift e drag são sempre relativos a movimentação do fluido. Sendo lift perpendicular ao drag enquanto o drag está na direção do movimento do fluido.

### Avaliando os valores obtidos

A pertir dessa simulação obtemos para os valores residuais:

![image](https://user-images.githubusercontent.com/70406366/97064648-da26c000-157d-11eb-8934-7542d0799ec4.png)

Podemos observar um resultado satisfatório pois vemos os valores dos residuais tentendo a valores próximos de zero.


Para os valores de cl:

![image](https://user-images.githubusercontent.com/70406366/97064680-13f7c680-157e-11eb-87de-84fe9d804d92.png)

Podemos observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cl.

Para os valores de cd:

![image](https://user-images.githubusercontent.com/70406366/97064688-2bcf4a80-157e-11eb-8920-ae0258cff523.png)

Podemos observar um resultado satisfatório pois vemos o valor convergindo para um resultado mais preciso de cd.

### Comparando os valores e calculando o erro:

![image](https://user-images.githubusercontent.com/70406366/97064634-b6637a00-157d-11eb-98cd-6c72a05e6022.png)

Ultilizando como referência os valores tabelados no site https://turbmodels.larc.nasa.gov/NACA0012_validation/CLCD_Ladson_expdata.dat .Obtemos :

![image](https://user-images.githubusercontent.com/70406366/97063444-2ec63d00-1576-11eb-8104-8f1a56428b7a.png) 

Dessa maneira o erro do cl será de :

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

![image](https://user-images.githubusercontent.com/70406366/97064894-f3c90700-157f-11eb-9f95-6b013a4ee0e4.png)

enquanto o do cd:

![formula_erro](https://user-images.githubusercontent.com/70406366/96937435-7b3e4980-149e-11eb-8c48-30de3e6a799f.gif)

![image](https://user-images.githubusercontent.com/70406366/97065041-f37d3b80-1580-11eb-81bd-98b3dc18d169.png)

# Gráficos das condições de contorno

### Pressão

![image](https://user-images.githubusercontent.com/70406366/97065217-8074c480-1582-11eb-8016-af6b422333f7.png)

Podemos perceber que com o aumento do ângulo de ataque houve,como esperado,uma mudança significativa entre as diferenças de pressão no intradorso quanto no extradorso.Vemos que a pressão na parte inferior do perfil é maior que na parte superior.

### Velocidade

![image](https://user-images.githubusercontent.com/70406366/97065230-92566780-1582-11eb-8eb3-1d98990b12f5.png)

Nota-se com o aumento do ângulo de ataque as velocidades ao logo do perfil não estão mais contantes quanto guando estava posicionada em 0 graus.

### Turbulence viscosity ratio

![image](https://user-images.githubusercontent.com/70406366/97065389-540d7800-1583-11eb-9c57-7021ed467847.png)

### Tubulence Wall pluss

![image](https://user-images.githubusercontent.com/70406366/97065452-bcf4f000-1583-11eb-9fa5-abc870404094.png)


