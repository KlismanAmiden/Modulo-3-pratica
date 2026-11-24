# Módulo 03 — Sistemas de Numeração — Prática

> **Objetivo da prática:** treinar conversões entre decimal, binário e hexadecimal até conseguir justificar cada passo — não só chegar na resposta certa por mecânica.

---

## 1. Decimal → binário

**Enunciado:** Converta pelo método das moedas, mostrando cada passo: `13`, `41`, `100`, `255`.

### 1.1 — `13`

Maior moeda que cabe em `13` → `8` (sobra `5`).

Maior moeda que cabe em `5` → `4` (sobra `1`).

Maior moeda que cabe em `1` → `1` (sobra `0`).

Moedas usadas: `8, 4, 1`.

```text
8  4  2  1
1  1  0  1
```

**Resultado:** `13 = 1101₂`

### 1.2 — `41`

Maior moeda que cabe em `41` → `32` (sobra `9`).

Maior moeda que cabe em `9` → `8` (sobra `1`).

Maior moeda que cabe em `1` → `1` (sobra `0`).

Moedas usadas: `32, 8, 1`.

```text
32  16  8  4  2  1
 1   0  1  0  0  1
```

**Resultado:** `41 = 101001₂`

### 1.3 — `100`

Maior moeda que cabe em `100` → `64` (sobra `36`).

Maior moeda que cabe em `36` → `32` (sobra `4`).

Maior moeda que cabe em `4` → `4` (sobra `0`).

Moedas usadas: `64, 32, 4`.

```text
64  32  16  8  4  2  1
 1   1   0   0  1  0  0
```

**Resultado:** `100 = 1100100₂`

### 1.4 — `255`

Maior moeda que cabe em `255` → `128` (sobra `127`).

Depois: `64` (sobra `63`).

Depois: `32` (sobra `31`).

Depois: `16` (sobra `15`).

Depois: `8` (sobra `7`).

Depois: `4` (sobra `3`).

Depois: `2` (sobra `1`).

Depois: `1` (sobra `0`).

Todas as moedas de `128` até `1` foram usadas:

```text
128  64  32  16  8  4  2  1
  1   1   1   1  1  1  1  1
```

**Resultado:** `255 = 11111111₂`

---

## 2. Binário → decimal

**Enunciado:** Converta somando o valor de cada casa (posição), mostrando a soma: `1010`, `101010`, `11111111`.

### 2.1 — `1010`

```text
1 × 8 + 0 × 4 + 1 × 2 + 0 × 1
= 8 + 0 + 2 + 0
= 10
```

**Resultado:** `1010₂ = 10₁₀`

### 2.2 — `101010`

```text
1 × 32 + 0 × 16 + 1 × 8 + 0 × 4 + 1 × 2 + 0 × 1
= 32 + 0 + 8 + 0 + 2 + 0
= 42
```

**Resultado:** `101010₂ = 42₁₀`

### 2.3 — `11111111`

```text
1 × 128 + 1 × 64 + 1 × 32 + 1 × 16
+ 1 × 8 + 1 × 4 + 1 × 2 + 1 × 1

= 128 + 64 + 32 + 16 + 8 + 4 + 2 + 1
= 255
```

**Resultado:** `11111111₂ = 255₁₀`

---

## 3. Binário ↔ hexadecimal

### 3.1 — `11010110` para hexadecimal

**Enunciado:** Converta `11010110` para hexadecimal, mostrando o agrupamento em blocos de 4 bits.

Separando em blocos de 4 bits:

```text
1101 0110
```

Cada bloco corresponde a um dígito hexadecimal:

```text
1101 = D
0110 = 6
```

**Resultado:**

```text
11010110₂ = 0xD6
```

Conferência em decimal:

```text
11010110
= 128 + 64 + 16 + 4 + 2
= 214
```

Conferência em hexadecimal:

```text
D6 = 0xD6
```


### 3.2 — `0x3F` para binário e depois para decimal

Cada dígito hexadecimal representa 4 bits:

```text
3 = 0011
F = 1111
```

Então:

```text
0x3F = 0011 1111₂
```

Convertendo para decimal:

```text
0011 1111
= 32 + 16 + 8 + 4 + 2 + 1
= 63
```

**Resultado:**

```text
0x3F = 00111111₂ = 63₁₀
```

---

## 4. Soma binária

**Enunciado:** Some, mostrando coluna por coluna e o vai-um explicitamente.

### 4.1 — `0110 + 0011`

Começando pela direita:

```text
  0110
+ 0011
------
  1001
```

Colunas:

```text
0 + 1 = 1
1 + 1 = 10₂ → escreve 0 e vai-um 1
1 + 0 + 1 = 10₂ → escreve 0 e vai-um 1
0 + 0 + 1 = 1
```

Portanto:

```text
0110 + 0011 = 1001
```

### 4.2 — `1011 + 0111`

```text
  1011
+ 0111
------
 10010
```

Da direita para a esquerda:

```text
1 + 1 = 10₂ → escreve 0, vai-um 1

1 + 1 + 1 = 11₂ → escreve 1, vai-um 1

0 + 1 + 1 = 10₂ → escreve 0, vai-um 1

1 + 0 + 1 = 10₂ → escreve 0, vai-um 1

vai-um final = 1
```

Portanto:

```text
1011 + 0111 = 10010
```

---

## 5. Quantos bits são necessários?

**Enunciado:** Quantos bits, no mínimo, são necessários para representar todos os números inteiros de `0` até `1000`? Explique quantos valores diferentes `n` bits conseguem representar, e a partir de qual `n` esse total passa de 1000.

Com `n` bits, cada bit pode ser `0` ou `1`, então existem:

```text
2ⁿ
```

combinações diferentes.

De `0` até `1000` existem:

```text
1000 - 0 + 1 = 1001 valores
```

Testando 9 bits:

```text
2⁹ = 512
```

`512` valores não são suficientes para representar `1001` valores.

Testando 10 bits:

```text
2¹⁰ = 1024
```

`1024` valores são suficientes para representar os `1001` valores de `0` até `1000`.

**Resposta:** são necessários, no mínimo, **10 bits**.

---

## 6. Conferindo com o terminal

**Enunciado:** Depois de resolver os exercícios 1 a 3 na mão, confira cada resposta rodando os comandos de conversão. Cole a saída do terminal ao lado de cada resposta manual.

### Decimal → binário/hexadecimal

#### `13`

```text
C:\Users\Wkkli>py -c "print(bin(13), hex(13))"
0b1101 0xd
```

Manual:

```text
13 = 1101₂
```

Terminal:

```text
0b1101 0xd
```

Bateu.

#### `41`

```text
C:\Users\Wkkli>py -c "print(bin(41), hex(41))"
0b101001 0x29
```

Manual:

```text
41 = 101001₂
```

Terminal:

```text
0b101001 0x29
```

Bateu.

#### `100`

```text
C:\Users\Wkkli>py -c "print(bin(100), hex(100))"
0b1100100 0x64
```

Manual:

```text
100 = 1100100₂
```

Terminal:

```text
0b1100100 0x64
```

Bateu.

#### `255`

```text
C:\Users\Wkkli>py -c "print(bin(255), hex(255))"
0b11111111 0xff
```

Manual:

```text
255 = 11111111₂
```

Terminal:

```text
0b11111111 0xff
```

Bateu.

### Binário → decimal

#### `1010`

```text
C:\Users\Wkkli>py -c "print(int('1010', 2))"
10
```

Manual:

```text
1010 = 10
```

Bateu.

#### `101010`

```text
C:\Users\Wkkli>py -c "print(int('101010', 2))"
42
```

Manual:

```text
101010 = 42
```

Bateu.

#### `11111111`

```text
C:\Users\Wkkli>py -c "print(int('11111111', 2))"
255
```

Manual:

```text
11111111 = 255
```

Bateu.

### Hexadecimal → decimal

#### `3F`

```text
C:\Users\Wkkli>py -c "print(int('3F', 16))"
63
```

Manual:

```text
0x3F = 63
```

Bateu.

### `11010110` → hexadecimal

A resposta manual foi:

```text
11010110 = 0xD6
```

Conferência real no terminal:

```text
C:\Users\Wkkli>py -c "print(int('11010110', 2), hex(int('11010110', 2)))"
214 0xd6
```

A resposta manual bateu com o terminal.

---

## 7. Decimal ↔ octal, e a "quarta base"

### 7.1 — `41` para octal

**Enunciado:** Converta `41` para octal usando divisões sucessivas por 8.

```text
41 ÷ 8 = 5, resto 1
5 ÷ 8 = 0, resto 5
```

Lendo os restos de baixo para cima:

```text
51
```

**Resultado:**

```text
41₁₀ = 0o51₈
```

### 7.2 — `0o61` para decimal

**Enunciado:** Converta `0o61` de volta para decimal, somando o valor de posição de cada dígito (potências de 8).

```text
0o61
```

O `6` está na posição dos `8¹` e o `1` está na posição dos `8⁰`:

```text
6 × 8¹ + 1 × 8⁰
= 6 × 8 + 1 × 1
= 48 + 1
= 49
```

**Resultado:**

```text
0o61 = 49₁₀
```

### 7.3 — `101001` binário para octal

**Enunciado:** Converta `101001` diretamente para octal, agrupando de 3 em 3 bits a partir da direita.

Agrupando:

```text
101 001
```

Convertendo cada grupo:

```text
101₂ = 5₈
001₂ = 1₈
```

Logo:

```text
101001₂ = 51₈
```

O agrupamento é de 3 em 3 porque:

```text
2³ = 8
```

Ou seja, cada grupo de 3 bits pode representar exatamente um dígito octal.

No hexadecimal, o agrupamento é de 4 em 4 porque:

```text
2⁴ = 16
```

**Resultado:** `101001₂ = 51₈`

### 7.4 — Conferência no terminal

```text
C:\Users\Wkkli>py -c "print(oct(41), int('61', 8))"
0o51 49
```

Os resultados conferem com os cálculos manuais.

---

## 8. Subtração binária

**Enunciado:** A subtração binária segue a mesma lógica da subtração decimal com "empréstimo" (borrow). Quando falta valor numa coluna, você empresta 1 da coluna seguinte, que vale o dobro.

### 8.1 — `1011 - 0011`

```text
  1011
- 0011
------
  1000
```

Da direita para a esquerda:

```text
1 - 1 = 0

1 - 1 = 0

0 - 0 = 0

1 - 0 = 1
```

Não foi necessário empréstimo neste caso.

**Resultado:**

```text
1011 - 0011 = 1000
```

### 8.2 — `1000 - 0001`

```text
  1000
- 0001
------
  0111
```

Na última coluna:

```text
0 - 1
```

Não é possível, então precisamos pegar `1` emprestado da coluna à esquerda. Como essa coluna também é `0`, o empréstimo passa pelas colunas seguintes até chegar ao `1` mais à esquerda.

O `1` mais à esquerda empresta para a próxima posição:

```text
1000
↓
0 111
```

O empréstimo transforma as posições seguintes em valores que permitem realizar a subtração:

```text
10₂ - 1₂ = 1
```

e as colunas intermediárias ficam com o valor necessário para continuar:

```text
1 - 0 = 1
1 - 0 = 1
0 - 0 = 0
```

Assim:

```text
1000 - 0001 = 0111
```

### 8.3 — `1011 - 0011` usando complemento de 2

Primeiro pegamos `0011`.

Invertemos todos os bits:

```text
0011 → 1100
```

Depois somamos `1`:

```text
1100
+0001
-----
1101
```

Portanto:

```text
complemento de 2 de 0011 = 1101
```

Agora fazemos:

```text
  1011
+ 1101
------
1 1000
```

Como estamos trabalhando com 4 bits, descartamos o vai-um extra:

```text
1000
```

Logo:

```text
1011 - 0011 = 1000
```

Os dois métodos produzem o mesmo resultado.

---

## 9. Complemento de 2 (representando negativos)

**Enunciado:** Complemento de 2 é como um computador representa números negativos usando apenas `0` e `1`. Considerando registradores de 4 bits:

### 9.1 — Complemento de 2 de `0011`

`0011` representa o decimal `3`.

Primeiro fazemos o complemento de 1, invertendo todos os bits:

```text
0011
↓
1100
```

Depois somamos `1`:

```text
  1100
+ 0001
------
  1101
```

Portanto:

```text
complemento de 2 de 0011 = 1101
```

Em um registrador de 4 bits, `1101` representa `-3`.

**Resultado:** `0011 → 1101`, que representa `-3`.

### 9.2 — Interpretando `1101`

**Enunciado:** Dado `1101` em complemento de 2, 4 bits, descubra que número decimal negativo ele representa.

Como o primeiro bit é `1`, o número é negativo.

Invertendo os bits:

```text
1101
↓
0010
```

Somando `1`:

```text
0010
+0001
-----
0011
```

`0011` em decimal é `3`.

Como o número original era negativo:

```text
1101 = -3
```

### 9.3 — Comparando os dois métodos

Subtração direta:

```text
1011 - 0011 = 1000
```

Complemento de 2 de `0011`:

```text
0011 → 1100 → 1101
```

Agora:

```text
  1011
+ 1101
------
1 1000
```

Descartando o vai-um extra:

```text
1000
```

Portanto:

```text
1011 - 0011 = 1000

1011 + complemento_de_2(0011)
= 1011 + 1101
= 1000
```

Os dois métodos dão o mesmo resultado.

### 9.4 — Por que o complemento de 2 evita um circuito separado para subtração?

O complemento de 2 transforma uma **subtração em uma soma**.

Em vez de fazer:

```text
A - B
```

o computador pode fazer:

```text
A + complemento_de_2(B)
```

Assim, ele pode usar o mesmo circuito somador para realizar tanto somas quanto subtrações, sem precisar de um circuito separado para subtrair.

---

## 10. Overflow na prática, com código C++

### 10.1 — Previsão

**Enunciado:** Sem rodar nada ainda, preveja o que acontece se você somar `1` ao valor `255` guardado em uma variável `unsigned char` de 8 bits.

A previsão é que ocorrerá um overflow, porque:

```text
255 + 1 = 256
```

Mas `256` não cabe em 8 bits sem sinal.

Um `unsigned char` de 8 bits consegue representar:

```text
0 até 255
```

Por isso, o valor volta para `0`.

### 10.2 — Código C++ e execução

Código utilizado:

```cpp
#include <iostream>

int main() {
    unsigned char valor = 255;
    valor = valor + 1;
    std::cout << "Resultado: " << static_cast<int>(valor) << "\n";
    return 0;
}
```

Saída real de execução registrada no terminal:

```text
PS C:\Users\Wkkli\Downloads> & C:\Users\Wkkli\Downloads\programa.exe
Resultado: 0
PS C:\Users\Wkkli\Downloads>
```

### 10.3 — Por que `255 + 1` vira `0`?

A previsão estava correta.

Com 8 bits existem:

```text
2⁸ = 256
```

valores possíveis, de `0` até `255`.

O número `255` em binário é:

```text
11111111
```

Ao somar `1`:

```text
  11111111
+ 00000001
----------
1 00000000
```

O resultado precisaria de 9 bits.

Como `unsigned char` possui somente 8 bits, o bit extra é descartado:

```text
1 00000000
↑
bit extra descartado
```

Sobra:

```text
00000000
```

Portanto:

```text
255 + 1 = 0
```

nesse tipo de 8 bits.

---

## 11. ASCII, Unicode e UTF-8

### 11.1 — Código de `'A'`

**Enunciado:** Tente lembrar o código decimal de `'A'` e confira com `py -c "print(ord('A'))"`.

O código decimal de `'A'` é:

```text
65
```

Comando executado:

```text
C:\Users\Wkkli>py -c "print(ord('A'))"
65
```

A resposta manual bateu com o terminal.

### 11.2 — `'a'` e `'0'`

Os códigos são:

```text
'A' = 65
'a' = 97
'0' = 48
```

Conferência no terminal:

```text
C:\Users\Wkkli>py -c "print(ord('A'), ord('a'), ord('0'))"
65 97 48
```

A diferença entre `'A'` e `'a'` é:

```text
97 - 65 = 32
```

A diferença entre o código do caractere `'0'` e o valor inteiro `0` é:

```text
48 - 0 = 48
```

Isso acontece porque `'0'` é um **caractere**, representado pelo código ASCII `48`, enquanto `0` é o valor numérico inteiro zero.

Isso acontece porque `'0'` é um **caractere**, representado pelo código ASCII `48`, enquanto `0` é o valor numérico inteiro zero.

### 11.3 — UTF-8 e o caractere `á`

O comando executado:

```text
C:\Users\Wkkli>py -c "print(len('á'.encode('utf-8')))"
2
```

O resultado foi `2`.

O caractere `á` não faz parte dos 128 caracteres originais do ASCII.

O ASCII original cobre 128 símbolos e usa 7 bits. O UTF-8 mantém esses 128 primeiros símbolos compatíveis com ASCII usando 1 byte, mas utiliza mais bytes para representar caracteres que estão fora desse conjunto, como `á`.

Por isso, o caractere `á` ocupa **2 bytes em UTF-8**, apesar de continuar sendo apenas um caractere.

---

## 12. Aplicação real: endereço IP em binário

**Enunciado:** Um endereço IPv4 como `192.168.1.1` é, por baixo dos panos, 4 números de 8 bits (0–255) cada, separados por pontos.

### 12.1 — `192.168.1.1` para binário

Convertendo cada octeto para 8 bits:

```text
192 = 11000000
168 = 10101000
1   = 00000001
1   = 00000001
```

Juntando os quatro octetos:

```text
11000000 10101000 00000001 00000001
```

Portanto:

```text
192.168.1.1
=
11000000 10101000 00000001 00000001
```

São 4 octetos de 8 bits:

```text
4 × 8 = 32 bits
```

### 12.2 — Binário para endereço IPv4

Dado:

```text
00001010 00000000 00000000 00000001
```

Separando nos quatro octetos:

```text
00001010
00000000
00000000
00000001
```

Convertendo cada um:

```text
00001010 = 8 + 2 = 10
00000000 = 0
00000000 = 0
00000001 = 1
```

Remontando o endereço:

```text
10.0.0.1
```

**Resultado:** `10.0.0.1`
