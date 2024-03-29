<img src="https://drive.google.com/uc?id=1SOzRTjUt7cuBJpSqoK90fcAiKBrnpUJo" width="400">

**Curso:** Analise e Desenvolvimento de sistemas <br>
**Disciplina:** Raciocínio Lógico e Algoritimos<br>
**Código/Turma:** T160-80 <br>
**Professor:** Ricardo Carubbi <br>
**Data:** 28/03/2024 <br>
**Aluno(a):** Marjorie Castelo dos Santos <br>
**Matrícula:** 2412908 <br>

**1a chamada (Sim/Não):** Não <br>
**2a chamada (Sim/Não):** Sim <br>

# Avaliação Diagnóstica 1



## Lista de questões

### Questão 1 - Troca dos valores de duas variáveis 

Dadas duas variáveis, $a$ e $b$, implemente e teste um algoritmo para trocar os valores atribuídos a elas.

#### Descrição geral do algoritmo

1. Guardar o valor original da variável $a$ em uma variável auxiliar $aux$;
2. Atribuir à variável $a$ o valor original da variável $b$;
3. Atribuir à variável $b$ o valor original da variável $a$, que está armazenado na variável auxiliar $aux$.
4. Exibir os novos valores de $a$ e $b$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite o valor da a:"}}
B --> C[\a\]
C --> D{{"Digite o valor da b:"}}
D --> E[\b\]
E --> F[aux = a]
F --> G[a = b]
G --> H[b = aux]
H --> I{{"a =", a}}
I --> J{{"b =", b}}
```

#### Pseudocódigo 

```java
ALGORTIMO TrocaValores
DECLARE a,b,axu: REAL

INICIO

    // Variável A como entrada
    ESCREVA "Digite o valor da a:"

    // Solicita ao usuário para inserir o valor de 'a'
    LEIA a

    // Solicita ao usuário para inserir o valor de 'b'
    ESCREVA "Digite o valor da b:"

    // Solicita ao usuário para inserir o valor de 'b'
    LEIA b

    // Troca os valores de 'a' e 'b' usando uma variável auxiliar
    aux <- a 

    // Atribui o valor de 'b' para 'a'
    a <- b

    // Atribui o valor original de 'a' (guardado em 'aux') para 'b'
    b <- aux

    // Exibe os novos valores de 'a' e 'b'
    ESCREVA "a=", a
    ESCREVA "b=", b

FIM
```

#### Tabela de testes

| a  | b  | aux | a  | b  | saída 1 | saída 2 | 
| -- | -- | --  | -- | -- | --      | --      | 
| 0  | 1  | 0   | 1  | 0  | a = 1   | b = 0   |

### Questão 2 - Contagem (1 ponto)

Dado um conjunto $n$ de notas de alunos em um exame, implemente e teste um algoritmo para fazer uma contagem $cont$ do número de alunos que foram aprovados no exame. 
Será considerado aprovado o aluno que tirar $nota$ 50 ou maior (no intervalo de 0 a 100).

#### Descrição geral do algoritmo

1. Obter o número de notas $n$ a serem processadas;
2. Inicializar a contagem $cont$ com zero;
3. Enquanto houver notas a serem processadas, fazer repetidamente:
    - obter a próxima nota;
    - se a nota for suficiente para passar no exame ($n ≥ 50$) então adicionar 1 (um) à contagem $cont$;
4. Exibir a contagem $cont$ (número total de aprovações).

#### Fluxograma 01
Fluxograma conforme descrição do algoritmo acima, usando o loop ENQUANTO.

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o número de alunos: }}
B --> C[\n\]
C --> D[\cont = 0\]
D --> E[\i = 1\]
E --> F{i <= n}
F --FALSE--> W{{Número de alunos aprovados: cont}}
W --> Z([FIM])
F --TRUE--> G{{Digite a nota do aluno, i}}
G --> H[\nota\]
H --> I{"nota >= 50 <br>E <br>nota <=100"}
I --TRUE--> J[\cont =+ 1\]
I --FALSE--> K[\i =+ 1\]
J --> K
K --LOOP--> F
```

#### Fluxograma 02
Fluxograma opcional usando o loop PARA.

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o número de notas: }}
B --> C[\n\]
C --> D[\cont = 0\]
D --> E[[i=1 ATE n PASSO 1]]
E --"i=1,2...,n"--> F{{Digite nota, i}}
E --"i > n"--> K{{Número de alunos aprovados: , cont}}
K --> L([FIM])
F --> G[\nota\]
G --> H{"nota >= 50 <br>E <br>nota <=100"}
H --FALSE/LOOP--> E
H --TRUE--> J[\cont =+ 1\]
J --LOOP--> E
```

#### Pseudocódigo 01 (1 ponto)

```java
ALGORTIMO ContaAprovacoes
DECLARE n, cont, nota, i: INTEIRO

INICIO

    // Solicita ao usuário para inserir a quantidade de notas dos alunos
    ESCREVA "Digite a quantidade de notas dos alunos:"

    // Lê o valor fornecido pelo usuário para a quantidade de notas
    LEIA n

    // Inicializa o contador
    cont = 0 

    // Loop para iterar sobre as notas dos alunos
    PARA i DE 1 ATE n FAÇA

        // Solicita ao usuário para inserir a nota do aluno atual
        ESCREVA "Digite a nota do aluno", i, ":"

        // Lê a nota fornecida pelo usuário
        LEIA nota

        // Verifica se a nota está dentro do intervalo de aprovação
        SE nota >= 50 E nota <= 100 ENTAO

            // Adiciona o contador de alunos aprovados
            cont = cont + 1 

        FIM_SE

    FIM_PARA

    // Exibe o número de alunos aprovados
    ESCREVA "O numero de alunos aprovados e:", cont

FIM
```

#### Tabela de testes 01
Tabela de testes referente ao algoritmo usando o loop ENQUANTO.

| it | n  | i  | cont | i<=n  | nota, i | nota | nota_valida | cont+1 | i+1 | saída        | 
| -- | -- | -- | --   | --    | --      | --   | --          | --     | --  | --           |
| 1  | 3  | 1  |  0   | True  | nota 1  | 60   | True        | 1      | 2   |              |
| 2  | 3  | 2  |  1   | True  | nota 2  | 40   | False       | 1      | 3   |              |
| 3  | 3  | 3  |  1   | True  | nota 3  | 90   | True        | 2      | 4   |              |
| 4  | 3  | 4  |  2   | False |         |      |             |        |     | Aprovados: 2 |

#### Tabela de testes 02
Tabela de testes referente ao algoritmo usando o loop PARA.

| it | n  | cont | i  | nota, i | nota | nota_valida | cont+1 | saída        | 
| -- | -- | --   | -- | --      | --   | --          | --     | --           |
| 1  | 3  | 0    | 1  | nota 1  | 60   | True        | 1      |              |
| 2  | 3  | 1    | 2  | nota 2  | 40   | False       | 1      |              |
| 3  | 3  | 1    | 3  | nota 3  | 90   | True        | 2      | Aprovados: 2 |

### Questão 3 - Soma de um conjunto de números (1 ponto)

Dado um conjunto de $n$ números, implemente e teste um algoritmo para calcular a soma desses números. <br>
Aceite apenas $n$ maior ou igual a zero.

#### Descrição geral do algoritmo

1. Obter a quantidade de números $n$ a serem somados.
2. Inicializar a variável $soma$ com 0 (zero).
3. Enquanto menos do que $n$ números tiverem sido somados, fazer repetidamente:
    - obter o próximo número $i$;
    - calcular a soma atual, adicionando o número $i$ obtido à soma mais recente;
4. Exibir a soma dos $n$ números

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a quantidade de números<br> (n >= 0):"}}
B --> C[\n\]
C --> D{n >= 0}
D --FALSE-->N{{"O valor deve ser maior ou igual a zero!"}}
N --> M([FIM])
D --TRUE--> E[/soma = 0/]
E --> F[i = 1]
F --> G{i <= n}
G --FALSE--> L{{"A soma dos numeros é , soma"}}
L --> M
G --TRUE--> H{{Digite um número: }}
H --> I[\num\]
I --> J[soma =+ num]
J --> K[i =+ 1]
K --LOOP--> G
```

#### Pseudocódigo (1 ponto)

```java
Algoritmo SomaNumeros
DECLARE n,i,soma: INTEIRO

INICIO

    // Solicita ao usuário para inserir a quantidade de números (n >= 0)
    ESCREVA "Digite a quantidade de números<br> (n >= 0):"
    LEIA n

    // Verifica se n é maior ou igual a zero
    SE n >= 0 ENTAO

        // Inicializa a variável soma
        soma <- 0

        // Inicializa o contador i
        i <- 1

        // Loop enquanto i for menor ou igual a n
        ENQUANTO i <= n FAÇA

            // Solicita ao usuário para inserir um número
            ESCREVA "Digite um número:"

            // Lê o número fornecido pelo usuário
            LEIA num 

            // Adiciona o número à soma
            soma <- soma + num

            // Incrementa o contador i
            i <- i + 1

        FIM_ENQUANTO

    // Caso n não seja maior ou igual a zero
    SENAO
        ESCREVA "O valor deve ser maior ou igual a zero!"

    FIM_SE

    // Exibe a soma dos números
    ESCREVA "A soma dos numeros é ", soma

FIM
```

#### Tabela de testes

| it | n  | n >= 0 | soma | i  | i <= n | num | soma =+ num  | saída                   |
| -- | -- | --     | --   | -- | --     | --  | --           | --                      |
|    | -3 | False  |      |    |        |     |              | O valor deve ser ...    |
| 1  | 0  | True   | 0    | 1  | False  |     |              | A soma dos números é 0  |
| 1  | 3  | True   | 0    | 1  | True   | 5   | 0 + 5 = 5    |                         |
| 2  | 3  | True   | 5    | 2  | True   | 10  | 5 + 10 = 15  |                         |
| 3  | 3  | True   | 15   | 3  | True   | 20  | 15 + 20 = 35 |                         |
| 4  | 3  | True   | 35   | 4  | False  |     |              | A soma dos números é 35 |

### Questão 4 - Cálculo de uma série (1 ponto)

Dado um conjunto de $n$ termos da série, implemente e teste um algoritmo para calcular o valor de S, conforme definido abaixo:

$$ S = \frac{1}{2} + \frac{3}{4} + \frac{5}{6} + \frac{7}{8} + \dots $$

#### Descrição geral do algoritmo

1. Obter o número de termos $n$;
2. Inicializar a variável $S$ com 0 (zero).
3. Iterar o valor de $n$ na variável $i$ iniciando com 0 (zero), de acordo com as instruções abaixo:
    - calcular o numerador na variável $numerador$;
    - calcular o denominador  na variável $denominador$;;
    - calcular o termo da série na variável $termo$, onde $termo = numerador/denominador$;
    - adicionar esse termo à variável $S$.
4. Exibir o valor da série $S$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite o número de termos da série S:"}}
B --> C[/n/]
C --> D[S = 0]
D --> E[[i=0 ATE n-1 PASSO 1]]
E --"i > n-1"--> J{{"Soma da série S é ", S}}
J --> K([FIM])
E --"i=0,1,2,..,n-1"--> F[numerador = 2 * i + 1]
F --> G[denominador = 2 * i + 2]
G --> H[termo = numerador / denominador]
H --> I[S += termo]
I --LOOP--> E
```

#### Pseudocódigo (1 ponto)

```java
Algoritmo SomaSerie
DECLARE n,numerador,denominador: INTEIRO; termo, S: REAL

INICIO

    // Solicita ao usuário para inserir o número de termos da série S
    ESCREVA "Digite o número de termos da série S:"

    // Lê o valor fornecido pelo usuário para o número de termos
    LEIA n

    // Inicializa a variável S que irá armazenar a soma dos termos
    S <- 0

    // Loop para calcular cada termo da série S e somá-lo
    PARA i de 0 ATÉ n-1 PASSO 1 FAÇA

        // Calcula o numerador do termo
        numerador = 2 * i + 1

        // Calcula o denominador do termo
        denominador <- 2 * i + 2

        // Calcula o termo atual da série S
        termo = numerador / denominador

        // Soma o termo atual à variável S
        S += termo

    FIM_PARA

    // Exibe a soma da série S
    ESCREVA "Soma da série S é ", S

FIM
```

#### Tabela de testes (0.25 ponto)

| it | n  | S  | i | numerador | denominador | termo | S += termo     | saída                  |
| -- | -- | -- |-- | --        | --          | --    | --             | --                     |
|    | 0  | 0  |   |           |             |       |                |                        |
| 1  | 4  | 0  | 0 | 2*0+1 = 1 | 2*0+2 = 2   | 1/2   | 0+1/2 = 1/2    |                        |
| 2  | 4  | 0  | 1 | 2*1+1 = 1 | 2*1+2 = 2   | 3/4   | 1/2+3/4 = 1.25 |                        |
| 3  | 4  | 0  | 2 | 2*2+1 = 1 | 2*2+2 = 2   | 5/6   | 0+1/2 = 2.08   |                        |
| 4  | 4  | 0  | 3 | 2*3+1 = 1 | 2*3+2 = 2   | 7/8   | 0+1/2 = 2.96   | Soma da série S é 2.96 |

### Questão 5 - Cálculo fatorial (2 pontos)

Dado um número $n$, implemente e teste um algoritmo para calcular o fatorial de $n$ (escrito como $n!$), onde $n ≥ 0$.

#### Descrição geral do algoritmo

1. Obter o número $n$, onde $n \geq 0$;
2. Inicializar a variável $fator$ com 1 (um) para armazenar o resultado do cálculo do fatorial;
3. Iterar o valor de $n$ na variável $i$, ou seja, executar $n$ vezes, as instruções abaixo:
    - Incrementar o valor atual $fator$ multiplicando pelo valor de $i$;
4. Exibir o resultado ($n!$).

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite um numero inteiro nao-negativo:"}}
B --> C[/n/]
C --> D{n >= 0}
D --TRUE--> E[fator = 1]
D --FALSE--> J{{"O valor deve ser maior ou igual a zero!"}}
J --> I([FIM])
E --> F[[i=1 ATÉ n PASSO 1]]
F --"i > n"--> H{{O fatorial de, n, é:, fator}}
F --"i=1,2,..n"--> G[fator = fator * i]
G --LOOP--> F
H --> I
```

#### Pseudocódigo (2 pontos)

```java
ALGORITMO CalcFatorial
DECLARE n: INTEIRO

INICIO

    // Solicita ao usuário para inserir um número inteiro não-negativo
    ESCREVA "Digite um numero inteiro nao-negativo:"

    // Lê o valor fornecido pelo usuário
    LEIA n

    // Verifica se o número fornecido é não-negativo
    SE n >= 0 ENTAO

        // Inicializa o fator como 1 para o cálculo do fatorial
        fator <- 1

        // Calcula o fatorial de n
        PARA i DE 1 ATÉ n PASSO 1 FAÇA

            // Multiplica o fator pelo valor de i (atual) para calcular o fatorial
            fator <- fator * i        // fator *= i

        FIM_PARA

        // Exibe o resultado do cálculo do fatorial
        ESCREVA "O fatorial de", n, "é:", fator

    // Caso o número fornecido seja negativo
    SENAO
        ESCREVA "O valor deve ser maior ou igual a zero!"
    FIM_SE

FIM
```

#### Tabela de testes

| n  | fator | i  | fator = fator * i | saída               |
| -- | --    | -- | --                | --                  |
| 3  | 1     | 1  | 1*1 = 1           |                     |
| 3  | 1     | 2  | 1*2 = 2           |                     |
| 3  | 2     | 3  | 2*3 = 6           | O fatorial de 3 é 6 |

### Questão 6 - Geração da sequência de Fibonacci (2 pontos)

Gerar e imprimir os $n$ primeiros termos da sequência de Fibonacci, onde $n ≥ 1$. <br>
Os primeiros termos são: $0, 1, 1, 2, 3, 5, 8, 13, \dots$. Cada termo, além dos dois primeiros, é derivado da soma dos seus dois antecessores mais próximos.

#### Descrição geral do algoritmo

1. Obter o número de termos $n$, onde $n \geq 1$;
2. Inicializar os dois primeiros termos da série nas variável $a$ e $b$ com 0 (zero);
3. Iterar o valor de $n$, ou seja, executar $n$ vezes, as instruções abaixo:
    - Imprimir o termo inicial $a$ (instrução para exibir a sequência ao atualizar a variável $a$);
    - Somar os termos $a$ e $b$ na variável $termo_atual$;
    - Atribuir a variável $a$ o valor da variável $b$;
    - Atribuir a variável $b$ o valor da variável $termo_atual$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Número de termos da série Fibonacci:"}}
B --> C[/n/]
C --> D[a = 0]
D --> E[b = 1]
E --> F[[i=1 ATÉ n PASSO 1]]
F --"i > n"--> K([FIM])
F --"i=1,2,...,n"--> G{{a}}
G --> H[termo_atual = a + b]
H --> I[a = b]
I --> J[b = termo_atual]
J --LOOP--> F 
```

#### Pseudocódigo (2 pontos)

```java
ALGORITMO GeraFibonacci
DECLARE n, a, b, termo_atual: INTEIRO

INICIO

    // Solicita ao usuário o número de termos da série Fibonacci
    ESCREVA "Número de termos da série Fibonacci:"

    // Lê o valor fornecido pelo usuário para o número de termos
    LEIA n

    // Inicializa o primeiro termo da série Fibonacci
    a <- 0

    // Inicializa o segundo termo da série Fibonacci
    b <- 1

    // Loop para calcular e imprimir os termos da série Fibonacci
    PARA i DE 1 ATE n FAÇA

        // Imprime o termo atual da série Fibonacci
        ESCREVA a

        // Calcula o próximo termo da série Fibonacci
        termo_atual <- a + b

        // Atualiza os valores de 'a' e 'b' para os próximos cálculos
        a <- b
        b <- termo_atual

    FIM_PARA
FIM
```
#### Tabela de testes

| it | n  | a  | b  | i  | saída | termo_atual = a + b | a = b | b = termo_atual |
| -- | -- | -- | -- | -- | --    | --                  | --    | --              |
| 1  | 5  | 0  | 1  | 1  | 0     | 0 + 1 = 1           | 1     | 1               |
| 2  | 5  | 1  | 1  | 2  | 1     | 1 + 1 = 2           | 1     | 2               |
| 3  | 5  | 1  | 2  | 3  | 1     | 1 + 2 = 3           | 2     | 3               |
| 4  | 5  | 2  | 3  | 4  | 2     | 2 + 3 = 5           | 3     | 5               |
| 4  | 5  | 3  | 5  | 5  | 3     | 3 + 5 = 8           | 5     | 8               |

### Questão 7 - Inversão dos dígitos de um número inteiro (2 pontos)

Implemente e teste um algoritmo para inverter a ordem dos dígitos de um número inteiro positivo.

#### Descrição geral do algoritmo

1. Obter o número inteiro positivo $num$ a ser invertido;
2. Inicializar a variável $num \textunderscore inv$ com 0 (zero);
3. Enquanto o número for maior que zero ($num > 0$), faça repetidamente:
    - Calcular o último dígito do número na variável $digito$;
    - Adicionar o dígito ao número invertido $num \textunderscore inv$;
    - Remover o último dígito do número original $num$; 
4. Exibir o número invertido.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número inteiro: }}
B --> C[\num\]
C --> D{num >= 0}
D --TRUE--> G[num_inv = 0]
G --> H{num > 0}
H --FALSE--> Z{{"Número invertido:", numero_inv}}
Z --> W([FIM])
H --TRUE--> I[digito = num % 10]
I --> J[num_inv = num_inv * 10 + digito]
J --> K[num = num // 10]
K --LOOP--> H
D --FALSE--> E{{O número deve ser positivo!}}
E --> W
```

#### Pseudocódigo (2 pontos)

```java
Algoritmo InverteInteiro
DECLARE num, num_inv, digito: INTEIRO

INICIO

    // Solicita ao usuário para inserir o número a ser invertido
    ESCREVA "Digite o número a ser invertido:"
    LEIA num

    // Verifica se o número é negativo
    SE num < 0 ENTAO

        // Exibe uma mensagem de erro se o número for negativo
        ESCREVA "O número deve ser positivo!"

    // Caso o número seja positivo
    SENAO

        // Inicializa a variável para armazenar o número invertido
        num_inv <- 0

        // Loop para inverter o número
        ENQUANTO num > 0 FAÇA

            // Obtém o último dígito do número
            digito <- num % 10

            // Adiciona o dígito invertido ao número invertido
            num_inv <- (num_inv * 10) + digito

            // Remove o último dígito do número original
            num <- num // 10

        // Exibe o número invertido
        ESCREVA "Número invertido:", num_inv

    FIM_SE

FIM
```

#### Tabela de testes

| it | num | num_inv | num > 0 | digito | num = num // 10 | num_inv = (num_inv * 10) + digito | Saída                        |
| -- | --  | --      | --     | --      | --              | --                                | --                           |
|    | -1  | 0       | False  |         |                 |                                   | O número deve ser positivo!  |
| 1  | 0   | 0       | False  |         |                 |                                   | Número invertido:: 0         |
| 1  | 42  | 0       | True   | 2       | 4               | 2                                 |                              |
| 2  | 4   | 2       | True   | 4       | 0               | 24                                |                              |
| 3  | 0   | 24      | False  |         |                 |                                   | Número invertido:: 24        |
