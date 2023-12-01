# aprendendo-clojure
Repositório foca em aprender Clojure

## Instalação

Passo 1: Instalar o Java 
- https://adoptium.net/

Passo 2: No Powershell do windows execute como administrador e rode o seguinte comando:
```
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```
Passo 3: Em seguida instale através do seguinte comando:
```
iwr -useb github.com/clojure/brew-install/releases/latest/download/win-install.ps1 | iex
```
Passo 4: Escolha o local onde instalar. Número 1 caso não tenha permissao de admin e 2 ou 3 caso você tenha permissão.


## Linguagem

### Executar Funções
Para funções ou operações devem ser usadas entre () parenteses. A função que eu quero executar tambem deve vir sempre no inicio. Por exemplo:

```
(println "Bem vindo")
```

A função println retorna um valor nulo, por isso ele retorna nil na linha de baixo.

### Definição de Simbolos

Para definir um simbolo usamos o comando def. Por exemplo para definir uma variavel de produtos com valor 15 vou usar o seguinte comando.
```
(def total-de-produtos 15)
```
Para imprimir o valor da variavel usamos o println:
```
(println total-de-produtos)
```
Se quisermos imprimir um texto e logo em seguida o valor de uma variavel usamos o seguinte:
```
(println "Total" total-de-produtos)
```
Isso irá imprimir a palavra Total dar um espaço e exibir o valor da variavel.

Para mudar o valor de uma variavel podemos redefinir usando o def. Por exemplo:
```
(def total-de-produtos 10)
```

### Calculando valores

Para podermos por exemplo fazer uma soma, devemos lembrar que a função vem sempre no início então a soma de 2 valores ficaria assim:
```
(+ 13 3)
```
Isso irá somar 13 com 3. É como se inicialmente colocamos a função e logo em seguida os parametros dela.
```
(- 13 3)
```
Os operadores costumam ser funções em clojure. Podemos usar as operaçoes com os simbolos tambem.
```
(+ total-de-produtos 3)
```
Se quisermos redefinir um valor do total de produtos usaremos da seguinte maneira:
```
(def total-de-produtos (+ total-de-produtos 3))
```
Assim estamos usando o resultado de uma função como parametro de um novo simbolo.

### Imutabilidade - Vetor

Definiremos um vetor assim:
```
(def estoque ["Mochila","Camiseta"])
```
Para imprimir iremos fazer assim:
```
(println estoque )
```
Reparem que a impressão virá com espaço, porque a virgula para o clojure é como um espaço em branco.

#### Operacoes com o Vetor

Para imprimir um item do vetor podemos usar o simbolo dele como uma funcao. Por exemplo:
```
(estoque 0)
```
Você verá que será exibido o primeiro valor de dentro do vetor.

Para contar um vetor usaremos a função count:
```
(count estoque)
```

Para adicionar um valor novo dentro do vetor usaremos a funcao conj:
```
(conj estoque "Cadeira")
```
Mas se formos olhar para a impressao do estoque veremos que não irá redefinir o vetor.
```
(println estoque)
```

Para redefinir o vetor precisamos redefinir ele:
```
(def estoque (conj estoque "Cadeira"))
```
Ai sim iremos ter o estoque com o valor Cadeira redefinido dentro dele.
```
(println estoque)
```

### Criando uma função

Para criar uma função usaremo o defn, para isso precisamos dizer o nome da funcao e dizer que ela não irá receber nenhum parametro, para isso usaremos um [].
O corpo da função é passado na linha seguinte com um espaço identado. Nossa função ficará assim:
```
(defn imprime-mensagem 
    []
    (println "Bem vindo"))
```

Definida a função podemos executa-la simplemente chamando ela assim:
```
(imprime-mensagem)
```

Para passarmos parametros definimos dentro dos [] o nome do parametro. Por exemplo, vamos criar uma função que vai aplicar um desconto num valor.
```
(defn aplica-desconto 
    [valor-bruto]
    (* valor-bruto 0.9))
```    
Feito isso iremos imprimir passando um valor pra função
```
(aplica-desconto 100)
```

Na literatura veremos que o nome da função é escrito como uma solicitacao. Exemplo: a mesma função acima com esse formato.
```
(defn valor-descontado 
    [valor-bruto]
    (* valor-bruto 0.9))

(valor-descontado 100)
```

Podemos documentar a nossa função usando aspas duplas depois do nome dela. Por exemplo:
```
(defn valor-descontado 
    "Retorna o valor descontado de 90% do valor bruto"
    [valor-bruto]
    (* valor-bruto 0.9))
```

Desta maneira temos uma descrição do que esta função faz.