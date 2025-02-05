# Temporizadores-Semaforo-Periodico-e-One-Shot

Este repositório reúne duas implementações utilizando o Pico SDK para temporização, conforme a atividade proposta:

1. **Temporizador Periódico – Semáforo:**  
   Utiliza a função `add_repeating_timer_ms()` para implementar um semáforo que alterna os sinais dos LEDs (vermelho, amarelo e verde) a cada 3 segundos.  
   - **Ciclo:** Inicia com o LED vermelho, passa para o amarelo e depois para o verde, repetindo o ciclo.
   - **Feedback Serial:** Mensagens são impressas a cada 1 segundo, informando o estado do semáforo.
   - **Experimento:** Utilização do LED RGB (GPIOs 11, 12 e 13) conforme a configuração da simulação.

2. **Temporizador One Shot – Disparo Único:**  
   Utiliza a função `add_alarm_in_ms()` para acionar uma sequência de LEDs a partir do pressionamento de um botão (pushbutton, conectado ao GPIO 5).  
   - **Sequência:** Ao pressionar o botão, os 3 LEDs são acesos; em seguida, com intervalos de 3 segundos, eles são desligados progressivamente (por exemplo, desligando primeiro o LED azul, depois o vermelho e, por fim, o verde).
   - **Controle de Ação:** A sequência não pode ser reiniciada enquanto estiver em andamento (variável de controle `is_running`).
   - **Debounce:** Implementado um atraso de 50 ms para evitar múltiplos acionamentos.
   - **Feedback Serial:** Mensagens com ícones (ex.: "🔵", "🔴", "🟢") indicam os estados dos LEDs.

## Componentes Utilizados

- **Microcontrolador:** Raspberry Pi Pico W
- **LEDs:**  
  - Semáforo: LEDs vermelho, amarelo e verde.  
  - One Shot: LEDs representados via LED RGB (conectados aos GPIOs 11, 12 e 13).
- **Resistores:** 3 resistores de 330 Ω.
- **Botão:** Pushbutton (para a função One Shot, conectado ao GPIO 5 ou ao Botão A, conforme simulação).
- **Simulador:** Wokwi integrado ao VS Code.
- **Ferramenta Educacional:** BitDogLab (para experimentos com o LED RGB e o botão).

## Estrutura do Projeto

Temporizadores-Semaforo-Periodico-e-One-Shot/
├── temporizador_periodico.c         # Código do semáforo periódico
├── temporizador_oneshot.c           # Código do temporizador One Shot (disparo único)
├── diagram_periodico.json           # Diagrama do semáforo no Wokwi
├── diagram_oneshot.json             # Diagrama do One Shot no Wokwi
├── CMakeLists.txt                   # Arquivo de configuração CMake
└── README.md                        # Este arquivo

Instruções de Uso
1. Clonando o Repositório
Abra o terminal e execute:

bash
Copiar
git clone https://github.com/ElissonNadson/Temporizadores-Semaforo-Periodico-e-One-Shot.git
cd Temporizadores-Semaforo-Periodico-e-One-Shot
2. Abrir no VS Code
Abra o projeto no VS Code e certifique-se de que a integração com o simulador Wokwi esteja funcionando corretamente.

3. Compilar e Simular
Semáforo Periódico:

Compile o código presente em temporizador_periodico.c.
Inicie a simulação no Wokwi.
Verifique o ciclo dos LEDs (vermelho → amarelo → verde) e acompanhe as mensagens na porta serial, que são atualizadas a cada segundo.
Temporizador One Shot:

Compile o código presente em temporizador_oneshot.c.
Inicie a simulação.
Pressione o pushbutton (simulado) para iniciar a sequência.
Os LEDs serão acesos e, em intervalos de 3 segundos, serão desligados progressivamente, conforme os prints com ícones exibidos no terminal.
Requisitos e Ambiente
Ambiente de desenvolvimento: VS Code com integração ao Wokwi.
Pico SDK configurado corretamente.
CMake para a compilação.
Repositório versionado no GitHub.
