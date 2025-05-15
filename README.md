# Palavras-Chave (keywords) em Python

Este guia aborda as keywords mais utilizadas em Python, com uma explicação prática de fácil compreensão.
---

## * `def`: é a palavra-chave usada para definir uma função.
_Quando você usa `def`, você está dizendo ao Python: "Estou prestes a criar uma nova função com este nome e este é o código que ela executará."_

**Estrutura básica:**
```python
def nome_da_funcao(parametro1, parametro2, ...):
    # Bloco de código da função (indentado)
    # O que a função faz
    [return valor_de_retorno] # Opcional
```    

**Exemplo:**
```
def saudar(nome):
    mensagem = "Olá, " + nome + "!"
    return mensagem

# Chamando a função
print(saudar("Fulano"))  

# Saída será: 
Olá, Fulano!
```
---

## * `class`: Usada para definir uma classe.
_Pense em class como o momento em que você desenha a planta baixa de uma casa ou cria uma forma de biscoitos.  
Você está definindo o molde para todas as casas ou biscoitos que virão.  
Esses "biscoitos" ou "casas" reais e concretas que são construídos a partir desses moldes são os objetos!_

**Estrutura básica:**
```
class NomeDaClasse:
    # Método especial construtor, chamado ao criar um objeto
    def __init__(self, parametro1, parametro2, ...):
        # self.atributo1 = parametro1  # Define os atributos (estado) do objeto
        # self.atributo2 = "algum valor"
        pass # Remova o 'pass' ao adicionar seus atributos

    # Outros métodos (comportamentos do objeto)
    def algum_metodo(self, parametro_metodo, ...):
        # Lógica do método
        # Pode usar self.atributo1, etc.
        pass # Remova o 'pass' ao implementar
```

**Exemplo:**
```
class Pessoa:
    def __init__(self, nome, idade):
        self.nome = nome  # Atributo do objeto
        self.idade = idade # Atributo do objeto

    def apresentar(self): # Método do objeto
        return f"Olá, meu nome é {self.nome} e tenho {self.idade} anos."

# Criando objetos (instâncias da classe Pessoa)
pessoa1 = Pessoa("Ana", 30)
pessoa2 = Pessoa("Carlos", 25)

print(pessoa1.apresentar()) # Saída: Olá, meu nome é Ana e tenho 30 anos.
print(pessoa2.nome)       # Saída: Carlos
```
---

## O que são Objetos (criados a partir de classes)?
Se as classes são os "moldes", os objetos são as coisas reais e concretas construídas a partir desses moldes. Um objeto é uma instância de uma classe.

Os objetos possuem:
- Estado (Atributos/Propriedades): Os dados que descrevem o objeto. No exemplo Pessoa, nome e idade são atributos. Cada objeto Pessoa (Ana, Carlos) tem seus próprios valores para esses atributos.

- Comportamento (Métodos): As ações que o objeto pode realizar. No exemplo Pessoa, apresentar() é um método. Todos os objetos Pessoa podem usar o método apresentar().

**Exemplo mais detalhado com Objetos:**

```
class Cachorro:
    def __init__(self, nome_do_cachorro, raca_do_cachorro):
        self.nome = nome_do_cachorro
        self.raca = raca_do_cachorro
        self.energia = 100

    def latir(self):
        if self.energia > 10:
            self.energia -= 5
            return f"{self.nome} ({self.raca}) diz: Au au!"
        else:
            return f"{self.nome} ({self.raca}) está muito cansado para latir."

    def brincar(self):
        if self.energia >= 20:
            self.energia -= 20
            return f"{self.nome} está brincando feliz!"
        else:
            return f"{self.nome} não tem energia para brincar agora."

# Criando objetos Cachorro
cachorro_rex = Cachorro("Rex", "Labrador")
cachorro_toto = Cachorro("Totó", "Poodle")

# Cada objeto tem seu próprio estado (seus próprios atributos)
print(f"Nome: {cachorro_rex.nome}, Raça: {cachorro_rex.raca}, Energia: {cachorro_rex.energia}")
print(f"Nome: {cachorro_toto.nome}, Raça: {cachorro_toto.raca}, Energia: {cachorro_toto.energia}")

# Objetos usam os comportamentos (métodos) definidos na classe
print(cachorro_rex.latir())
print(cachorro_toto.brincar())
print(f"Energia do Totó agora: {cachorro_toto.energia}")
```
Em Python, quase tudo é um objeto (números, strings, listas, e instâncias de suas classes).

---
## ESTRUTURAS CONDICIONAIS:
## * `if, elif, else`: Usadas para estruturas condicionais.
A estrutura condicional permite o desvio de fluxo de controle, quando determinadas expressões lógicas são atendidas.

_Imagine que o Python é um porteiro tomando decisões._  
- if é a primeira pergunta ("Você tem convite?")
- elif é uma pergunta alternativa ("Se não, você está na lista?")
- else é o que acontece se nenhuma das condições anteriores for atendida ("Desculpe, não pode entrar").

**Estrutura básica:**
```
if condicao1:
    # Bloco de código se condicao1 for Verdadeira
elif condicao2:
    # Bloco de código se condicao1 for Falsa E condicao2 for Verdadeira
else:
    # Bloco de código se todas as condições anteriores forem Falsas
```

**Exemplo:**
```
idade = 20
if idade < 18:
    print("Menor de idade.")
elif idade == 18:
    print("Tem exatamente 18 anos.")
else:
    print("Maior de idade.")
# Saída: Maior de idade.
```
### * `if` ternário: Usado em uma única linha de código.
_Pense no `if` ternário como um "decisor rápido e direto". Em vez de usar um bloco if e else mais longo só para escolher um entre dois valores para uma variável, você faz a pergunta (if condição) e já diz "Me dê este valor se for sim, ou aquele valor se for não (else)". É a resposta instantânea para uma escolha simples!  

**Estrutura básica:**
```
valor_se_verdadeiro if condicao else valor_se_falso
```
- A condicao (condição) é avaliada primeiro.
- Se a condicao for True (Verdadeira), a expressão inteira retorna o valor_se_verdadeiro.
- Se a condicao for False (Falsa), a expressão inteira retorna o valor_se_falso.

**Exemplo:**
```
# Imagine que você tem um 'saldo' na conta e vai fazer um 'saque'
saldo = 2000
saque = 500

# Decidimos o 'status' da operação em uma única linha:
# Se o saldo for MAIOR que o saque, o status é "Sucesso", SENÃO ("else") é "Falha".
status = "Sucesso" if saldo > saque else "Falha"

print(f"O status ao realizar o saque é: {status}")

# Neste exemplo, 2000 é > 500 (Verdadeiro), então a condição é True.
# A expressão retorna "Sucesso".
# Saída esperada: O status ao realizar o saque é: Sucesso

# Se alterássemos:
# saldo = 300
# saque = 500
# status = "Sucesso" if saldo > saque else "Falha"
# Neste caso, 300 > 500 (Falso), então a condição é False.
# A expressão retornaria "Falha".
```
---
## ESTRUTURAS DE REPETIÇÃO:
## * `for`: Usada para laços de repetição (iterar sobre sequências).
_O `for` é como um funcionário que pega cada item de uma caixa (uma lista, uma string, etc.), um por vez, e faz algo com ele até que todos os itens tenham sido processados._


**Estrutura básica:**
```
for variavel_item in sequencia:
    # Bloco de código executado para cada item na sequencia
    # Use a variavel_item aqui
```

**Exemplo:**
```
frutas = ["maçã", "banana", "cereja"]
for fruta in frutas:
    print(f"Eu gosto de {fruta}")

# Usando range para repetir um número de vezes
for numero in range(3): # Gera números de 0 a 2
    print(f"Número: {numero}")
```

## Função `range()`
_Imagine a função `range()` como um "gerador de sequências numéricas" super eficiente. Em vez de criar uma lista gigante de números na memória de uma só vez (o que poderia consumir muito espaço para sequências grandes!), o `range()` é "inteligente".  Ele sabe de onde começar (o início), onde parar (E ATENÇÃO: ele para antes de chegar neste número final!) e de quanto em quanto pular. Ele só "produz" o próximo número da sequência quando um loop `for` (ou outra operação que precise dos números) pede. É perfeito para controlar quantas vezes um loop deve rodar ou para iterar sobre índices!_

**Sintaxe e Uso:**
`range()` é uma função built-in do Python e serve para gerar sequências imutáveis de números, frequentemente usada em loops `for`. Ela pode ser usada de três formas:

- `range(stop)`: Gera números inteiros começando em `0` (padrão) e terminando **antes** de `stop`. O argumento `stop` é **obrigatório** e o fim da sequência é **exclusivo**.
- `range(start, stop)`: Gera uma sequência de números inteiros começando em `start` (inclusive) até `stop - 1` (exclusivo). `start` e `stop` são **obrigatórios** nesta forma, o `step` padrão é `1`.
- `range(start, stop, step)`: Gera uma sequência de números inteiros começando em `start` (inclusive) até `stop - 1` (exclusivo), pulando de acordo com o valor de `step`. Todos os três argumentos são **obrigatórios** nesta forma.

**Exemplos:** 
```
# Exemplo 1: range(stop) - Gera números de 0 até 4 (5-1)
list(range(4)) -> [0, 1, 2, 3]

# Exemplo 2: range(stop) com for
for numero in range(5):
    print(numero, end=" ")
# Saída esperada: 0 1 2 3 4

# Exemplo 3: range(start, stop) - Gera números de 2 até 5 (6-1)
for i in range(2, 6):
    print(i, end=" ")
# Saída esperada: 2 3 4 5

# Exemplo 4: range(start, stop, step) - Gera números de 0 até 10 (11-1), pulando de 2 em 2
for i in range(0, 11, 2):
    print(i, end=" ")
# Saída esperada: 0 2 4 6 8 10
```
---

## * `while`: Usada para laços de repetição (enquanto uma condição for verdadeira).
_O `while` é como dizer "continue fazendo isso enquanto esta luz estiver verde". Assim que a luz ficar vermelha (a condição se tornar falsa), pare!_
Faz sentido usar `while` quando não sabemos o número exato de vezes que o bloco de código deve ser executado.


**Estrutura básica:**
```
while condicao_verdadeira:
    # Bloco de código executado repetidamente
    # Importante: algo dentro do loop deve eventualmente tornar a condição_verdadeira Falsa
```

**Exemplo:**
```
contador = 0
while contador < 3:
    print(f"Contador é {contador}")
    contador += 1 # Incrementa o contador para evitar loop infinito
# Saída:
# Contador é 0
# Contador é 1
# Contador é 2
```

## * `break`: Usado para interromper a repetição.
_Pense na palavra-chave `break` como um "botão de parada imediata" para os seus loops (`for` e `while`). Normalmente, um loop segue seu curso natural – o `for` até processar todos os itens ou o `while` até sua condição se tornar falsa. Mas se, no meio dessa repetição, uma situação específica ocorrer e você decidir que não precisa ou não quer mais continuar o loop, o `break` é o seu comando mágico. Ele diz ao Python para **encerrar o loop na hora**, ignorando quaisquer iterações futuras ou a condição do `while`, e continuar a execução do programa na primeira linha *após* o loop. É útil para otimizar o código, parando um processo assim que o objetivo for atingido (como encontrar um item em uma busca)._

Geralmente, o `break` é usado em conjunto com uma estrutura condicional (`if`) dentro do loop, para que a saída prematura ocorra apenas quando uma condição específica for atendida.

**Exemplos:**
```
# Exemplo 1: Usando break em um loop for para parar uma busca
print("--- Usando break em um loop for ---")
frutas = ["maçã", "banana", "cereja", "uva", "laranja"]
item_desejado = "cereja"

print(f"Procurando por '{item_desejado}' na lista de frutas:")
for fruta in frutas:
    print(f"Verificando: {fruta}")
    if fruta == item_desejado:
        print(f"Encontramos '{item_desejado}'! Não precisamos procurar mais.")
        break # Sai do loop for imediatamente

print("Execução continua após o loop for.")
# Saída esperada:
# --- Usando break em um loop for ---
# Procurando por 'cereja' na lista de frutas:
# Verificando: maçã
# Verificando: banana
# Verificando: cereja
# Encontramos 'cereja'! Não precisamos procurar mais.
# Execução continua após o loop for.

# Exemplo 2: Usando break em um loop while para sair sob condição
print("\n--- Usando break em um loop while ---")
contador = 0
limite = 10

print(f"Contando de 0 até um limite, mas parando se chegar a 5:")
while contador <= limite:
    print(f"Contador atual: {contador}")
    if contador == 5:
        print("Chegamos a 5! Hora de parar.")
        break # Sai do loop while imediatamente
    contador += 1

print("Execução continua após o loop while.")
# Saída esperada:
# --- Usando break em um loop while ---
# Contando de 0 até um limite, mas parando se chegar a 5:
# Contador atual: 0
# Contador atual: 1
# Contador atual: 2
# Contador atual: 3
# Contador atual: 4
# Contador atual: 5
# Chegamos a 5! Hora de parar.
# Execução continua após o loop while.
```
---
////////////////////
## * `return`: Usada dentro de uma função para enviar um valor de volta.
_Quando uma função com `return` termina seu trabalho, ela é como um mensageiro que volta para quem a chamou e entrega um pacote (o valor de retorno). Se não houver `return` explícito ou se for `return None`, ela entrega um "pacote vazio" (None)._


**Estrutura básica:**
```
def nome_da_funcao(parametros):
    # ... processamento ...
    valor_a_retornar = "algo"
    return valor_a_retornar
```

**Exemplo:**
```
def adicionar(x, y):
    soma = x + y
    return soma

resultado_soma = adicionar(5, 3)
print(f"O resultado da soma é: {resultado_soma}") 
# Saída: O resultado da soma é: 8
```
---

## * `import, from`: Usadas para importar módulos.
_`import nome_modulo` é como pegar uma caixa de ferramentas inteira (o módulo) para usar.  
 `from nome_modulo import ferramenta_especifica`  é como pegar apenas uma ferramenta específica dessa caixa._


**Estrutura básica:**
```
import nome_do_modulo
# Uso: nome_do_modulo.funcao_do_modulo()

from nome_do_modulo import item_especifico
# Uso: item_especifico()

from nome_do_modulo import item1 as apelido1, item2
# Uso: apelido1(), item2()
```

**Exemplo:**
```
import math
print(f"O valor de PI é aproximadamente: {math.pi}")

from random import randint
numero_aleatorio = randint(1, 10) # Gera um inteiro aleatório entre 1 e 10
print(f"Número aleatório: {numero_aleatorio}")
```
---

## * `try, except, finally`: Usadas para tratamento de exceções.
_`try` é como dizer "Vou tentar fazer isso, que pode dar errado".  
 `except TipoDeErro` é o plano B ("Se der aquele tipo de erro específico, faça isso").  
 `finally` é "Não importa se deu certo ou errado, faça isso no final de qualquer jeito"._


**Estrutura básica:**
```
try:
    # Bloco de código onde um erro (exceção) pode ocorrer
    pass
except NomeDoErroEspecifico:
    # Bloco de código para tratar o NomeDoErroEspecifico
    pass
except OutroErroEspecifico as e: # 'e' contém informações sobre o erro
    # Bloco de código para tratar o OutroErroEspecifico
    print(f"Ocorreu um erro: {e}")
else:
    # Bloco opcional, executa se NENHUMA exceção ocorreu no bloco try
    pass
finally:
    # Bloco opcional, SEMPRE executa, ocorrendo exceção ou não
    pass
```

**Exemplo:**
```
try:
    numero = int(input("Digite um número: "))
    resultado = 10 / numero
    print(f"10 dividido por {numero} é {resultado}")
except ValueError:
    print("Entrada inválida! Por favor, digite um número.")
except ZeroDivisionError:
    print("Erro: Não é possível dividir por zero!")
finally:
    print("Fim da tentativa de cálculo.")
```
---

## * `pass`: Uma operação nula (placeholder).
_`pass` é como um bilhete dizendo "Construção em andamento aqui" ou "Ainda vou preencher isso".  
 O Python vê que tem algo ali (para satisfazer a sintaxe que exige um bloco), mas não faz nada, só continua. Útil para quando você sabe que precisa de uma função, classe ou bloco condicional, mas ainda não escreveu o código interno._


**Estrutura básica:**
```
def funcao_ainda_nao_implementada():
    pass # TODO: Implementar a lógica desta função depois

if condicao_complexa:
    pass # Lógica a ser definida
else:
    print("Condição não atendida")
```

**Exemplo:**
```
class MinhaClasseFutura:
    pass # Atributos e métodos serão adicionados aqui

def processar_dados(dados):
    if not dados:
        pass # O que fazer se 'dados' estiver vazio? Pensar depois.
    else:
        print("Processando dados...")

processar_dados([]) # Nada acontece visivelmente por causa do pass
```
---

## * `lambda`: Usada para criar pequenas funções anônimas.
_`lambda` é para criar uma "funçãozinha rápida" de uma linha só, sem precisar de todo o ritual do `def` com nome e bloco. É como um bilhete de anotação com uma instrução simples, em vez de uma carta formal. Geralmente usada para funções que serão usadas uma vez ou como argumento para outras funções (como `map, filter, sorted`)._


**Estrutura básica:**
```
nome_da_variavel = lambda argumento1, argumento2, ...: expressao_que_retorna_um_valor
```

**Exemplo:**
```
# Função normal
def dobrar_valor(x):
    return x * 2

# Função lambda equivalente
dobrar_com_lambda = lambda x: x * 2

print(dobrar_valor(5))         # Saída: 10
print(dobrar_com_lambda(5))    # Saída: 10

# Usando lambda com sorted
pontos = [(1, 2), (3, 1), (5, 4), (2, 0)]
# Ordenar pela segunda coordenada do par (y)
pontos_ordenados = sorted(pontos, key=lambda ponto: ponto[1])
print(pontos_ordenados) # Saída: [(2, 0), (3, 1), (1, 2), (5, 4)]
```
---

## * `yield`: Usada em funções geradoras.
_`yield` em uma função transforma-a em um "gerador". É como um mágico que tira coelhos da cartola um por vez, mas só quando você pede o próximo. A função "pausa" após cada `yield` e entrega um valor. Quando você pede o próximo valor, ela "retoma" de onde parou. Isso é muito eficiente para criar sequências grandes ou infinitas, pois não gera todos os valores de uma vez na memória._


**Estrutura básica (dentro de uma função):**
```
def nome_da_funcao_geradora(parametros):
    # ... lógica ...
    yield valor1
    # ... mais lógica ...
    yield valor2
    # ... etc ...
```

**Exemplo:**
```
def contador_simples(maximo):
    n = 0
    while n < maximo:
        yield n # Pausa aqui e retorna 'n'
        n += 1  # Retoma daqui na próxima chamada a next()

# Usando o gerador
meu_contador = contador_simples(3)

print(next(meu_contador)) # Saída: 0
print(next(meu_contador)) # Saída: 1
print(next(meu_contador)) # Saída: 2
# print(next(meu_contador)) # Isso geraria um erro StopIteration, pois não há mais valores

# Geradores são frequentemente usados com loops 'for'
print("Usando com loop for:")
for numero in contador_simples(3):
    print(numero)
```
---

## * `with`: Usada com gerenciadores de contexto.
_`with` é como contratar um ajudante muito responsável para usar um recurso que precisa ser configurado e depois, importantíssimo, liberado (como um arquivo, uma conexão de rede, um bloqueio).  
 Você diz: "Com este recurso (ex: arquivo), faça o seguinte...". O "ajudante" (gerenciador de contexto) garante que, não importa o que aconteça (mesmo se ocorrer um erro), o recurso será devidamente preparado no início e limpo/liberado no final (o arquivo será fechado, a conexão encerrada, etc.)._ 

**Estrutura básica:**
```
with expressao_que_retorna_um_gerenciador_de_contexto [as nome_da_variavel]:
# Bloco de código que usa o recurso
```

**Exemplo (muito comum com arquivos):**
```
# Escrevendo em um arquivo
try:
    with open("meu_arquivo.txt", "w") as arquivo: # 'arquivo' é o objeto retornado por open()
        arquivo.write("Olá, mundo do 'with'!\n")
        arquivo.write("Esta é a segunda linha.")
    # Ao sair do bloco 'with', o arquivo é automaticamente fechado, mesmo se ocorrer um erro.

    # Lendo de um arquivo
    with open("meu_arquivo.txt", "r") as arquivo:
        conteudo_completo = arquivo.read()
        print("Conteúdo do arquivo:")
        print(conteudo_completo)
except IOError:
    print("Ocorreu um erro de E/S (Entrada/Saída) com o arquivo.")
```
---

## * `del`: Usada para deletar objetos, variáveis ou itens.
_`del` é o comando para "apagar", "remover" ou "desassociar" um nome de um objeto. Pode ser usado para remover uma variável que você não precisa mais, um item de uma lista pelo seu índice, uma fatia de uma lista, ou uma chave (e seu valor) de um dicionário. Ao deletar a última referência a um objeto, ele se torna elegível para ser removido da memória pelo coletor de lixo do Python._ 

**Exemplo:**
```
# Deletar uma variável
minha_variavel = 10
# print(minha_variavel) # Funciona
del minha_variavel
# print(minha_variavel) # Geraria um NameError, pois 'minha_variavel' não existe mais

# Deletar um item de uma lista
numeros = [10, 20, 30, 40, 50]
del numeros[2] # Remove o item no índice 2 (o valor 30)
print(numeros)   # Saída: [10, 20, 40, 50]

# Deletar uma fatia de uma lista
del numeros[1:3] # Remove os itens dos índices 1 e 2 ([20, 40] da lista atual)
print(numeros)   # Saída: [10, 50]

# Deletar uma chave de um dicionário
meu_dicionario = {"nome": "Carlos", "idade": 30, "cidade": "SP"}
del meu_dicionario["idade"]
print(meu_dicionario) # Saída: {'nome': 'Carlos', 'cidade': 'SP'}
```
---

---
### _Disclaimer_

Este guia foi produzido como parte da minha jornada de aprendizado em Python.   
Sou um estudante e estou sempre buscando evoluir.

Caso você encontre alguma informação que possa ser corrigida ou tenha sugestões para melhorar este material, por favor, não hesite em contribuir!  
Você pode abrir uma *issue*  no [repositório deste projeto no GitHub](https://github.com/elilopes-c/keywords-python).

Toda colaboração é muito bem-vinda e apreciada! 😊

