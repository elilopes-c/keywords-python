# Palavras-Chave (keywords) em Python

Este guia aborda as keywords mais utilizadas em Python, com uma explicação prática de fácil compreensão.
---

## **O que são e Por que Usar Funções:**
Em Python, funções são blocos de código nomeados e reutilizáveis projetados para realizar uma tarefa específica. Elas são definidas usando a palavra-chave `def`.

_Imagine que você tem uma tarefa específica no seu programa que precisa executar várias vezes, ou talvez seja uma sequência de passos que você quer dar um "nome" para facilitar. As funções são como "receitas" ou "mini-programas" que você cria! Você usa a palavra mágica `def` (de "definir") para dar um nome à sua receita (sua função) e ensina ao Python os passos que ela deve seguir. Depois, sempre que precisar que essa "receita" seja executada, basta "chamar" a função pelo nome dela. É como ter um kit de ferramentas onde cada ferramenta (função) faz uma tarefa específica, evitando que você tenha que construir a ferramenta do zero toda hora! Você pode até passar "ingredientes" (parâmetros) para a receita e ela pode te dar um "produto final" (retorno)._

Utilizar funções é fundamental para:

- **Modularizar o Código:** Dividir um programa grande em partes menores e mais gerenciáveis.
- **Reutilizar Código:** Evitar a repetição de blocos de código (Princípio DRY: Don't Repeat Yourself - Não se Repita).
- **Melhorar a Legibilidade:** Dar nomes descritivos a blocos de código que realizam tarefas claras.
- **Facilitar a Manutenção:** Alterações em uma funcionalidade são feitas em apenas um local (na definição da função).
- **Abstração:** Ocultar detalhes de implementação, permitindo que o programador pense em um nível mais alto.

**Definindo uma Função:**
A definição de uma função começa com `def`, seguida pelo nome da função, parênteses `()` (que podem conter parâmetros) e dois pontos `:`. O corpo da função é o bloco de código indentado abaixo da linha de definição.

**Sintaxe:**
```python
def nome_da_funcao(parametro1, parametro2, ...):
    # Corpo da função
    # Instruções que a função executa
    # Pode haver um comando 'return' para retornar um valor
    pass # 'pass' é usado quando o corpo está vazio (temporariamente)
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

## * `return`: Usada exclusivamente dentro do corpo de uma função em Python. Sua função principal é:

1.  **Encerrar a Execução da Função:** Assim que a linha com `return` é alcançada, a execução da função para imediatamente. Qualquer código após o `return` dentro da mesma função **não** será executado.
2.  **Enviar um Valor de Volta:** O valor especificado após o `return` é "retornado" para o código que chamou a função. Este valor pode ser capturado e utilizado (por exemplo, atribuído a uma variável).

* Se uma função termina sem um `return` explícito que especifique um valor, ou se você apenas escreve `return` sem nada depois, a função implicitamente retorna o objeto `None`.

**Retornando Múltiplos Valores:**
Embora uma função em Python retorne tecnicamente um único objeto, você pode retornar múltiplos valores simplesmente listando-os separados por vírgulas após o `return`. Python automaticamente empacota esses valores em uma **tupla** e retorna essa tupla. No código que chama a função, você pode desempacotar essa tupla em variáveis separadas.

**Exemplos:**

```
# Exemplo 1: Função retornando um único valor (simples)
def criar_saudacao(nome):
    """Recebe um nome e retorna uma mensagem de saudação."""
    mensagem = f"Olá, {nome}! Tudo bem?"
    return mensagem # Retorna a string criada

# Chamando a função e usando a mensagem retornada
saudacao_pronta = criar_saudacao("Ana")
print(saudacao_pronta)
# Saída: Olá, Ana! Tudo bem?

# Exemplo 2: Função sem return explícito (retorna None)
def mostrar_status_sistema(status):
    """Apenas imprime um status, não precisa retornar nada."""
    print(f"Status do sistema: {status}")
    # Não há 'return' aqui, então implicitamente retorna None

valor_obtido_da_funcao = mostrar_status_sistema("OK")
print(f"O que essa função retornou? {valor_obtido_da_funcao}")
# Saída: Status do sistema: OK
# Saída: O que essa função retornou? None

# Exemplo 3: Função retornando múltiplos valores (como uma tupla)
def obter_informacoes_contato():
    """Simula obter nome e email de um contato."""
    nome_contato = "Bruno"
    email_contato = "bruno.c@email.com"
    # Retornamos nome e email separados por vírgula.
    # Python os empacota automaticamente em uma tupla.
    return nome_contato, email_contato

# Chamando a função e desempacotando os valores retornados em variáveis separadas
nome_capturado, email_capturado = obter_informacoes_contato()

print(f"Contato: {nome_capturado}, Email: {email_capturado}")
# Saída: Contato: Bruno, Email: bruno.c@email.com

# Você também pode capturar o retorno múltiplo como uma única tupla:
info_completa_contato = obter_informacoes_contato()
print(f"Info completa do contato (como tupla): {info_completa_contato}")
# Saída: Info completa do contato (como tupla): ('Bruno', 'bruno.c@email.com')

# Exemplo 4: Função retornando um valor baseado em condição
def verificar_elegibilidade_compra(idade):
    """Verifica se a idade permite fazer uma compra (>= 18)."""
    if idade >= 18:
        return "Pode comprar" # Retorna esta string se a condição for True
    else:
        return "Não pode comprar" # Retorna esta string se a condição for False

status_compra_joao = verificar_elegibilidade_compra(20)
print(f"João ({20} anos): {status_compra_joao}")
# Saída: João (20 anos): Pode comprar

status_compra_maria = verificar_elegibilidade_compra(16)
print(f"Maria ({16} anos): {status_compra_maria}")
# Saída: Maria (16 anos): Não pode comprar

# Exemplo 5: Função com parâmetro padrão retornando um valor
def gerar_etiqueta_produto(nome_produto, quantidade=1):
    """Cria uma etiqueta para um produto, usando 1 como quantidade padrão."""
    etiqueta = f"Produto: {nome_produto} | Quantidade: {quantidade}"
    return etiqueta # Retorna a string da etiqueta

# Usando a quantidade padrão (1)
etiqueta_maca = gerar_etiqueta_produto("Maçã")
print(etiqueta_maca)
# Saída: Produto: Maçã | Quantidade: 1

# Especificando a quantidade
etiqueta_banana = gerar_etiqueta_produto("Banana", 6)
print(etiqueta_banana)
# Saída: Produto: Banana | Quantidade: 6
```
## * `*args` e `**kwargs`
_Imagine que você está dando instruções para um assistente virtual (sua função em Python), mas nem sempre sabe *quantas* informações extras você vai querer dar a ele, ou se essas informações extras virão com "etiquetas" (nomes) ou não._

O `*args` (com um asterisco) é como uma "sacola de itens sem etiqueta". Tudo que você joga para o assistente *além* das instruções básicas, e que não tem nome (como `fazer_algo(item1, item2)`), vai parar organizado dentro dessa sacola, que em Python chamamos de **tupla** (uma lista arrumadinha que não muda depois de pronta). O assistente recebe essa tupla e pode processar todos os itens extras posicionais.

O `**kwargs` (com dois asteriscos) é como uma "caixa de itens com etiquetas". Tudo que você joga para o assistente dando um nome (como `configurar(cor="azul", tamanho="grande")`) vai parar organizado dentro dessa caixa, que em Python chamamos de **dicionário** (uma coleção onde cada item tem uma "etiqueta" única para encontrá-lo, como um mini-caderno de endereços). O assistente recebe esse dicionário e sabe exatamente qual item extra é qual pela etiqueta.

Juntos, `*args` e `**kwargs` tornam suas funções super flexíveis, capazes de receber um número variável de informações adicionais, estejam elas "etiquetadas" ou não!

**O que são e Por que Usar:**
`*args` e `**kwargs` são convenções de nomes (mas o que importa são os asteriscos `*` e `**`) usadas na definição de funções para permitir que elas aceitem um **número variável de argumentos**. Isso é útil quando você não sabe de antemão quantos inputs adicionais uma função pode receber em diferentes chamadas.

* **`*args`**: Captura um número variável de **argumentos posicionais** adicionais em uma **tupla**.
    * **Tupla:** Uma coleção ordenada de itens, similar a uma lista, mas **imutável** (seu conteúdo não pode ser alterado após a criação). É representada por parênteses `()`. Ex: `(1, 'banana', True)`.
* **`**kwargs`**: Captura um número variável de **argumentos nomeados** (na forma `chave=valor`) adicionais em um **dicionário**.
    * **Dicionário:** Uma coleção **não ordenada** de pares *chave-valor*. Cada valor é acessado usando sua chave. É representado por chaves `{}` com pares `chave: valor`. Ex: `{'cor': 'azul', 'idade': 10}`.

**Ordem na Definição da Função:**
Se você usar parâmetros obrigatórios, `*args` e `**kwargs` juntos, eles devem aparecer nesta ordem na definição da função:
1.  Parâmetros obrigatórios
2.  `*args`
3.  Parâmetros *apenas* nomeados (se houver, após `*args`)
4.  `**kwargs`

**Exemplos:**

```python
# Exemplo 1: Função usando *args (argumentos posicionais variáveis)
def listar_ingredientes(*ingredientes):
    """Recebe um número variável de ingredientes e os lista."""
    print("Ingredientes informados:")
    # 'ingredientes' dentro da função é uma tupla
    for item in ingredientes:
        print(f"- {item}")
    print("-" * 20)

listar_ingredientes("farinha", "açúcar", "ovos") # Passando 3 argumentos posicionais
# Saída:
# Ingredientes informados:
# - farinha
# - açúcar
# - ovos
# --------------------

listar_ingredientes("leite") # Passando apenas 1 argumento posicional
# Saída:
# Ingredientes informados:
# - leite
# --------------------

# Exemplo 2: Função usando **kwargs (argumentos nomeados variáveis)
def criar_cartao_visita(**informacoes):
    """Recebe informações variáveis (nomeadas) para um cartão de visita."""
    print("--- Cartão de Visita ---")
    # 'informacoes' dentro da função é um dicionário
    for chave, valor in informacoes.items():
        print(f"{chave.replace('_', ' ').title()}: {valor}") # Formata a chave
    print("------------------------")

criar_cartao_visita(nome="Ana Silva", profissao="Desenvolvedora", telefone="123-4567")
# Saída:
# --- Cartão de Visita ---
# Nome: Ana Silva
# Profissao: Desenvolvedora
# Telefone: 123-4567
# ------------------------

criar_cartao_visita(empresa="Tech Solutions") # Passando apenas 1 argumento nomeado
# Saída:
# --- Cartão de Visita ---
# Empresa: Tech Solutions
# ------------------------

# Exemplo 3: Combinando parâmetros obrigatórios com *args e **kwargs
def registrar_evento(tipo_evento, *participantes, local="Online", **detalhes_extras):
    """Registra um evento com tipo obrigatório, participantes variáveis e detalhes extras nomeados."""
    print(f"Registrando Evento: {tipo_evento.upper()}")
    print("Participantes:")
    if participantes:
        for p in participantes:
            print(f"- {p}")
    else:
        print("- Nenhum participante listado.")

    print(f"Local: {local}") # Usa o local padrão ou o passado como argumento nomeado 'local='

    print("Detalhes Extras:")
    if detalhes_extras:
        for chave, valor in detalhes_extras.items():
            print(f"{chave.replace('_', ' ').title()}: {valor}")
    else:
        print("- Nenhum detalhe extra.")
    print("=" * 30)

registrar_evento("Workshop Python", "Maria", "João", local="Sala 5", tema="Funções", nivel="Básico")
# Saída:
# Registrando Evento: WORKSHOP PYTHON
# Participantes:
# - Maria
# - João
# Local: Sala 5
# Detalhes Extras:
# Tema: Funções
# Nivel: Básico
# ==============================

registrar_evento("Reunião Geral") # Apenas parâmetro obrigatório
# Saída:
# Registrando Evento: REUNIÃO GERAL
# Participantes:
# - Nenhum participante listado.
# Local: Online
# Detalhes Extras:
# - Nenhum detalhe extra.
# ==============================
```

### Parâmetros Especiais

Por padrão, ao definir uma função em Python, os argumentos podem ser passados de duas maneiras:

1.  **Por Posição (Positional Arguments):** A ordem em que os argumentos são passados na chamada da função corresponde à ordem dos parâmetros na definição da função.
2.  **Por Nome (Keyword Arguments):** Os argumentos são passados explicitamente com o nome do parâmetro seguido por um sinal de igual (`=`) e o valor. A ordem não importa nesse caso.

No entanto, Python oferece uma sintaxe para restringir como os argumentos podem ser passados para uma função. Isso pode melhorar a legibilidade e o desempenho do código, pois força uma maneira específica de chamar a função, tornando a intenção mais clara na definição. Os parâmetros especiais são definidos usando os símbolos `/` e `*` na lista de parâmetros da função.

**Sintaxe:**

```python
def nome_da_funcao(posicional_apenas, /, posicional_ou_nome, *, nome_apenas):
    # Corpo da função
    pass
```

**Tipos de Parâmetros Especiais:**

1.  **Parâmetros Posicionais Apenas (Positional-Only Parameters):**
    * Definidos *antes* do símbolo `/` na lista de parâmetros.
    * Só podem ser passados por posição na chamada da função.
    * Se a definição for `def minha_funcao(a, b, /):`, ao chamar, você deve usar `minha_funcao(1, 2)`, e não `minha_funcao(a=1, b=2)`.
    * O símbolo `/` indica o fim dos parâmetros posicionais apenas. Se não houver nomes de parâmetros antes de `/`, significa que a função não aceita nenhum parâmetro posicional.

2.  **Parâmetros Posicionais ou por Nome (Positional or Keyword Arguments):**
    * São os parâmetros comuns que aparecem *entre* os parâmetros posicionais apenas (se houver) e os parâmetros nomeados apenas (se houver), ou antes de `/` se não houver parâmetros posicionais apenas, ou depois de `*` se não houver parâmetros nomeados apenas.
    * Podem ser passados tanto por posição quanto explicitamente pelo nome na chamada da função.
    * Exemplo: Em `def outra_funcao(x, y):`, você pode chamar como `outra_funcao(10, 20)` ou `outra_funcao(y=20, x=10)`.

3.  **Parâmetros Nomeados Apenas (Keyword-Only Arguments):**
    * Definidos *após* o símbolo `*` na lista de parâmetros.
    * Só podem ser passados explicitamente pelo nome na chamada da função.
    * Se a definição for `def funcao_especial(*, nome1, nome2):`, ao chamar, você deve usar `funcao_especial(nome1='valor1', nome2='valor2')`, e não `funcao_especial('valor1', 'valor2')`.
    * O símbolo `*` indica o início dos parâmetros nomeados apenas. Se não houver nomes de parâmetros após `*`, a função não aceita nenhum argumento nomeado.

**Exemplo Combinado:**

```python
def f(pos1, pos2, /, pos_ou_kwd, *, kwd1, kwd2):
    print(f"pos1: {pos1}, pos2: {pos2}, pos_ou_kwd: {pos_ou_kwd}, kwd1: {kwd1}, kwd2: {kwd2}")

# Chamadas válidas:
f(1, 2, 3, kwd1=4, kwd2=5)
f(1, 2, pos_ou_kwd=3, kwd1=4, kwd2=5)

# Chamadas inválidas (resultarão em TypeError):
# f(pos1=1, pos2=2, 3, kwd1=4, kwd2=5)  # pos1 e pos2 são posicionais apenas
# f(1, 2, 3, 4, 5)                     # kwd1 e kwd2 devem ser nomeados
# f(1, 2, 3, kwd2=5, 4)                # ordem de nomeados não importa, mas 4 não é nomeado
```

**Benefícios:**

- **Clareza na Assinatura da Função:** A definição da função já indica como os argumentos devem ser passados.
- **Melhor Legibilidade:** Ao chamar a função, a forma como os argumentos são passados é mais explícita.
- **Flexibilidade no Nome dos Parâmetros:** Você pode usar nomes de parâmetros mais descritivos sem se preocupar com conflitos na ordem dos argumentos posicionais na chamada.

Ao utilizar parâmetros especiais, o desenvolvedor que for usar sua função terá uma diretriz clara sobre como os argumentos devem ser fornecidos, o que contribui para um código mais robusto e fácil de entender.

//////////
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

///////////
---

## INTERPOLAÇÃO DE VARIÁVEIS:

## * `f-string`: Usada para inserir o valor de uma variável no meio de um texto.
_Em vez de ficar colando pedaços de texto com `+` ou usar métodos mais antigos, você simplesmente coloca a letra `f` antes das aspas da sua string e, onde quiser que o valor de uma variável apareça, você a coloca entre chaves `{}`_

_Elas suportam expressões complexas, formatação específica (como número de casas decimais), chamadas de métodos e são geralmente mais rápidas e legíveis que outros métodos de interpolação (`%` formatting ou `.format()`)._

**Exemplos:**

```
# Exemplo 1: Interpolação básica de variáveis
nome = "Alice"
idade = 30
mensagem = f"Olá, meu nome é {nome} e tenho {idade} anos."
print(mensagem)
# Saída: Olá, meu nome é Alice e tenho 30 anos.

# Exemplo 2: Usando expressões e formatação dentro das chaves
# É possível fazer cálculos ou usar métodos de formatação diretamente dentro das chaves {}.
preco_unitario = 19.99
quantidade = 3

# Imprime o preço unitário formatado para 2 casas decimais
print(f"Preço unitário: R${preco_unitario:.2f}")
# Saída: Preço unitário: R$19.99

# Calcula o total (preço * quantidade) e já formata o resultado para 2 casas decimais
print(f"Total da compra: R${(preco_unitario * quantidade):.2f}")
# Saída: Total da compra: R$59.97

# Exemplo 3: Chamando métodos diretamente na expressão
linguagem = "PYTHON"
# Chama o método .lower() na string 'linguagem' e insere o resultado.
print(f"Nome da linguagem em minúsculas: {linguagem.lower()}")
# Saída: Nome da linguagem em minúsculas: python

# Exemplo 4: Usando f-strings com múltiplas linhas (strings triplas)
# Strings triplas (com """ ou ''') permitem criar strings que quebram linha.
# Ao adicionar 'f' antes das aspas triplas, elas se tornam f-strings de múltiplas linhas.

# 1. Definimos as variáveis que serão usadas na string de múltiplas linhas.
nome_cliente = "Carlos" # Usando nome_cliente para não confundir com 'nome' do Exemplo 1
idade_cliente = 45
produto = "Tablet"
valor = 550.75

# 2. Criamos a f-string usando aspas triplas e 'f' antes.
# O texto dentro das aspas triplas, incluindo as quebras de linha, é parte da string.
# As variáveis e expressões entre {} serão substituídas por seus valores.
confirmacao_pedido = f"""
Prezado(a) {nome_cliente},

Confirmamos seu pedido do produto: {produto}.
O valor total é de R${valor:.2f}.
Seu pedido está sendo processado.

Agradecemos a sua compra!
"""
# A quebra de linha imediatamente após """ é incluída na string.

# 3. Imprimimos a string resultante formatada.
print(confirmacao_pedido)

# Saída:
#
# Prezado(a) Carlos,
#
# Confirmamos seu pedido do produto: Tablet.
# O valor total é de R$550.75.
# Seu pedido está sendo processado.
#
# Agradecemos a sua compra!
```

## * Fatiamento de strings
_Imagine sua string como um delicioso "bolo" de letras, onde cada letra é uma fatia individual com uma posição (o índice). Fatiar a string é como pedir um "pedaço" desse bolo, uma porção específica das fatias. Você especifica qual a **primeira fatia** que quer (o `start`, que *inclui* aquela fatia), qual a **última fatia** que *não* quer (o `stop`, que *exclui* aquela fatia final!), e, opcionalmente, de quantas em quantas fatias você quer pular (`step`). O Python te entrega um novo "mini-bolo" (uma nova string) contendo apenas as fatias que você pediu, na ordem certinha ou até de trás para frente se usar um passo negativo! É uma forma super flexível e eficiente de trabalhar com partes do seu texto._

**Sintaxe:** A sintaxe é feita utilizando colchetes `[]` após a string, seguindo o formato: `[start : stop : step]`.

* `start`: O índice do primeiro caractere a ser incluído na fatia (o início do pedaço). Se omitido, o fatiamento começa do índice 0.
* `stop`: O índice do primeiro caractere a *não* ser incluído na fatia (o fim do pedaço, que é *exclusivo*). Se omitido, o fatiamento vai até o final da string.
* `step`: O passo ou "salto" entre os índices (de quanto em quanto pular). O padrão é `1`. Se for negativo, percorre a string de trás para frente.

**Exemplos:** 

```
# Definindo a string 
nome = "Guilherme Arthur de Carvalho"
print(f"String original: '{nome}'")
# Saída: String original: Guilherme Arthur de Carvalho

# Exemplo 1: Acessando um único caractere pelo índice
# Indices começam em 0. nome[0] é o primeiro caractere.
print(f"Primeira letra (nome[0]): '{nome[0]}'")
# Saída: Primeira letra (nome[0]): 'G'

# Exemplo 2: Fatiamento básico [start : stop]
# Pega do índice 'start' (incluso) até 'stop' (excluso).
print(f"Primeiro nome (nome[0:9]): '{nome[0:9]}'")
# Saída: Primeiro nome (nome[0:9]): 'Guilherme'

# Exemplo 3: Fatiamento do início até o stop [ : stop]
# Quando start é omitido, começa do índice 0.
print(f"Do início até o nono caractere (nome[:9]): '{nome[:9]}'")
# Saída: Do início até o nono caractere (nome[:9]): 'Guilherme'

# Exemplo 4: Fatiamento do start até o final [start : ]
# Quando stop é omitido, vai até o último caractere.
print(f"Do décimo caractere até o final (nome[10:]): '{nome[10:]}'")
# Saída: Do décimo caractere até o final (nome[10:]): 'Arthur de Carvalho'

# Exemplo 5: Fatiamento com start e stop específicos [start : stop]
# Pega do índice 10 (inclusive) até o 16 (exclusivo).
print(f"Parte do meio (nome[10:16]): '{nome[10:16]}'")
# Saída: Parte do meio (nome[10:16]): 'Arthur'

# Exemplo 6: Fatiamento com passo [start : stop : step]
# Do início ao fim (omitindo start e stop), pulando de 2 em 2.
print(f"Pulando de 2 em 2 (nome[::2]): '{nome[::2]}'")
# Saída: Pulando de 2 em 2 (nome[::2]): 'Gilem Arhrd avlo'

# Exemplo 7: Fatiamento reverso [ : : -1]
# Um step negativo (-1) percorre a string de trás para frente.
print(f"String invertida (nome[::-1]): '{nome[::-1]}'")
# Saída: String invertida (nome[::-1]): 'ohlavraC ed ruhtrA emrehliuG'

# Exemplo 8: Usando índices negativos
# Índices negativos contam a partir do final da string (-1 é o último caractere).
print(f"Último caractere (nome[-1]): '{nome[-1]}'")
# Saída: Último caractere (nome[-1]): 'o'

# Exemplo 9: Fatiamento usando índice negativo no start
# Pega da 8ª posição contando do final, até o final da string.
print(f"Último nome (nome[-8:]): '{nome[-8:]}'")
# Saída: Último nome (nome[-8:]): 'Carvalho'

# Exemplo 10: Fatiamento com índices negativos e step negativo
# Pega do penúltimo caractere (-2) até o 4º caractere (-26), pulando de -1 em -1.
print(f"Penúltimo até o 4º caractere invertido (nome[-2:-26:-1]): '{nome[-2:-26:-1]}'")
# Saída: Penúltimo até o 4º caractere invertido (nome[-2:-26:-1]): 'ohlavraC ed ruhtrA emrehliu'
```
//////////
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

## * `continue`: Usado para pular o restante do ciclo atual de uma iteração (em loops `for` ou `while`) e ir para a próxima iteração
_Se o `break` é o botão de "parada total" para um loop, o `continue` é como o botão de "pular esta volta" ou "próximo item!". Quando seu loop (`for` ou `while`) está no meio de uma iteração (fazendo os passos para um item ou um ciclo) e encontra um `continue`, ele diz: "Ok, esquece o resto do que eu ia fazer NESTA volta! Não termine este ciclo de iteração. Vá direto para o começo da PRÓXIMA volta do loop!" Ele ignora o código que viria depois dele naquele ciclo e segue para a próxima iteração (no `for` vai para o próximo item, no `while` volta para reavaliar a condição e, se verdadeira, começa o próximo ciclo). É ótimo quando você quer pular o processamento de itens específicos ou pular uma parte da lógica para uma condição particular._

**Exemplos:**
```
# Exemplo 1: Usando continue em um loop for para pular a impressão de um número
print("--- Usando continue em um loop for ---")
numeros = [1, 2, 3, 4, 5, 6]

print("Imprimindo números, mas pulando o 3:")
for numero in numeros:
    if numero == 3:
        print(f"Pulando a impressão do número {numero} nesta iteração...")
        continue # Pula o restante do código para esta iteração (não executa o print abaixo)
    print(f"Processando e imprimindo: {numero}")

print("Execução continua após o loop for.")
# Saída esperada:
# --- Usando continue em um loop for ---
# Imprimindo números, mas pulando o 3:
# Processando e imprimindo: 1
# Processando e imprimindo: 2
# Pulando a impressão do número 3 nesta iteração...
# Processando e imprimindo: 4
# Processando e imprimindo: 5
# Processando e imprimindo: 6
# Execução continua após o loop for.

# Exemplo 2: Usando continue em um loop while para pular uma ação para um número específico
print("\n--- Usando continue em um loop while ---")
contador = 0

print("Contando de 0 a 5, mas pulando a 'ação principal' para o número 2:")
while contador < 6:
    if contador == 2:
        print(f"Número {contador} encontrado. Pulando a ação principal para ele.")
        contador += 1 # CRUCIAL: Atualiza o contador ANTES do continue para evitar loop infinito
        continue # Pula o restante do loop para esta iteração

    print(f"Ação principal para o número: {contador}")
    contador += 1 # Atualiza o contador (para as iterações que não usam continue)

print("Execução continua após o loop while.")
# Saída esperada:
# --- Usando continue em um loop while ---
# Contando de 0 a 5, mas pulando a 'ação principal' para o número 2:
# Ação principal para o número: 0
# Ação principal para o número: 1
# Número 2 encontrado. Pulando a ação principal para ele.
# Ação principal para o número: 3
# Ação principal para o número: 4
# Ação principal para o número: 5
# Execução continua após o loop while.

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

