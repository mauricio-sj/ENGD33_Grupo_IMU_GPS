## Descrição

Este projeto implementa o controle de um robô equipado com diversos sensores de navegação, incluindo acelerômetro e giroscópio (MPU6050), magnetômetro (HMC5883L), e o sistema de posicionamento Marvelmind Hedgehog. Utilizando o FreeRTOS, o projeto gerencia múltiplas tarefas, processa dados dos sensores e aplica controle PID para ajustar o posicionamento e a movimentação do robô.

## Funcionalidades

- **Controle PID**: Implementação do controle PID para ajustar as velocidades e o posicionamento do robô com base em dados de sensores.
- **Fusão de Sensores**: Integração de dados de acelerômetros, giroscópios, magnetômetros e sistema de GPS para navegação precisa.
- **Gerenciamento de Tarefas com FreeRTOS**: Uso do FreeRTOS para a execução de tarefas paralelas, como leitura de sensores e processamento de dados.
- **Sistema de Posicionamento Marvelmind Hedgehog**: Leitura e interpretação de dados de posição em tempo real para controlar o robô em ambientes com condições adversas para sinais de GPS.

## Estrutura do Projeto

O projeto está dividido nas seguintes partes principais:

- **Tarefas do FreeRTOS**: As tarefas principais incluem a leitura dos sensores (acelerômetro, giroscópio e magnetômetro), processamento de dados do Hedgehog e cálculo da posição e orientação do robô.
- **Filas e Semáforos**: O projeto utiliza filas para comunicação entre as tarefas e semáforos para sincronização de acesso ao barramento I2C.
- **Controle PID**: Implementação de funções de controle PID para ajustar a velocidade e posição do robô.

## Arquivos Principais

- `main.c`: Contém o loop principal e a inicialização dos periféricos e RTOS.
- `stm32f4xx_it.c`: Tratadores de interrupções.
- `freertos.c`: Configurações do FreeRTOS e criação de tarefas.
- `mpu6050.c` e `hmc5883l.c`: Funções para leitura dos sensores MPU6050 e HMC5883L.
- `hedgehog.c`: Funções para comunicação com o sistema Marvelmind Hedgehog.

## Requisitos

- **Placa STM32**: Desenvolvido para STM32 com suporte ao STM32CubeMX e FreeRTOS.
- **STM32CubeIDE ou STM32CubeMX**: Para configuração e geração do código do projeto.
- **FreeRTOS**: Sistema operacional de tempo real utilizado para gerenciamento das tarefas.

## Como Compilar e Executar

1. **Clone o Repositório:**
   ```bash
   git clone [https://github.com/seu-usuario/RoboNavControl.git](https://github.com/mauricio-sj/ENGD33_Grupo_IMU_GPS/)
