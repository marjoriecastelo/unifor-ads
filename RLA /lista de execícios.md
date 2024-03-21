Curso: analise e desenvolvimento de sistema
Disciplina: raciocinio logico
Código/Turma:T160-80
Professor: Ricardo Carubbi
Data: 21/04/24
Aluno(a):marjorie castelo dos santos
Matrícula: preencha com seus dados

1a chamada (Sim/Não): sim
2a chamada (Sim/Não):nao

Questão 1 - Troca dos valores de duas variáveis (1 ponto)
```mermaid



flowchart TD
A([INICIO]) --> B{{Digite o valor da a: }}
B --> C[\a\]
C --> D{{Digite o valor da b: }}
D --> E[\b\]
E --> F[aux = a]
F --> G[a = b]
G --> H[b = aux]
H --> I{{"a =", a}}
I --> J{{"b =", b}}

```
pseudocodico


1.algoritmo definir_variaveis{Definir variáveis a e b}
2.definir_variaveis --> atribuir_valores{Atribuir valores iniciais a e b}
3. atribuir_valores --> guardar_original{Guardar valor original de a em auxiliar}
4.guardar_original --> atribuir_a{Atribuir valor original de b a a}
5. atribuir_a --> atribuir_b{Atribuir valor original de a (guardado em auxiliar) a b}
6.  ALGORITIMO atribuir_b --> mostrar_novos_valores((Exibir novos valores de a e b))
7. FIM_SE
8. FIM


teste de mesa 

Teste de mesa referente ao algoritmo usando o loop PARA.

| it | n  | cont | i  | nota, i | nota | nota_valida | cont+1 | saída   
     
| -- | -- | --   | -- | --      | --   | --   | --    | --    |  --         |
| 1  | 3  | 0    | 1  | nota 1  | 60   | True        | 1      |              |
| 2  | 3  | 1    | 2  | nota 2  | 40   | False       | 1      |              |
| 3  | 3  | 1    | 3  | nota 3  | 90   | True        | 2      | Aprovados: 2 |





Questão 2 - Contagem (1 ponto)

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

pseudocodico

1. print("Digite o número de alunos: ")
2. n = int(input())  # número de alunos
3. cont = 0  # contador de alunos aprovados
4. i = 1  # contador para iterar sobre os alunos
//enquanto i for menor ou igual a n
5. while i <= n:
// Digite a nota do aluno i
6.print("Digite a nota do aluno", i, ":")
7.nota = float(input())
//Se a nota estiver entre 50 e 100 (inclusive)
8.if nota >= 50 and nota <= 100:
9.cont += 1  # Incrementa o contador de alunos aprovados
10.i += 1  # Incrementa o contador de alunos
//Número de alunos aprovados
11.print("Número de alunos aprovados:", cont)



###teste de mesa2

   | isto| n  | i  | continuação | i<=n  | nota, i | nota | nota_valida | cont+1 | i+1 | saída | 
| -- | -- | -- | --   | --    | --      | --   | --          | --     | --  | --           |
| 1  | 3  | 1  |  0   | True  | nota 1  | 60   | True        | 1      | 2   |              |
| 2  | 3  | 2  |  1   | True  | nota 2  | 40   | False       | 1      | 3   |              |
| 3  | 3  | 3  |  1   | True  | nota 3  | 90   | True        | 2      | 4   |              |
| 4  | 3  | 4  |  2   | False |         |      |             |        |     | Aprovados: 2 |


questao 3) Soma de um conjunto de números

```mermaid

flowchart TD
A([INICIO]) --> B([FIM])
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

pseudocodigo

  // INICIO
1.print("Digite o número de termos da série S: ")
2.n = int(input())  # número de termos da série
3.S = 0  # inicializa a série S com zero
   // Loop para cada termo da série
4.for i in range(n + 1):
5.numerador = 2 * i + 1
6.denominador = 2 * i + 2
7.termo = numerador / denominador
8.S += termo
  //Soma da série S
9.print("Soma da série S é", S)
  // FIM

###teste de mesa3

| it | n  | n >= 0 | soma | i  | i <= n | num | soma =+ num  | saída                   |
| -- | -- | --     | --   | -- | --     | --  | --           | --                      |
|    | -3 | False  |      |    |        |     |              | O valor deve ser ...    |
| 1  | 0  | True   | 0    | 1  | False  |     |              | A soma dos números é 0  |
| 1  | 3  | True   | 0    | 1  | True   | 5   | 0 + 5 = 5    |                         |
| 2  | 3  | True   | 5    | 2  | True   | 10  | 5 + 10 = 15  |                         |
| 3  | 3  | True   | 15   | 3  | True   | 20  | 15 + 20 = 35 |                         |
| 4  | 3  | True   | 35   | 4  | False  |     |              | A soma dos números é 35 |

questaon 4 -Cálculo de um serie


```mermaid

flowchart TD
A([INICIO]) --> B([FIM])
A([INICIO]) --> B{{Digite o número de termos da série S: }}
B --> C[/n/]
C --> D[S = 0]
D --> E[[i=0 ATE n PASSO 1]]
E --i > n--> J{{"Soma da série S é ", S}}
J --> K([FIM])
E --"i=0,1,2,..,n"--> F[numerador = 2 * i + 1]
F --> G[denominador = 2 * i + 2]
G --> H[termo = numerador / denominador]
H --> I[S += termo]
I --LOOP--> E
```

pseudocodigo

1.print("Digite o número de termos da série S: ")
2.n = int(input())  
3.S = 0  
4.for i in range(n + 1):
5.numerador = 2 * i + 1
6.denominador = 2 * i + 2
7.termo = numerador / denominador
8.S += termo
9.print("Soma da série S é", S)




###teste de mesa 4

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |
| it | n  | S  | i | numerador | denominador | termo | S += termo     | saída                  |
| -- | -- | -- |-- | --        | --          | --    | --             | --                     |
|    | 0  | 0  |   |           |             |       |                |                        |
| 1  | 4  | 0  | 0 | 2*0+1 = 1 | 2*0+2 = 2   | 1/2   | 0+1/2 = 1/2    |                        |
| 2  | 4  | 0  | 1 | 2*1+1 = 1 | 2*1+2 = 2   | 3/4   | 1/2+3/4 = 1.25 |                        |
| 3  | 4  | 0  | 2 | 2*2+1 = 1 | 2*2+2 = 2   | 5/6   | 0+1/2 = 2.08   |                        |
| 4  | 4  | 0  | 3 | 2*3+1 = 1 | 2*3+2 = 2   | 7/8   | 0+1/2 = 2.96   | Soma da série S é 2.96 |

Questão 5 - Cálculo fatorial 


```mermaid

flowchart TD
A([INICIO]) --> B([FIM])
A([INICIO]) --> B{{"Digite um numero inteiro nao-negativo:"}}
B --> C[/n/]
C --> D{n >= 0}
D --TRUE--> E[fator = 1]
D --FALSE--> J{{O valor deve ser maior ou igual a zero!}}
J --> I([FIM])
E --> F[[i=1 ATÉ n PASSO 1]]
F --"i > n"--> H{{O fatorial de, n, é:, fator}}
F --"i=1,2,..n"--> G[fator = fator * i]
G --LOOP--> F
H --> I
```
pseudocodigo

# Entrada
1.n = int(input("Digite um número inteiro não-negativo: "))
# Verificação se n é não-negativo
2.if n >= 0:
    # Inicialização do fator
3.fator = 1
    
# Loop para calcular o fatorial
4.for i in range(1, n + 1):
5.fator *= i
# Saída do resultado
6.print("O fatorial de", n, "é:", fator)
7.else:
# Mensagem de erro para valores negativos
8.print("O valor deve ser maior ou igual a zero!")
#FIM

###teste de mesa 5 
|N|fator| i | fator = fator * i| saida|
|  --  |  --  |  --  |  --  |  --  |  --             |
| 3  | 1     | 1  | 1*1 = 1    |                     |
| 3  | 1     | 2  | 1*2 = 2    |                     |
| 3  | 2     | 3  | 2*3 = 6    | O fatorial de 3 é 6 |

Questão 6 - Geração da sequência de Fibonacci

```mermaid
flowchart TD
A([INICIO]) --> B([FIM])
A([INICIO]) --> B{{"Número de termos da série Fibonacci:"}}
B --> C[a = 0]
C --> D[b = 1]
D --> E[[i=1 ATÉ n PASSO 1]]
E --"i > n"--> J([FIM])
E --"i=1,2,...,n"--> F{{a}}
F --> G[termo_atual = a + b]
G --> H[a = b]
H --> I[b = termo_atual]
I --LOOP--> E 
```

pseudocodigo
# Entrada do número de termos da série Fibonacci
1.n = int(input("Número de termos da série Fibonacci: "))
# Inicialização dos primeiros termos da série
2.a = 0
3.b = 1
# Loop para calcular os termos da série Fibonacci
4.for i in range(1, n + 1):
# Saída do termo atual
5.print("Termo", i, "da série Fibonacci:", a)
# Cálculo do próximo termo
6.termo_atual = a + b
# Atualização dos valores para o próximo cálculo
7. a = b
8. b = termo_atual

####teste de mesa 6

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |
| it | n  | a  | b  | i  | saída | termo_atual = a + b | a = b | b = termo_atual |
| -- | -- | -- | -- | -- | --    | --                  | --    | --              |
| 1  | 5  | 0  | 1  | 1  | 0     | 0 + 1 = 1           | 1     | 1               |
| 2  | 5  | 1  | 1  | 2  | 1     | 1 + 1 = 2           | 1     | 2               |
| 3  | 5  | 1  | 2  | 3  | 1     | 1 + 2 = 3           | 2     | 3               |
| 4  | 5  | 2  | 3  | 4  | 2     | 2 + 3 = 5           | 3     | 5               |
| 4  | 5  | 3  | 5  | 5  | 3     | 3 + 5 = 8           | 5     | 8               |

Questão 7 - Inversão dos dígitos de um número inteiro 

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
J --> K[numero = numero // 10]
K --LOOP--> H
D --FALSE--> E{{O número deve ser positivo!}}
E --> W
```

#### Teste de mesa 7

| it | num | num_inv | num > 0 | digito | num = num // 10 | num_inv = (num_inv * 10) + digito | Saída                       |
| -- | --  | --      | --     | --      | --              | --                                | --                          |
|    | -1  | 0       | False  |         |                 |                                   | O número deve ser positivo! |
| 1  | 0   | 0       | False  |         |                 |                                   | Número invertido:: 0        |
| 1  | 42  | 0       | True   | 2       | 4               | 2                                 |                             |
| 2  | 4   | 2       | True   | 4       | 0               | 24                                |                             |
| 3  | 0   | 24      | False  |         |                 |                                   | Número invertido:: 24       |
