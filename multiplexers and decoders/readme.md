# Multiplexadores e Decodificadores
## Multiplexadores

### Definição

Um multiplexador (ou MUX) é um dispositivo digital que seleciona uma de várias linhas de entrada e a encaminha para uma única linha de saída. Ele age como um "comutador" que permite que múltiplos sinais compartilhem um único canal de transmissão.

### Descrição

O multiplexador é controlado por um conjunto de linhas de seleção, que determinam qual entrada será transmitida para a saída. Por exemplo, um multiplexador de $4$ entradas ($4:1$) tem duas linhas de seleção, pois $2^2 = 4$. A linha de seleção escolhe uma das entradas, e o sinal correspondente é enviado para a saída.

### Exemplo

Considere um multiplexador $4:1$ com as entradas $I0,I1,I2,I3$​, duas linhas de seleção $S_0$​ e $S_1$​, e uma saída $Y$. Dependendo da combinação das linhas de seleção, a saída YYY será uma das entradas:

- $S_1S_0$ = $00$ → $Y = I_0$​
- $S_1S_0 = 01 → Y = I_1$​
- $S_1S_0 = 10 → Y = I_2$
- $S_1S_0 = 11 → Y = I_3$​

### Decodificadores

#### Definição

Um decodificador é um dispositivo digital que converte uma entrada codificada em um formato legível, ou seja, ele traduz um código de entrada em um código de saída diferente, geralmente em um formato mais "aberto" ou mais facilmente interpretável.

#### Descrição

Um decodificador geralmente possui $n$ linhas de entrada e $2^n$ linhas de saída. Ele pega uma entrada binária de $n$ bits e ativa uma única linha de saída correspondente, mantendo todas as outras saídas desativadas. Isso faz com que o decodificador seja amplamente utilizado em circuitos digitais onde é necessário ativar uma linha específica com base em uma combinação binária.

#### Exemplo

Um exemplo comum é um decodificador 2 para 4, que possui 2 entradas ($A$ e $B$) e 4 saídas ($Y_0, Y_1, Y_2, Y_3$​). As saídas são determinadas pelas entradas da seguinte forma:

- $AB = 00 → Y_0 = 1$, todas as outras saídas = 0
- $AB = 01 → Y_1 = 1$, todas as outras saídas = 0
- $AB = 10 → Y_2 = 1$, todas as outras saídas = 0
- $AB = 11 → Y_3 = 1$, todas as outras saídas = 0