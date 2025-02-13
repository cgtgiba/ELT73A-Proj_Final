# ELT73A-Proj_Final - REQUISITOS
-----------------------------------------------------------------------------------------------
1) Conter pelo menos um dispositivo de entrada (Teclado, botão, sensor...) (10%);
2) Utilizar pelo menos um periférico dedicado (ADC, PWM, DMA, Timer...) (10%);
3) Conter pelo menos um dispositivo saída (CubeMonitor, LCD, Motor, Node-RED...) (10%);
4) Possuir alguma rotina de interrupção (ISR) (10%);
5) Ser feito em bancada, protótipo operacional (40%);
6) Documentação no GitHub (5%);
7) Video de apresentação (15%).
************************************************************************************************
************************************************************************************************
* *Materiais e equipamentos:*
************************************************************************************************
Microcontrolador STM32F411 Black pil
Módulo LDR HW-072
Sensor LDR
push buton
módulo Relé de 4 Canais JQC-3FF-S-Z
sonda de temperatura DS18B20
resistores
jumpers

![image](https://github.com/user-attachments/assets/673a95aa-233d-4a68-bab7-67b3564651d4)

* *Pinos de Entrada:*

- PA0 - Botão (UserKey)
- PA1 - Entrada Analógica para sonda de Temperatura
- PA6 - LDR_2
- PA7 - Módulo LDR
- *PA5 - DHT11*

* *Pinos de Saída:*

- PC13 - Blue LED / Relé CH1
- PC14 - Relé CH2
- PC15 - Relé CH3
- PB1 - Relé CH4

***********************************************************************************************
* FUNCIONAMENTO
***********************************************************************************************
O sistema está configurado com FreeRTOS e tasks diferentes para cada pino de sáida
Inicialmente o pino PA0 foi configurado com interrupsão,enviando sinal para o PC13 que ira energizar o Blue Led da placa juntamente com canal 1 do módulo de relé
PA6 e PA7 recebem o sinal analógico dos LDRs, fazem a conversão no ADC, e através de uma lógica, habilitam as saídas PC14 (canal 2 do relé) e PB1 (canal 4 do relé)
O pino PA1 recebe o o sinal da sonda DS18B20, e atravéz de lógica habilita a saída PC15 (canal 3 do relé)
