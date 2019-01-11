---
layout: post
title: faça
---

Há tempos em que planejo uma série de postagens sobre sintaxes e semânticas de linguagens de programação. A ideia é em cada postagem partir de uma *keyword* (palavra-chave), *token* (símbolo) ou *expression* (expressão), estudando suas aplicações em diversas linguagens ao mesmo tempo em que uma tradução transforma seus sentidos estritamente lógicos e funcionais em outra coisa qualquer, provavelmente algo no campo da textualidade. A escolha de cada *token* não segue nenhum critério específico, apenas algum interesse estudar essa ou aquela *keyword* fora de um contexto prático e aplicativo (apesar de provavelmente tocarmos esses assuntos aqui e ali).

Sem mais introduções, vamos ao que interessa:

### **do**

**do** é um dos lexemas mais recorrentes nas linguagens de programação. Sua aplicação difere em diferentes paradigmas e linguagens de programação, mas seu sentido é quase sempre o mesmo: **fazer** uma série de instruções em sequência.

Na linguagem estruturada e imperativa C, o símbolo **do** faz parte de uma semântica de execução/condição/re-execução? (nesta ordem), acompanhada pela **token** **`while`** (**do-while**, faça-enquanto...). Significa que dado um corpo de ação contido dentro fecho faça{ .. }enquanto, a ação somente será reexecutada dada certa condição-teste no corpo de **while**. Uma definição comum dessa sequência de execuções é de *loop* (repetição). Como exemplo, o seguinte código:

```c
/* dowhile.c */
#include <stdio.h>

int main() {
  /* variável local */
  int regressiva = 10;
  
  /* repetição do */
  do {
    printf("contagem regressiva: %d\n", regressiva);
    regressiva = regressiva - 1;
    } while ( regressiva >= 0);
    
   return 0;
}
```
será compilado e executado para o seguinte programa:
```bash
$ gcc dowhile.c -o dowhile
$ ./dowhile
contagem regressiva: 10
contagem regressiva: 9
contagem regressiva: 8
contagem regressiva: 7
contagem regressiva: 6
contagem regressiva: 5
contagem regressiva: 4
contagem regressiva: 3
contagem regressiva: 2
contagem regressiva: 1
contagem regressiva: 0
$
```

Em Haskell, uma linguagem de programação de paradigma puramente funcional e tipada, **do** executa uma série de ações/comandos em sequência, produzindo e tornando 'visível' o último comando na cadeia.
```Haskell
-- src/lib/Lib.sh
module Lib
    ( boasVindas
    ) where

boasVindas :: IO ()
boasVindas = do putStrLn "Qual seu primeiro nome?"
                primeiro <- getLine
                putStrLn "E seu sobrenome?"
                ultimo <- getLine
                let completo = primeiro ++ " " ++ ultimo
                putStrLn ("Bem vindo, " ++ completo ++ "!")
```
```Haskell
-- ../app/Main.hs
module Main where

import Lib

main :: IO ()
main = boasVindas
```

```bash
$ stack run
Qual seu primeiro nome?
Marcos
E seu sobrenome?
Frankowicz
Bem vindo, Marcos Frankowicz!
$ 
```
