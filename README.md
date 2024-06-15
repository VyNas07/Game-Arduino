# Game-Arduino

Português -> Este código implementa um jogo semelhante ao clássico "Dinossauro Corredor" do Google Chrome, adaptado para ser executado em um display LCD 16x2 com o auxílio de um Arduino. O jogo consiste em controlar um dinossauro que corre automaticamente, saltando sobre obstáculos no terreno.

English -> This code implements a game similar to Google Chrome's classic "Running Dinosaur", adapted to run on a 16x2 LCD display with the help of an Arduino. The game consists of controlling a dinosaur that runs automatically, jumping over obstacles in the terrain.


### Integrantes
- Vyktor Nascimento
- Elias Mascarenhas
- João Miguel Freitas
- Thaíssa Fernandes
- Luan Martins
- Priscila Maciel
- Mariana Ferreira

### Orientadores
- Rafael Batista Duarte
- Henrique Braga Foresti

### Instituição
- C.E.S.A.R. School

### Componentes
- 1 x Arduino UNO
- 1 x LCD screen (16 x 2 character)
- 1 x Electronics breadboard
- 1 x I2C
- 1 x Pushbutton switch
- Solid-core hookup wire
- 1 x USB cable
  
### Estrutura do Código

O código é dividido em várias partes para organizar a lógica e os elementos do jogo:

1. *Bibliotecas e Constantes:*
   - LiquidCrystal_I2C.h: Permite a comunicação com o display LCD através do protocolo I2C.
   - Wire.h: Necessária para a comunicação I2C.
   - Constantes: Definem os pinos utilizados (botão, autoplay), os sprites (desenhos) do personagem e do terreno, e as diferentes posições do dinossauro durante o jogo.

2. *Função initializeGraphics():*
   - Cria os caracteres personalizados (sprites) que serão exibidos no display LCD.
   - Inicializa os arrays terrainUpper e terrainLower, que armazenam o estado do terreno em cada linha do display.

3. *Função advanceTerrain():*
   - Desloca o terreno para a esquerda, simulando o movimento do jogo.
   - Atualiza os arrays terrainUpper e terrainLower com base no tipo de terreno que está entrando na tela.

4. *Função drawCAR():*
   - Desenha o dinossauro no display LCD, com base na posição atual (CARPos).
   - Verifica se houve colisão com obstáculos e retorna true se houver.
   - Atualiza o placar (distância percorrida).

5. *Interrupção buttonPush():*
   - É acionada quando o botão é pressionado, definindo a variável buttonPushed para true.

6. *Função setup():*
   - Configura os pinos como entrada (botão) e saída (autoplay).
   - Ativa o resistor de pull-up interno do pino do botão.
   - Configura a interrupção para detectar o pressionamento do botão.
   - Inicializa o display LCD e os gráficos.

7. *Função loop():*
   - Controla a lógica principal do jogo:
     - Se o jogo não estiver em execução, exibe a tela inicial e espera o botão ser pressionado para iniciar.
     - Se o jogo estiver em execução:
       - Desloca o terreno.
       - Gera novos obstáculos no terreno.
       - Lê o estado do botão para realizar o salto.
       - Desenha o dinossauro e o terreno.
       - Verifica se houve colisão e encerra o jogo, se necessário.
       - Atualiza a posição do dinossauro e o placar.

### Funcionamento do Jogo

1. *Início:* Ao ligar o Arduino, a tela inicial é exibida, convidando o jogador a pressionar o botão para iniciar o jogo.

2. *Execução:*
   - O dinossauro corre automaticamente para a direita.
   - O terreno se desloca para a esquerda, dando a impressão de movimento.
   - Obstáculos são gerados aleatoriamente no terreno.
   - Ao pressionar o botão, o dinossauro salta, evitando os obstáculos.

3. *Fim:* Se o dinossauro colidir com um obstáculo, o jogo termina e a distância percorrida é exibida.

### Considerações Finais

Este código é uma implementação simples do jogo "Dinossauro Corredor" para um display LCD com Arduino. Ele pode ser modificado e aprimorado de diversas formas, como:

- Adicionar diferentes tipos de obstáculos.
- Aumentar a dificuldade do jogo ao longo do tempo.
- Criar animações mais elaboradas para o dinossauro.
- Adicionar efeitos sonoros.
- Implementar um sistema de pontuação mais complexo.

Este código serve como um ponto de partida para projetos mais avançados e pode ser adaptado para outros tipos de jogos ou aplicações.
