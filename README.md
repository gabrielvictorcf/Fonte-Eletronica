# Fonte-Eletronica
Projeto desenvolvido para a disciplina SSC0180 - Eletrônica para Computação do ICMC-USP, apresentada pelo Prof. Eduardo Valle Simões.

Autores:
-   Gabriel Victor - 18878296
-   Alexandre Brito - 11857323

## Objetivo do projeto
Construir uma fonte que converta a corrente alternada 110V/220V de uma tomada para uma saída váriavel entre 12V-3V com corrente contínua de 100mA.

## Simulação do circuito
Para simular o circuito com seus componentes foi utilizado o falstad e ele se encontra [neste link](http://tinyurl.com/ydbdvrwy).

[![diagrama do circuito no falstad](/imgs/fonte-falstad.png "Simulação no Falstad")](http://tinyurl.com/ydbdvrwy)

## Desenvolvimento da fonte & Justificativa dos componentes
Para alcançar a saída desejada aplicou-se cada componente de acordo com seu papel no fluxograma abaixo:

![fluxograma do desenvolvimento](/imgs/fonte-fluxograma.jpg)

### Transformador
Nesse estágio, utilizando do **Transformador 12V+12V**, nós baixamos a corrente alternada da tomada de 127V/220V para 24V.

### Retificador
Usando 4 **Diodos 1N4004** fazemos uma *Ponte Retificadora*. Com esta, fazemos a corrente alternada variar em apenas 1 ciclo, o que permite maior proveito da entrada para alimentação do circuito.

### Filtro
Com o **Capacitor de 470uF** reduz-se a frequência da variação da entrada, deixando-a estável para o uso sem flutuações muito grandes.

### Regulador
Finalmente, com o **Diodo zener BZX55C** de tensão-zener 13V, nós "cortamos" abaixo da corrente de entrada para alimentar o circuito com a voltagem desejada.

Juntando o zener com o **Transistor NPN BC337** e o **Potenciômetro** se forma o *Regulador*. Associando o Regulador em série a uma resistência de 2.2K, podemos selecionar a voltagem de saída entre 3V-12V já com a corrente contínua.

### Carga
A saída do circuito, no Falstad, está representada pela resistência de 120Ω. Adicionalmente, o circuito também alimenta um LED que serve de referência à voltagem selecionada pelo usuário no potenciômetro.

## Custos dos componentes
|Componente|Especificação|Custo|
|----------|-------------|-----|
|Transformador|110/220V -> 12V+12V / 250mA|[R$ 16,60](https://www.baudaeletronica.com.br/transformador-trafo-12v-12v-250ma-110-220vac.html)|
|Potenciômetro|5kΩ / 0.2W|[R$ 1,09](https://www.baudaeletronica.com.br/potenciometro-linear-de-5k-5000.html)|
|Knob p/ Potênciometro|Botao p/ facilitar manuseio|[R$ 1,01](https://www.baudaeletronica.com.br/knob-para-potenciometro-cinza-com-vermelho.html)|
|Capacitor Eletrolítico|470 μF / 35V|[R$ 0,60](https://www.baudaeletronica.com.br/capacitor-eletrolitico-470uf-35v.html)|
|LED Vermelha Alto-Brilho|2V / 20mA|[R$ 0,24](https://www.baudaeletronica.com.br/led-de-alto-brilho-vermelho.html)|
|Transistor NPN BC337|45V / 500mA (Ic) / hFE 100-600|[R$ 0,17](https://www.baudaeletronica.com.br/transistor-npn-bc337.html)|
|Diodo Zener BZX55C|Vz 13V / 500mW|[R$ 0,09](https://www.baudaeletronica.com.br/diodo-zener-bzx55c-13v-0-5w.html)|
|Resistor 1K6|1K6Ω / 0,25W|[R$ 0,08](https://www.baudaeletronica.com.br/resistor-1k6-5-1-4w.html)|
|Resistor 2K|2KΩ / 0,25W|[R$ 0,08](https://www.baudaeletronica.com.br/resistor-2k-5-1-4w.html)|
|Resistor 2K2|2K2Ω / 0,25W|[R$ 0,08](https://www.baudaeletronica.com.br/resistor-2k2-5-1-4w.html)|
|4x Diodo 1N4004|1A / 400Vr|[R$ 0,07](https://www.baudaeletronica.com.br/diodo-1n4004.html)|

Total = R$ 20,32

Alguns componentes, como o Diodo 1N4004, possuem atributos em excesso. Nesses casos a escolha foi direcionada pelo preço vantajoso do componente.
## Simulação no EAGLE (PCB e Esquemático)
![pcb](/imgs/pcb.jpg)
![eagle](/imgs/eagle.jpg)
