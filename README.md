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
O sistema está configurado com FreeRTOS e tasks diferentes para cada pino de sáida.
Inicialmente o pino PA0 foi configurado com interrupsão e então alterado para uma *TASK* do FreeRTOS. Precionando o botão, tanto da placa de desenvolvimento quanto o do *protoboard*, alteras-se o estafo da *flag* BLUELED, alterando o estado do pino PC13 de *High* para  *Low*, o que fará com que acenda ou apague o LED azul da placa, e consequentemente ligue ou desligue o canal 1 do módulo de relé.

PA1 configurado como entrada analógica recebe o sinal da sonda DS18B20 pelo ADC, e atravéz de lógica habilita a saída PC15 (canal 3 do relé).

PA6 e PA7 foram configurados como entrada analógica e devem receber o sinal vindo de um sensor LDR para o PA6 e se um módulo LDR para o PA7. Ambos com ADC no IN6 e IN7, e através de lógica, habilitam as saídas PCB1 (canal 4 do relé) e PC14 (canal 2 do relé).

*************************************************************************************************
* INTERTRAVAMENTO
*************************************************************************************************
PA0 (Key)      --> PC13 (Relé CH1)

PA1 (DS18B20)  --> PC15 (Relé CH3)

PA2  (Key2)    -->

PA5 (DHT11)    -->

PA6 (LDR2)     --> PB1 (Relé CH4)

PA7 (LDR1)     --> PC14 (Relé CH2)
<<<<<<< HEAD
=======

*************************************************************************************************
* DADHBOAR / MQTT Client
*************************************************************************************************
![image](https://github.com/user-attachments/assets/9a389fac-8d79-4e97-a5c8-6e9c2d75d135)
![Imagem do WhatsApp de 2025-02-21 à(s) 15 37 16_ac2d3330](https://github.com/user-attachments/assets/8792de7e-fd52-4b26-8a54-49f52d8f6089)

>>>>>>> branch-novo
<<<<<<< HEAD
=======

>>>>>>> branch-novo
