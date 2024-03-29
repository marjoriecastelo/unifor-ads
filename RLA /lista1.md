# UNIFOR
**Nome**: Marjorie Castelo dos Santos <br>
**Disciplina**: Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01 (1 ponto)
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma (0,25 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número:}}
B --> C[\numero\]
C --> D{numero >= 0}
D --FALSE--> E[O número não é positivo!]
D --TRUE--> F[resto = numero % 2]
E --> Z([FIM])
F --> G{resto == 0}
G --FALSE--> H{{O número é impar!}}
G --TRUE--> I{{O número é par!}}
H --> Z
I --> Z
```

#### Pseudocódigo
```java
ALGORTIMO verifica_par_impar
DECLARE numero, resto: INTEIRO

INICIO

    // Solicita ao usuário para inserir um número
    ESCREVA "Digite um número: "
    
    // Lê o número fornecido pelo usuário
    LEIA numero
    
    // Verifica se o número é não-negativo
    SE numero >= 0 ENTAO

        // Calcula o resto da divisão por 2 para determinar se o número é par ou ímpar
        resto <- numero % 2

        // Verifica se o resto da divisão é igual a zero (número par)
        SE resto == 0 ENTAO
            ESCREVA "O número é par!"

        // Se não for igual a zero, então o número é ímpar
        SENAO
          ESCREVA "O número é ímpar!"

        FIM_SE

    // Caso o número seja negativo
    SENAO             
        ESCREVA "O número deve ser positivo!"

    FIM_SE

FIM


```

#### Tabela de testes (0,25 ponto)
| numero | numero >= 0 | resto | resto == 0 | Saída |
| -- | -- | -- | -- | -- | 
| -1 | F |   |   | "O número deve ser postivo!" |
| 0  | V | 0 | V | "O número é par!" |
| 13 | V | 1 | F | "O número é impar!" |
| 30 | V | 0 | V | "O número é par!" |

## Exercício 02 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. 
Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite seu salário atual:"}}
B --> C[/sal_atual/]
C --> D{sal_atual <= 500}
D --FALSE--> E[sal_reaj = sal_atual * 1.1]
D --TRUE--> F[sal_reaj = sal_atual * 1.2]
E --> G{{O novo salário é, sal_reaj}}
F --> G
G --> H([FIM])
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORTIMO ReajusteSalario
DECLARE sal_atual, sal_reaj: REAL

INICIO

    // Solicita ao usuário para inserir seu salário atual
    ESCREVA "Digite seu salário atual:"

    // Lê o salário atual fornecido pelo usuário
    LEIA sal_atual

    // Verifica se o salário atual é menor ou igual a 500
    SE sal_atual <= 500 ENTAO
        // Se o salário for menor ou igual a 500, aplica-se um aumento de 20%
        sal_reaj = sal_atual * 1.2

    // Se o salário for maior que 500
    SENAO
        // Se o salário for maior que 500, aplica-se um aumento de 10%
        sal_reaj = sal_atual * 1.1

    FIM_SE

    // Exibe o novo salário reajustado
    ESCREVA "O novo salário é R$", sal_reaj

FIM
```

#### Tabela de testes (1.0 ponto)

| sal_atual | sal_atual >= 500 |sal_reaj       | saída                   | 
| --        | --               | --            | --                      | 
| 400       | False            | 400*1.2 = 480 | O novo salário é R$ 480 |
| 500       | True             | 500*1.2 = 600 | O novo salário é R$ 600 |
| 600       | True             | 600*1.1 = 660 | O novo salário é R$ 660 |

## Exercício 03 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado.

#### Fluxograma (1 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a nota 1:"}}
B --> C[/nota1/]
C --> D{{"Digite a nota 2:"}}
D --> E[/nota2/]
E --> F{nota1 >= 0<br> OU <br>nota2 >= 0}  
F --FALSE--> K{{"A nota deve ser maior que zero!"}}
K --> L([FIM])
F --TRUE--> G["media = (nota1 + nota2)/2"]
G --> H{media >= 7}
H --FALSE--> I{{"O aluno está reprovado!"}}
H --TRUE--> J{{"O aluno está aprovado!"}}
I --> L
J --> L
```

#### Pseudocódigo (1 ponto)

```java
ALGORTIMO SituacaoAluno
DECLARE nota1, nota2, media: REAL

INICIO

    // Solicita ao usuário para inserir a nota 1
    ESCREVA "Digite a nota 1:"

    // Lê a nota 1 fornecida pelo usuário
    LEIA nota1

    // Solicita ao usuário para inserir a nota 2
    ESCREVA "Digite a nota 2:"

    // Lê a nota 2 fornecida pelo usuário
    LEIA nota2

    // Verifica se ambas as notas são não-negativas
    SE nota1 >= 0 E nota2 >= 0 ENTAO

        // Calcula a média das duas notas
        media =  (nota1 + nota2)/2

        // Verifica se a média é maior ou igual a 7
        SE media >= 7 ENTAO
            // Exibe uma mensagem indicando que o aluno está aprovado
            ESCREVA "O aluno está aprovado!"

        // Se a média não for maior ou igual a 7
        SENAO
            // Exibe uma mensagem indicando que o aluno está reprovado
            ESCREVA "O aluno está reprovado!"

        FIM_SE

    // Se uma das notas for negativa
    SENAO
        // Exibe uma mensagem indicando que a nota deve ser maior que zero
        ESCREVA "A nota deve ser maior que zero!"

    FIM_SE

FIM
```

#### Tabela de testes (1 ponto)

| nota1 | nota2 | nota1 >= 0 E nota2 >= 0 | media        | saĩda | 
| --    | --    | --                      | --           | --    | 
| -1    | 0     | False                   |              | A nota deve ser maior que zero! | 
| 0     | 0     | True                    | (0+0)/2 = 0  | O aluno está reprovado!|
| 4     | 8     | True                    | (4+8)/2 = 6  | O aluno está reprovado!|
| 4     | 10    | True                    | (4+10)/2 = 7 | O aluno está aprovado!|

## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a sua idade:"}}
B --> C[/idade/]
C --> D{idade < 0}
D --FALSE--> E{idade >= 18}
E --FALSE--> F[anos_apto = 18 - idade]
F --> G{{Faltam, anos_apto, anos para o candidato estar apto!}}
G --> H([FIM])
E --TRUE--> I{{"O candidato está apto a tirar a CNH!"}}
I --> H
D --TRUE--> J{{"A idade deve ser maior que zero!"}}
J --> H 
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORTIMO AptoCNH
DECLARE idade, anos_apto: INTEIRO

INICIO

    // Solicita ao usuário para inserir sua idade
    ESCREVA "Digite a sua idade:"

    // Lê a idade fornecida pelo usuário
    LEIA idade

    // Verifica se a idade é negativa
    SE idade < 0 ENTAO
        // Exibe uma mensagem indicando que a idade deve ser maior que zero
        ESCREVA "A idade deve ser maior que zero!"

    // Se a idade não for negativa
    SENAO

        // Verifica se a idade é maior ou igual a 18
        SE idade >= 18 ENTAO
            // Exibe uma mensagem indicando que o candidato está apto a tirar a CNH
            ESCREVA "O candidato está apto a tirar a CNH!"

        // Se a idade for menor que 18
        SENAO

            // Calcula quantos anos faltam para o candidato estar apto
            anos_apto <- 18 - idade

            // Exibe a quantidade de anos que faltam para o candidato estar apto
            ESCREVA "Faltam", anos_apto, "ano(s) para o candidato estar apto!"

        FIM_SE

    FIM_SE

FIM
```

#### Tabela de testes (1.0 ponto)

| idade | idade < 0 | idade >= 18 | anos_apto | saída                                         | 
| --    | --        | --          | --        | --                                            | 
| -1    | True      |             |           |                                               |
| 0     | False     | False       | 18-0 = 18 | Faltam 18 ano(s) para o candidato estar apto! |
| 17    | False     | False       | 18-17 = 1 | Faltam 1 ano(s) para o candidato estar apto!  |
| 18    | False     | True        |           | O candidato está apto a tirar a CNH!          |
