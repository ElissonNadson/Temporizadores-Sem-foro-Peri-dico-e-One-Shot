# Temporizadores: Semáforo Periódico e One-Shot

Este repositório contém duas implementações utilizando o **Pico SDK** para temporização, conforme a atividade proposta na disciplina *Clock e Temporizadores*.

## 📌 Descrição das Implementações

### 1️⃣ Temporizador Periódico – Semáforo  
Utiliza a função `add_repeating_timer_ms()` para alternar automaticamente os estados de um semáforo com três LEDs.  

- **Ciclo de Funcionamento:**  
  - LED **vermelho** → LED **amarelo** → LED **verde** (se repete a cada 3 segundos).  
- **Feedback Serial:**  
  - Mensagens são exibidas a cada 1 segundo informando o estado atual do semáforo.  
- **Configuração:**  
  - LEDs conectados aos GPIOs **11, 12 e 13** (LED RGB em simulação).  
- **Ferramenta Educacional:**  
  - Experimento realizado no **BitDogLab**.  
- **Código disponível em:**  
  - 🔗 [Repositório do Temporizador Periódico – Semáforo](https://github.com/ElissonNadson/temporizador-periodico-semaforo)

### 2️⃣ Temporizador One-Shot – Disparo Único  
Utiliza a função `add_alarm_in_ms()` para acionar LEDs após o pressionamento de um botão (pushbutton).  

- **Sequência de Funcionamento:**  
  - O usuário pressiona o botão → os três LEDs acendem.  
  - Após **3 segundos**, um LED apaga.  
  - Após mais **3 segundos**, o segundo LED apaga.  
  - Após mais **3 segundos**, o último LED apaga.  
- **Controle de Acionamento:**  
  - O botão **não pode reiniciar a sequência enquanto os LEDs estiverem apagando** (`is_running`).  
- **Debounce:**  
  - Implementado um atraso de **50 ms** para evitar múltiplos acionamentos indesejados.  
- **Feedback Serial:**  
  - Ícones como 🔵🔴🟢 são exibidos no terminal indicando os estados dos LEDs.  
- **Código disponível em:**  
  - 🔗 [Repositório do Temporizador One-Shot](https://github.com/ElissonNadson/temporizador-oneshot)

---

## 🛠️ Componentes Utilizados  

- **Microcontrolador:** Raspberry Pi Pico W  
- **LEDs:**  
  - **Semáforo:** LEDs vermelho, amarelo e verde.  
  - **One Shot:** LEDs azul, vermelho e verde.  
- **Resistores:** 3 resistores de **330 Ω**.  
- **Botão:** Pushbutton (GPIO **5** ou **Botão A** no simulador).  
- **Simulador:** Wokwi integrado ao **VS Code**.  
- **Ferramenta Educacional:** BitDogLab.

---

## 📂 Estrutura do Projeto



---

## 🚀 Instruções de Uso

### 1️⃣ Clonando o Repositório  
No terminal, execute:

git clone https://github.com/ElissonNadson/Temporizadores-Semaforo-Periodico-e-One-Shot.git
cd Temporizadores-Semaforo-Periodico-e-One-Shot
2️⃣ Abrir no VS Code
Abra o projeto no VS Code e certifique-se de que o Wokwi está configurado corretamente.

3️⃣ Compilar e Simular

📌 Semáforo Periódico
Compile o código temporizador_periodico.c.
Inicie a simulação no Wokwi.
Observe a mudança dos LEDs e as mensagens na porta serial.

📌 Temporizador One-Shot
Compile o código temporizador_oneshot.c.
Inicie a simulação no Wokwi.
Pressione o botão para ativar a sequência de LEDs.


📋 Requisitos e Ambiente
Ambiente: VS Code + Wokwi
SDK: Pico SDK corretamente configurado
Compilação: Utilizando CMake
Versionamento: GitHub

📌 Observações

O botão não pode ser acionado novamente até que todos os LEDs estejam apagados.
O debounce foi implementado para evitar múltiplos acionamentos.
Experimentos foram feitos com o LED RGB e o botão A no BitDogLab.

