# Resumo dos Materiais Didáticos - Módulo 8

Este módulo introduz uma das estruturas mais importantes da programação: a repetição. 

A ideia central é simples: em vez de escrever o mesmo código várias vezes, você usa um laço para executar uma ação automaticamente enquanto houver elementos para percorrer ou enquanto uma condição for atendida.

O Python oferece o comando `for`, que permite repetir instruções de forma organizada, eficiente e legível. Esse conceito é essencial porque grande parte dos programas trabalha com listas, textos, dados e processos que precisam ser repetidos várias vezes.

---

## Conteúdo explicado de forma geral

O módulo 8 foi dividido em partes relacionadas ao uso do `for`:

1. Estrutura de repetição `for` com `range()`;
2. Uso do `for` para percorrer listas e textos;
3. Combinação de `for` com `if` para analisar dados;
4. Uso de `enumerate()` para percorrer itens e índices ao mesmo tempo;
5. Escolha entre as diferentes formas de utilizar o `for`;
6. Uso de `for` dentro de outro `for`;
7. Interrupção e controle do laço com `break` e `continue`;
8. Exercícios de fixação com listas, análises e cálculos.

Essas etapas mostram como o computador consegue repetir tarefas automaticamente, acessar itens de uma coleção e tomar decisões dentro do mesmo processo.

Isso é muito útil em situações reais, como:
- processar uma lista de produtos;
- analisar vendas de vários funcionários;
- percorrer nomes de clientes;
- verificar texto letra por letra;
- automatizar relatórios e cálculos repetitivos.

Em outras palavras, o módulo ensina a lógica de repetição, que é a base para automação, análise de dados, processamento de listas e criação de programas mais inteligentes.

---

## 1) Estrutura de Repetição: for

O primeiro assunto do módulo ensina a sintaxe básica do `for`:

```python
for i in range(n):
    repetir código n vezes
```

O `range(n)` representa uma sequência numérica, como:

```python
range(5)
```

que, na prática, funciona como:

```python
[0, 1, 2, 3, 4]
```

Isso significa que o código dentro do laço será executado 5 vezes, com `i` assumindo cada valor da sequência.

Exemplo:

```python
for i in range(5):
    print(i)
```

Resultado:

```python
0
1
2
3
4
```

Essa parte do conteúdo é importante porque mostra o conceito central de repetição: controlar quantas vezes um bloco de código será executado.

Além disso, a aula apresenta um exemplo prático de produção de produtos em uma fábrica, mostrando como usar `for` para exibir a quantidade produzida de cada item:

```python
produtos = ['coca', 'pepsi', 'guarana', 'sprite', 'fanta']
producao = [15000, 12000, 13000, 5000, 250]

for i in range(len(produtos)):
    print('{} unidades produzidas de {}'.format(producao[i], produtos[i]))
```

Esse tipo de problema é muito comum na programação: você tem dados em duas listas e precisa relacioná-los por posição.

---

## 2) For "each" - Percorrendo itens de uma lista

A segunda parte do módulo mostra uma forma mais natural de usar o `for` em Python: percorrer cada item de uma lista diretamente.

Estrutura:

```python
for item in lista:
    print(item)
```

Essa sintaxe é muito mais simples do que usar `range()` quando você quer trabalhar com os valores da lista e não com os índices.

Exemplo:

```python
produtos = ['coca', 'pepsi', 'guarana', 'sprite', 'fanta']

for produto in produtos:
    print(produto)
```

Aqui, o Python percorre cada elemento da lista e atribui esse valor à variável `produto` em cada repetição.

Essa ideia também pode ser aplicada a strings:

```python
texto = 'lira@gmail.com'

for ch in texto:
    print(ch)
```

Nesse caso, o laço percorre cada caractere da string e imprime um por um.

Essa aula mostra que o `for` não serve apenas para números, mas também para percorrer:
- listas;
- textos;
- coleções de dados;
- informações vindas do usuário.

Ou seja, o `for` passa a ser a estrutura principal para automatizar a leitura e o processamento de dados.

---

## 3) For + If - Condição dentro do laço

A parte mais importante do módulo é a combinação de `for` com `if`, porque isso permite analisar dados e tomar decisões automaticamente.

Estrutura:

```python
for item in lista:
    if condicao:
        faça alguma coisa
    else:
        outra coisa
```

Esse recurso é muito importante porque une duas ideias fundamentais da programação:
- repetir ações;
- verificar condições.

No exemplo da aula, a empresa quer saber quantos funcionários bateram a meta de vendas, que é de 1000 reais.

```python
vendas = [1200, 300, 800, 1500, 1900, 2750, 400, 20, 23, 70, 90, 80, 1100, 999, 900, 880, 870, 50, 1111, 120, 300, 450, 800]
meta = 1000
qtde_bateu_meta = 0

for venda in vendas:
    if venda >= meta:
        qtde_bateu_meta += 1

qtde_funcionarios = len(vendas)
print('O percentual de pessoas que bateram a meta foi de {:.0%}'.format(qtde_bateu_meta / qtde_funcionarios))
print('{} funcionários bateram a meta'.format(qtde_bateu_meta))
```

O que acontece ali?
- o programa percorre cada valor da lista;
- compara cada venda com a meta;
- se a venda for maior ou igual a 1000, conta mais um funcionário;
- ao final, calcula o percentual e imprime o resultado.

Essa é a lógica que aparece muito em programas reais:
- verificar quem passou de um limite;
- identificar itens acima de um valor;
- separar dados válidos e inválidos;
- filtrar informações para gerar relatórios.

---

## 4) Enumerate - item e índice ao mesmo tempo

Quando é necessário percorrer uma lista e também saber a posição de cada item, o Python oferece a função `enumerate()`.

Estrutura:

```python
for i, item in enumerate(lista):
    resto do código
```

Em cada repetição, `i` recebe o índice do item e `item` recebe o valor correspondente. Assim, o código fica mais direto do que controlar os índices manualmente com `range(len(lista))`.

Exemplo com uma lista de funcionários:

```python
funcionarios = ['Maria', 'José', 'Antônio']

for i, funcionario in enumerate(funcionarios):
    print('{} é o funcionário {}'.format(i, funcionario))
```

O `enumerate()` também é útil quando duas listas possuem informações relacionadas pela mesma posição. No exemplo abaixo, o programa associa cada produto ao seu preço e calcula o preço com imposto:

```python
produtos = ['iphone', 'ipad', 'airpod', 'macbook']
precos = [7000, 10000, 2500, 14000]

for i, preco in enumerate(precos):
    preco = preco * 1.1
    produto = produtos[i]
    print(produto, preco)
```

Outro exemplo prático é identificar produtos abaixo do nível mínimo de estoque:

```python
nivel_minimo = 50

for i, qtde in enumerate(estoque):
    if qtde < nivel_minimo:
        print('{} está abaixo do nível mínimo. Temos apenas {} unidades'.format(produtos[i], qtde))
```

### Como escolher cada forma de `for`

- Use `for item in lista` quando só precisa do valor de cada item;
- use `for i in range(len(lista))` quando precisa controlar os índices ou relacionar posições de listas;
- use `for i, item in enumerate(lista)` quando precisa do índice e do valor juntos, de forma mais clara.

Essa comparação ajuda a escolher a estrutura mais simples para cada situação e evita criar controles manuais desnecessários.

---

## 5) For dentro de For - Laços aninhados

Quando uma lista contém outras listas, pode ser necessário percorrer primeiro a lista externa e depois cada lista interna. Para isso, usamos um `for` dentro de outro `for`:

```python
for item in lista:
    for item2 in item:
        faça alguma coisa
```

O material aplica essa estrutura ao controle de estoque de várias fábricas. Cada fábrica possui uma lista com a quantidade de produtos em estoque, e o programa verifica se existe algum produto abaixo do nível mínimo:

```python
for i, lista in enumerate(estoque):
    for qtde in lista:
        if qtde < nivel_minimo:
            if fabricas[i] not in fabricas_abaixo_nivel:
                fabricas_abaixo_nivel.append(fabricas[i])
```

Nesse caso, o primeiro laço identifica a fábrica e o segundo analisa cada quantidade de estoque. A verificação evita adicionar a mesma fábrica mais de uma vez à lista de resultados.

Esse padrão é útil para trabalhar com:
- listas de listas;
- tabelas e matrizes;
- dados separados por empresa, turma ou categoria;
- estoques de várias fábricas;
- qualquer coleção que possua níveis ou grupos internos.

---

## 6) Break e Continue - Controlando a repetição

Além de executar um laço, o Python permite controlar o seu fluxo com duas instruções:

- `break`: interrompe e finaliza o `for` imediatamente;
- `continue`: interrompe apenas a repetição atual e passa para o próximo item.

O `break` pode ser usado para encerrar uma verificação assim que uma condição for encontrada. No exemplo do material, a loja só recebe um bônus se todas as vendas estiverem acima da meta. Ao encontrar uma venda abaixo da meta, o programa informa que não há bônus e encerra o laço:

```python
for venda in vendas:
    if venda < meta:
        print('A loja não ganhou bônus')
        break
```

O `continue` é útil quando determinados itens devem ser ignorados, sem interromper o processamento dos demais. Para exibir apenas as vendas que atingiram a meta, o programa pula as vendas abaixo dela:

```python
for venda in vendas:
    if venda < meta:
        continue
    print(venda)
```

Assim, `break` encerra todo o laço, enquanto `continue` apenas pula a iteração atual.

---

## 7) Exercícios de aplicação

Os exercícios do módulo colocam os laços em situações próximas de problemas reais. Entre as propostas estão:

### Cadastro de hóspedes

O programa pergunta quantas pessoas ficarão no quarto e usa `for` com `range()` para solicitar o nome e o CPF de cada pessoa. Ao final, cria uma lista de registros, em que cada item contém o nome e o CPF do hóspede.

### Análise de vendas

Uma lista com vendedores e valores vendidos é percorrida para identificar quem atingiu a meta. Em outro exercício, o programa calcula o percentual de vendedores que atingiram a meta e encontra o vendedor com maior volume de vendas.

### Comparação de vendas entre anos

Com `enumerate()`, o programa relaciona produtos às vendas de 2019 e 2020, identifica os produtos que cresceram e calcula o percentual de crescimento.

### Exercícios extras com listas

Os materiais também propõem problemas que combinam laços, índices, condições e cálculos, como:
- exibir vendas e calcular a média de vendedores;
- calcular a média de cada aluno e contar quantos atingiram a média mínima;
- analisar funcionários com base em idade, salário e média salarial;
- identificar meses com temperatura acima da média nacional;
- calcular abonos, total gasto, quantidade de funcionários e maior abono;
- comparar consumo de veículos, litros necessários e custo de uma viagem;
- contar vendedores em faixas salariais de acordo com suas comissões.

Esses exercícios reforçam que o `for` pode ser combinado com listas auxiliares, acumuladores, contadores, `sum()`, `len()`, comparações e formatação de resultados.

---

## Conceitos-chave aprendidos no módulo

O módulo 8 trabalha com oito ideias centrais:

### 1. Repetição
Você usa `for` para executar o mesmo bloco de código várias vezes.

### 2. Iteração
Você percorre elementos de uma lista, sequência ou texto.

### 3. Condicional dentro do laço
Você usa `if` para verificar uma condição em cada item.

### 4. Automação de análise de dados
Você consegue processar muitos dados sem repetir manualmente o código.

### 5. Índices com `enumerate()`
Você consegue acessar o índice e o valor de cada item simultaneamente, facilitando o trabalho com listas relacionadas.

### 6. Laços aninhados
Você pode percorrer estruturas com listas dentro de listas usando um `for` dentro de outro `for`.

### 7. Controle do fluxo
Você usa `break` para encerrar um laço e `continue` para pular apenas a iteração atual.

### 8. Processamento com acumuladores e contadores
Você pode somar valores, contar ocorrências, criar listas filtradas e calcular médias e percentuais durante a repetição.

---

## Aplicações práticas

A lógica ensinada no módulo é usada em muitos contextos, como:
- controle de estoque;
- relatórios de vendas;
- análise de notas;
- processamento de nomes e e-mails;
- validação de dados;
- aplicação de impostos e outros cálculos sobre produtos;
- identificação de produtos abaixo do estoque mínimo;
- análise de estoques organizados por fábrica;
- cadastro de várias pessoas em um único quarto;
- comparação de vendas entre anos;
- cálculo de médias, percentuais, comissões e abonos;
- comparação de consumo e custo de veículos;
- automatização de tarefas repetitivas.

Em programação, esse tipo de estrutura é muito importante porque permite trabalhar com grandes quantidades de informação de forma organizada.

---

## Conclusão

O módulo 8 é essencial porque introduz a ideia de que um programa pode repetir ações automaticamente e analisar dados de maneira inteligente.

A partir daqui, o aluno começa a entender a lógica mais realista da programação:
- percorrer dados;
- escolher entre percorrer apenas os itens, usar índices ou obter os dois com `enumerate()`;
- percorrer listas de listas com laços aninhados;
- interromper ou pular partes da repetição com `break` e `continue`;
- tomar decisões;
- processar listas;
- acumular resultados e gerar listas filtradas;
- responder perguntas com base em informações.

Essa base é fundamental para os próximos módulos, porque tudo o que vier depois vai depender da compreensão de laços, condições e processamento de dados.
