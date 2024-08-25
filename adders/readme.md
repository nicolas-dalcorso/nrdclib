# Somadores
*Somadores* são circuitos combinacionais que realizam a soma de dois números. São parte intrínseca de qualquer ULA (Unidade Lógica e Aritmética), mas também são usados em outras componentes de máquinas de estados ou outros circuitos combinacionais.

## $\S 1$ Meio-Somador de 1 *bit* (*Half Adder*)
Dados dois *bits* $A$ e $B$, retorna a soma $S$ e o *carry* $C_{out}$ (*overflow* da operação, se houver). São definidos pelas funções booleanas
$$S = A \oplus B ~~~~~~ C = A \cdot B$$

![[Pasted image 20240824194538.png]]
`half_adder_1b`: meio-somador de 1 *bit*

|Inputs|   |Outputs|   |
|---|---|---|---|
|**A**|**B**|**C**out|**S**|
|0|0|0|0|
|0|1|0|1|
|1|0|0|1|
|1|1|1|0|

## $\S 2$ Somador de 1 *bit* (*Full Adder*)

![[Pasted image 20240824201758.png]]
`full_adder_1b`: somador completo de 1 *bit*

![{\displaystyle S=A\oplus B\oplus C_{in}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/990290db40d42d06d3a1e308db603e962455e729)
![{\displaystyle C_{out}=(A\cdot B)+(C_{in}\cdot (A\oplus B))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9e5fc9a394d89a7b7c78a9fe64105abb9fc2a580)

| Inputs |       |         | Outputs  |       |
| ------ | ----- | ------- | -------- | ----- |
| **A**  | **B** | **C**in | **C**out | **S** |
| 0      | 0     | 0       | 0        | 0     |
| 0      | 0     | 1       | 0        | 1     |
| 0      | 1     | 0       | 0        | 1     |
| 0      | 1     | 1       | 1        | 0     |
| 1      | 0     | 0       | 0        | 1     |
| 1      | 0     | 1       | 1        | 0     |
| 1      | 1     | 0       | 1        | 0     |
| 1      | 1     | 1       | 1        | 1     |
Também podemos construir um *full-adder* a partir de dois *half-adders*, como era de se esperar:
![[Pasted image 20240824202401.png]]


## $\S 3$ *Ripple-Carry Adder*: somador de $n$ bits
Com um *Ripple-Carry Adder*, podemos somar $n$ bits:
- O primeiro somador é um *half-adder*, sendo também possível utilizar um *full-adder* cuja entrada `Cin` seja setada para 0.
- Os demais $n-2$ somadores serão *full-adders*. Para todos eles, sua saída `Cout` será a entrada `Cin` do próximo somador. É desta forma que fazemos a *propagação* do carry.
- As entradas são dois vetores de $n$ bits, a saída será um vetor de $n$ bits e o $C_{out}$

![[Pasted image 20240824203849.png]]
`rippe_carry_adder_8b`: um somador de 8 *bits*


