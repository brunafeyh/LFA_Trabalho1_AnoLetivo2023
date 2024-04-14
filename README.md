## Simulador de AFD (Autômato Finito Determinístico)

Este é um simulador de Autômato Finito Determinístico (AFD) implementado em linguagem C, desenvolvido para interagir com o usuário através da linha de comando do sistema operacional.

### Requisitos do Programa

- O programa foi implementado em C e interage com o usuário via prompt de comando, sem utilizar qualquer interface gráfica.
- O alfabeto de entrada é composto por letras minúsculas e/ou dígitos.
- A especificação do autômato é carregada a partir de um arquivo texto, seguindo a sintaxe especificada abaixo.
- O símbolo "@" é usado para representar a palavra vazia.
- O programa permite ao usuário inserir palavras para serem testadas, imprimindo o passo a passo do processamento.

### Sintaxe do Arquivo de Especificação do Autômato

- A primeira linha contém o alfabeto.
- A segunda linha contém os estados do autômato, nomeados com "q" seguido de um inteiro. O estado inicial é assumido como "q0".
- A terceira linha contém os estados finais.
- A partir da quarta linha são especificadas as transições, uma por linha, no formato (estado_origem, símbolo) = estado_destino.

### Exemplo de Arquivo de Especificação

```plaintext
alfabeto={a,b,c,0,1,2}
estados={q0,q1,q2,q3,q4,q5}
finais={q2,q5}
(q0,a)=q1
(q1,a)=q2
(q1,b)=q1
(q1,0)=q4
(q2,c)=q3
(q3,b)=q2
(q3,0)=q5
(q4,0)=q2
(q4,1)=q5
(q5,2)=q4
```

### Exemplo de Uso

```plaintext
$ ./simuladorAFD arquivo.txt
Digite uma palavra para ser testada: abbac
[q0]abbac
[q1]bbac
[q1]bac
[q1]ac
[q2]c
[q3]REJEIÇÃO

$ ./simuladorAFD arquivo.txt
Digite uma palavra para ser testada: ab00cb
[q0]ab00cb
[q1]b00cb
[q1]00cb
[q4]0cb
[q2]cb
[q3]b
[q2]ACEITAÇÃO
```

### Critérios de Avaliação

- Documentação, organização e qualidade do código fonte (Peso: 1).
- Implementação correta do simulador (Peso: 9).

