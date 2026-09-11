# Resumo dos Materiais Didáticos - Módulo 9

O Módulo 9 apresenta a estrutura de repetição `while`, usada quando a quantidade de repetições não é conhecida previamente. Diferentemente do `for`, que normalmente percorre uma sequência ou repete um bloco por uma quantidade definida, o `while` continua executando enquanto uma condição for verdadeira.

Esse tipo de laço é útil em programas que dependem de uma ação do usuário, de uma entrada que pode acontecer várias vezes ou de uma condição que muda durante a execução.

---

## 1) Estrutura do `while`

A sintaxe básica é:

```python
while condicao:
    repetir código
```

O Python verifica a condição antes de cada repetição. Enquanto ela for verdadeira, o bloco indentado é executado. Quando a condição se torna falsa, o programa sai do laço e continua na próxima instrução.

Exemplo conceitual:

```python
while condicao:
    faça alguma coisa
```

Por isso, todo `while` precisa ter uma condição que possa mudar durante a execução ou que possa ser alterada por uma ação externa, como uma entrada do usuário.

---

## 2) Cadastro de vendas com entrada do usuário

O material apresenta um sistema simples de registro de vendas. O usuário informa o nome de um produto, que é adicionado a uma lista. O programa continua perguntando por novos produtos até que o usuário pressione `Enter` sem digitar nada.

```python
venda = input('Registre um produto. Para encerrar, pressione Enter: ')
vendas = []

while venda != '':
    vendas.append(venda)
    venda = input('Registre um produto. Para encerrar, pressione Enter: ')

print('Registro finalizado. As vendas foram: {}'.format(vendas))
```

Nesse exemplo:

- `venda != ''` é a condição de repetição;
- cada produto é adicionado com `append()`;
- a variável `venda` recebe uma nova entrada ao final de cada repetição;
- uma entrada vazia faz a condição se tornar falsa;
- a lista final contém todos os produtos registrados.

Esse padrão é conhecido como repetição controlada por sentinela: um valor especial, nesse caso uma string vazia, sinaliza que o usuário deseja encerrar o cadastro.

Esse tipo de lógica aparece em cadastros, menus, formulários e automações que precisam continuar disponíveis até uma ação de encerramento.

---

## 3) Cuidado com o loop infinito

Um loop infinito acontece quando a condição do `while` continua verdadeira para sempre. Isso pode travar o programa ou impedir que ele avance para as próximas instruções.

Um erro comum é esquecer de alterar a variável usada na condição:

```python
i = 0

while vendas[i] > meta:
    print(vendedores[i])
```

Nesse caso, o `while` não altera automaticamente o valor de `i`. Se `vendas[i] > meta` for verdadeiro, o programa continuará consultando o mesmo item e executando o bloco indefinidamente.

Para avançar pela lista, é necessário atualizar o índice dentro do laço:

```python
i = 0

while i < len(vendas) and vendas[i] > meta:
    print('{} bateu a meta. Vendas: {}'.format(vendedores[i], vendas[i]))
    i += 1
```

A condição `i < len(vendas)` também protege o acesso à lista e evita tentar consultar uma posição inexistente. O laço termina quando uma venda não atinge a meta ou quando todos os itens foram percorridos.

Ao utilizar `while`, sempre verifique:

- qual variável controla a repetição;
- em que ponto essa variável é alterada;
- qual situação torna a condição falsa;
- se o índice permanece dentro dos limites da lista;
- se existe uma forma clara de o usuário ou o programa encerrar o processo.

---

## `for` e `while`: quando usar cada um

- Use `for` quando você deseja percorrer uma sequência ou repetir um bloco com uma quantidade conhecida de vezes;
- use `while` quando a repetição depende de uma condição e a quantidade de repetições pode variar;
- use `while` para entradas repetidas até uma sentinela, como uma string vazia;
- use `for` quando o objetivo principal for visitar cada item de uma lista;
- ao usar `while` com listas, controle manualmente o índice e a condição de parada.

O `while` oferece mais controle sobre o momento de continuar ou parar, mas exige mais atenção para evitar condições que nunca terminam.

---

## Conceitos-chave aprendidos no módulo

1. **Condição de repetição:** o bloco é executado enquanto a condição for verdadeira.
2. **Repetição indeterminada:** a quantidade de execuções pode variar conforme os dados e as entradas.
3. **Sentinela:** um valor especial pode indicar o encerramento do processo.
4. **Atualização da variável de controle:** a condição precisa se aproximar do fim em algum momento.
5. **Loop infinito:** ocorre quando a condição nunca se torna falsa.
6. **Controle de índices:** ao percorrer listas com `while`, é necessário atualizar o índice e respeitar seus limites.

---

## Aplicações práticas

A estrutura `while` pode ser utilizada em:

- cadastro de produtos ou pessoas;
- menus de programas;
- leitura de entradas até o usuário escolher sair;
- validação de dados até receber uma informação válida;
- processamento de listas com uma condição de parada;
- automações que permanecem ativas enquanto uma tarefa não for concluída.

---

## Conclusão

O Módulo 9 mostra como repetir instruções com base em uma condição, permitindo criar programas mais interativos e flexíveis. O aluno aprende a controlar entradas sucessivas, armazenar resultados e encerrar um processo por meio de uma condição definida.

Também fica evidente que o `while` exige cuidado: a variável de controle deve ser atualizada e a condição precisa ter uma possibilidade real de se tornar falsa. Com esse cuidado, o `while` se torna uma ferramenta importante para construir cadastros, menus, validações e automações.