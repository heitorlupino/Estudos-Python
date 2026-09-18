# Resumo dos Materiais Didáticos - Módulo 11

O Módulo 11 apresenta os dicionários em Python, uma das estruturas mais importantes da linguagem. Diferentemente de listas e tuplas, que organizam dados por posição, os dicionários armazenam informações em pares de chave e valor.

Essa estrutura permite acessar dados por meio de uma identificação significativa, em vez de um índice numérico. Por isso, os dicionários são altamente utilizados em programas que precisam organizar informações como cadastro de clientes, produtos, notas, configurações e registros diversos.

---

## 1) O que é um dicionário?

Um dicionário é uma coleção que armazena dados em formato de chave: valor.

```python
cliente = {'nome': 'Ana', 'idade': 28, 'cidade': 'Recife'}
```

Nesse exemplo:

- `'nome'` é a chave;
- `'Ana'` é o valor associado;
- `'idade'` é outra chave;
- `28` é o valor correspondente.

As chaves costumam ser strings, mas podem ser outros tipos imutáveis, como inteiros e tuplas. Já os valores podem ser de qualquer tipo, incluindo listas, dicionários e outros objetos.

---

## 2) Como criar um dicionário

A criação de um dicionário pode ser feita com chaves `{}`:

```python
pessoa = {'nome': 'João', 'profissao': 'Programador'}
```

Também é possível criar um dicionário vazio:

```python
dados = {}
```

E depois adicionar itens:

```python
dados['idade'] = 25
dados['cidade'] = 'São Paulo'
```

Essa forma é muito comum para montar estruturas dinamicamente durante a execução do programa.

---

## 3) Acessando itens do dicionário

Para acessar o valor de uma chave, usamos o nome da chave entre colchetes:

```python
cliente = {'nome': 'Maria', 'idade': 30}

print(cliente['nome'])  # Maria
print(cliente['idade'])  # 30
```

Se a chave não existir, Python gera um erro `KeyError`.

Para evitar esse erro, pode-se usar o método `get()`:

```python
print(cliente.get('email', 'Não informado'))
```

O `get()` tenta buscar a chave. Se ela não existir, retorna um valor padrão informado pelo programador.

---

## 4) Verificando se uma chave existe

Antes de acessar uma chave com `[]`, é útil validar se ela existe:

```python
if 'nome' in cliente:
    print(cliente['nome'])
else:
    print('Chave não encontrada')
```

Também é possível verificar a presença de valores ou chaves usando operadores de pertencimento:

```python
print('nome' in cliente)      # True
print('Maria' in cliente.values())  # True
```

Essa abordagem é muito importante para evitar erros e preparar o código para entradas inesperadas.

---

## 5) Alterando e adicionando itens

Os valores de um dicionário podem ser alterados facilmente:

```python
cliente['idade'] = 31
```

Para adicionar uma nova chave:

```python
cliente['telefone'] = '11999999999'
```

Se a chave já existir, a nova atribuição apenas substitui o valor antigo.

---

## 6) Métodos úteis de dicionários

Os dicionários possuem vários métodos que facilitam a manipulação dos dados.

### `keys()`

Retorna todas as chaves do dicionário:

```python
print(cliente.keys())
```

### `values()`

Retorna todos os valores:

```python
print(cliente.values())
```

### `items()`

Retorna pares de chave e valor:

```python
print(cliente.items())
```

### `update()`

Atualiza o dicionário com novos pares:

```python
cliente.update({'cidade': 'Curitiba'})
```

### `pop()`

Remove uma chave e retorna o valor correspondente:

```python
idade = cliente.pop('idade')
```

### `del`

Remove uma chave diretamente:

```python
del cliente['cidade']
```

### `clear()`

Remove todos os itens do dicionário:

```python
cliente.clear()
```

Esses métodos ajudam a organizar, atualizar e limpar dados de forma eficiente.

---

## 7) Percorrendo dicionários

É possível percorrer chaves, valores e itens do dicionário com laços.

### Percorrendo as chaves:

```python
for chave in cliente:
    print(chave)
```

### Percorrendo os valores:

```python
for valor in cliente.values():
    print(valor)
```

### Percorrendo pares:

```python
for chave, valor in cliente.items():
    print(chave, valor)
```

Esse tipo de estrutura é muito útil para gerar relatórios, consultar registros e processar dados de forma organizada.

---

## 8) Dicionários aninhados

Um dicionário pode conter outros dicionários dentro dele, formando estruturas mais complexas:

```python
alunos = {
    'aluno1': {'nome': 'Pedro', 'nota': 9.5},
    'aluno2': {'nome': 'Luiza', 'nota': 8.7}
}
```

Para acessar uma informação interna:

```python
print(alunos['aluno1']['nome'])  # Pedro
```

Essa técnica é útil para representar grupos, cadastros e estruturas hierárquicas.

---

## 9) Diferença entre lista, tupla e dicionário

- Lista: guarda dados em ordem, acessados por índice;
- Tupla: guarda dados em ordem, imutável;
- Dicionário: guarda dados por chave e valor, acessados por nomes identificadores.

Exemplo:

```python
lista = ['Ana', 28]
# acessa pela posição
print(lista[0])

tupla = ('Ana', 28)
# acessa pela posição
print(tupla[0])

dicionario = {'nome': 'Ana', 'idade': 28}
# acessa pela chave
print(dicionario['nome'])
```

O dicionário é especialmente útil quando o significado dos dados importa mais do que a posição física na estrutura.

---

## 10) Aplicações práticas

Dicionários são usados em inúmeras situações, como:

- cadastro de clientes;
- armazenamento de produtos e preços;
- listas de alunos com notas;
- configurações de programas;
- organização de dados em APIs;
- controle de estoque;
- informações de usuário em aplicações web e desktop.

Exemplo de cadastro:

```python
produtos = {
    'mouse': 50,
    'teclado': 120,
    'monitor': 450
}

print(produtos['teclado'])  # 120
```

Dicionários permitem localizar rapidamente um item por uma identificação clara, em vez de percorrer uma lista inteira.

---

## 11) Conceitos-chave aprendidos no módulo

1. Dicionário armazena dados em pares de chave e valor.
2. A chave identifica o valor e pode ser acessada diretamente.
3. O método `get()` facilita o acesso seguro.
4. O operador `in` verifica se uma chave existe.
5. Métodos como `keys()`, `values()`, `items()`, `update()`, `pop()` e `clear()` são essenciais.
6. É possível percorrer dicionários com laços.
7. Dicionários aninhados permitem organizar estruturas mais complexas.
8. A principal vantagem do dicionário é a busca rápida e intuitiva por identificadores.

---

## Conclusão

O Módulo 11 mostra que os dicionários são uma estrutura essencial para manipular dados de maneira eficiente e organizada. Eles tornam o código mais legível e permitem acessar informações por nome, em vez de depender de índices numéricos.

Com o conhecimento sobre chaves, valores, métodos e percursos, o aluno passa a criar programas mais sofisticados, como cadastros, sistemas de controle, registros de dados e aplicações que exigem organização lógica. Os dicionários são uma das bases da programação em Python e aparecem em praticamente todos os projetos de nível intermediário.
