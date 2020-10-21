# Jonas_Santos_170050653


O objetivo do relatório é realizar a aplicação de instrumentos básicos de gestão de projetos para a elaboração, planejamento, preparação e execução de um projeto de Dinâmica dos Fluidos Computacional.

**Problema 3:** No projeto de uma asa de uma aeronave, deseja-se saber o melhor aerofólio para este perfil. No entanto, deseja-se um valor de coeficiente de sustentação em torno de 0,8 para um ângulo de ataque de 12 graus. Para avaliação do aerofólio, escolheu-se o perfil NACA 0012. O projeto de CFD deve:

- Determinar, com a simulação, um valor de coeficientes de arrasto e sustentação para o aerofólio NACA 0012 para o ângulo de ataque de 12 graus.
- Determinar se está ocorrendo o fenômeno de *stall* neste ângulo de ataque.
- Usando a simulação apresentada, realizar um estudo paramétrico da modelagem da turbulência para determinar cenários de desempenho aerodinâmico do perfil

### 1. Modelagem: 

### Objetivo:
**O principal objetivo do projeto fazer uma simulação computacional com o aerofólio da NACA0012**  
### Requisitos:
**Os requisitos da solução são : um conhecimento prévio no estudo de aeronaves ou aeromodelos,manejo do programa Ansys,valores de arrasto e de sustentação.**
### Finalidade:
**com a a finalidade de se determinar um valor de coeficiente de arrasto e sustentação para o aerofólio NACA 0012 para o ângulo de ataque de 12 graus.Além de determinar se está ocorrendo o fenômeno de *stall* neste ângulo de ataque.**
### Hipóteses 
**Usaresmo como hipóteses que o escoamento seja 2D ,turbulento e isotérmico.**
### Precisão
**Teremos uma precisão mínima de arrasto e sutentação de 5%.**
### Prazos: 
**O prazo de entrega para este trabalho será para o dia 04 de dezembro de 2020.Dessa forma segmentaremos as principais partes sendo :

**Modelagem: 10 dias**

**Pré-processamento: 20 dias**

**Processamento e pós processamento 45 dias**

### Opções além do cfd:
**Podemos ultilizar além do CFD uma simulação em um tunel de vento,cálculos númericos e tabelas no Exel. **


### Geometria 



Estamos ultilizando um perfil NACA 0012 com o tamanho da corda de 1000 milimetros,e com 200 pontos para traçarmos o perfil.Estabelecemos um domíno onde a parede horizontal esta a 10 vezes o tamanho da corda e a horizontal 20 vezes o tamanho da corda ,para avaliarmos durante a simulação  a influência dos efeitos de parede no nosso projeto.**
<p align="center">
       ![numero de pontos](https://user-images.githubusercontent.com/70406366/95993724-d5d40780-0e05-11eb-9a12-c1b9fbad3d23.PNG) 
       <p align="center">
              Fig 1: Números de pontos
<p align="center">
       ![geometria](https://user-images.githubusercontent.com/70406366/96736287-d71bac00-1392-11eb-9b26-1cd477ba4365.png)
              <p align="center">
                     Fig 2: Geometria da malha 
### Modelagem do problema 

- Desenhos CAD mostrando a geometria do problema.
- Desenho esquemático da modelagem do problema.

### 2.	Pré-Processamento:

A segunda etapa deverá conter as respostas para as seguintes perguntas:

- Quanto detalhado o domínio de cálculo precisa ser?
- A geometria está adequada?
- Que tipo de malha e método usar? Estruturada ou não-estruturada? Volumes Finitos ou Elementos Finitos?
- Quais são as informações de entrada (Input) do problema?
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

