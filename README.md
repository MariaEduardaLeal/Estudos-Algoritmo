# Listas Lineares Sequenciais

As listas lineares sequenciais são estruturas de dados que organizam elementos de forma contígua na memória, mantendo a ordem lógica dos elementos igual à ordem física em que estão armazenados. Nesse tipo de lista, os elementos são acessados de maneira sequencial, facilitando operações como inserção, remoção e busca.

## Características das Listas Lineares Sequenciais:

- **Armazenamento Contíguo:** Os elementos são armazenados de forma contígua na memória, facilitando o acesso sequencial.
  
- **Ordem Lógica e Física:** A ordem lógica dos elementos na lista é a mesma ordem física em que estão armazenados na memória.
  
- **Acesso Sequencial:** Os elementos são acessados de forma sequencial, percorrendo a lista de um elemento para o próximo.

## Operações em Listas Lineares Sequenciais:

### Inserção de Elementos:

# Inserção de Dados em uma Lista Sequencial

Para inserir novos dados em uma lista sequencial, é necessário seguir alguns passos para garantir que os elementos existentes sejam deslocados adequadamente para abrir espaço para o novo dado. Aqui está uma explicação detalhada de como mover elementos para inserir novos dados em uma lista sequencial:

## Identificação do Local de Inserção:
Antes de inserir o novo dado, é crucial identificar o local exato na lista onde ele será inserido. Isso pode ser determinado com base na posição desejada na lista ou em critérios específicos, como ordenação.

## Deslocamento dos Elementos:
Após identificar o local de inserção, os elementos que estão após esse ponto precisam ser deslocados para abrir espaço para o novo dado. Os elementos são movidos para posições subsequentes na lista, garantindo que nenhum dado seja perdido durante o processo.

## Inserção do Novo Dado:
Uma vez que os elementos foram deslocados adequadamente, o novo dado pode ser inserido na posição determinada. O novo dado é colocado no local correto na lista, respeitando a ordem dos elementos e mantendo a integridade da estrutura da lista.

## Atualização do Tamanho da Lista:
Após a inserção do novo dado, o tamanho da lista deve ser atualizado para refletir a adição do elemento. O contador de elementos na lista é incrementado para refletir a inclusão do novo dado.

## Verificação de Limites:
Durante o processo de inserção e deslocamento de elementos, é importante verificar os limites da lista para evitar erros de acesso a posições inválidas. Garantir que os deslocamentos e inserções estejam dentro dos limites da lista é essencial para manter a integridade dos dados.

### Inserção de Elemento em uma Lista Sequencial em C

```c
#include <stdio.h>

#define MAX_SIZE 10

int main() {
    int lista_sequencial[MAX_SIZE] = {1, 2, 3, 4, 5};
    int novo_elemento = 6;
    int tamanho = 5; // Tamanho atual da lista

    if (tamanho < MAX_SIZE) {
        lista_sequencial[tamanho] = novo_elemento;
        tamanho++;

        printf("Lista após adicionar elemento: ");
        for (int i = 0; i < tamanho; i++) {
            printf("%d ", lista_sequencial[i]);
        }
        printf("\n");
    } else {
        printf("Lista cheia, não é possível adicionar mais elementos.\n");
    }

    return 0;
}
```
# Remoção de Elementos:
## Remoção de Elemento em uma Lista Sequencial

Para explicar como funciona a remoção de um elemento em uma lista sequencial e o processo de deslocamento de elementos que ocorre durante essa operação, segue um passo a passo detalhado:

## Identificação do Elemento a Ser Removido:

Inicialmente, é necessário identificar o elemento específico que será removido da lista sequencial.

## Localização do Elemento na Lista:

Encontre a posição do elemento a ser removido na lista, seja por índice, valor ou critério específico.

## Deslocamento dos Elementos Posteriores:

Todos os elementos que estão após o elemento a ser removido precisam ser deslocados para preencher o espaço deixado pela remoção. Os elementos são movidos uma posição para trás, garantindo que a ordem dos elementos seja mantida.

## Atualização do Tamanho da Lista:

Após o deslocamento dos elementos, o tamanho da lista é atualizado para refletir a remoção do elemento.

## Exclusão do Elemento:

O elemento identificado é removido da lista após o deslocamento dos elementos posteriores.

## Verificação de Limites:

Durante o processo de remoção e deslocamento, é essencial verificar os limites da lista para evitar erros de acesso a posições inválidas.

## Finalização da Operação:

Após a remoção do elemento e o deslocamento adequado dos elementos posteriores, a operação de remoção é concluída.

Em resumo, ao remover um elemento de uma lista sequencial, é crucial identificar o elemento a ser removido, deslocar os elementos posteriores para preencher o espaço vazio, atualizar o tamanho da lista e, finalmente, excluir o elemento. Esse processo garante a integridade da lista e a correta ordenação dos elementos restantes após a remoção.

# Remoção de Elemento em uma Lista Sequencial em C

```c
#include <stdio.h>

#define MAX_SIZE 10

int main() {
    int lista_sequencial[MAX_SIZE] = {10, 20, 30, 40, 50};
    int elemento_remover = 30;
    int tamanho = 5; // Tamanho atual da lista

    int i, j;
    for (i = 0; i < tamanho; i++) {
        if (lista_sequencial[i] == elemento_remover) {
            for (j = i; j < tamanho - 1; j++) {
                lista_sequencial[j] = lista_sequencial[j + 1];
            }
            tamanho--;
            break;
        }
    }

    if (i == tamanho) {
        printf("Elemento não encontrado na lista.\n");
    } else {
        printf("Lista após remover elemento: ");
        for (i = 0; i < tamanho; i++) {
            printf("%d ", lista_sequencial[i]);
        }
        printf("\n");
    }

    return 0;
}
```

### Busca de Elementos:

- **Busca Sequencial:** Para encontrar um elemento específico, a lista é percorrida sequencialmente até encontrar o elemento desejado.

### Inicialização e Reinicialização:

- **Inicialização da Lista:** Antes de utilizar a lista, é necessário inicializá-la, definindo seu estado inicial.
  
- **Reinicialização:** Permite reiniciar a lista, removendo todos os elementos e preparando-a para um novo uso.

Em resumo, as listas lineares sequenciais são estruturas de dados simples e eficientes, ideais para situações em que a ordem de inserção e a sequencialidade dos elementos são importantes. Elas facilitam operações de manipulação de dados, como inserção, remoção e busca, devido à sua organização contígua e ordenada na memória.



# Listas Lineares Encadeadas

As listas lineares encadeadas são estruturas de dados que diferem das listas lineares sequenciais, como vetores, por não manterem seus elementos em posições contíguas de memória. Em uma lista encadeada, cada elemento, ou nó, contém um link para o próximo elemento na lista, permitindo inserções e remoções eficientes sem a necessidade de rearranjar os demais elementos. Essa estrutura é implementada através de ponteiros, onde cada nó guarda o endereço do próximo nó na sequência.

Uma vantagem significativa das listas encadeadas sobre as sequenciais é a eficiência nas operações de inserção e remoção, pois não exigem o deslocamento de todos os elementos da lista. Além disso, as listas encadeadas não requerem a previsão do número de elementos antecipadamente, pois o espaço é alocado dinamicamente durante a execução do programa.

Existem diferentes tipos de listas encadeadas, como simplesmente encadeadas, duplamente encadeadas e circulares, cada uma com suas características específicas. Por exemplo, em listas duplamente encadeadas, cada nó possui referências tanto para o próximo quanto para o nó anterior, facilitando a navegação em ambas as direções.

Essas estruturas são amplamente utilizadas em programação devido à sua flexibilidade e eficiência em lidar com operações de manipulação de dados, como inserções, remoções e buscas.

![conceito](https://github.com/MariaEduardaLeal/Estudos-Algoritmo/assets/71770176/cc0dadf6-aacf-487d-aa8a-b90f4f4b37bb)

## Inserção de Dados em Listas Encadeadas

A inserção de um elemento em uma lista linear encadeada é realizada de forma eficiente e flexível, sem a necessidade de realocar todos os elementos da lista. Para inserir um novo elemento em uma lista encadeada, segue-se um procedimento padrão que envolve a criação de um novo nó, a atualização dos ponteiros e a reorganização dos links na estrutura da lista. Aqui está um resumo do processo de inserção em uma lista linear encadeada:

### Criação do Novo Nó:

- Um novo nó é alocado na memória para armazenar o elemento a ser inserido.

### Atualização dos Ponteiros:

- O novo nó é configurado com o valor do elemento a ser inserido.
- O ponteiro do novo nó é ajustado para apontar para o nó que atualmente é o primeiro da lista.

### Atualização do Ponteiro da Cabeça:

- O ponteiro da cabeça da lista é redirecionado para apontar para o novo nó, tornando-o o primeiro elemento da lista.

### Conclusão da Inserção:

- Após esses passos, o novo elemento foi inserido com sucesso no início da lista encadeada.

Esse processo de inserção em uma lista linear encadeada é eficiente, pois não requer a movimentação de todos os elementos existentes na lista, apenas a atualização de alguns ponteiros. Isso torna as operações de inserção e remoção mais ágeis em comparação com estruturas de dados sequenciais, como arrays, especialmente em cenários onde a lista pode crescer ou diminuir dinamicamente.
![insercao-lista-encadeda](https://github.com/MariaEduardaLeal/Estudos-Algoritmo/assets/71770176/c7c30352-b93b-4435-93d2-2b699ac592f4)

## Remoção de Elementos em Listas Encadeadas

A remoção de um elemento em uma lista linear encadeada é um processo que envolve ajustar os ponteiros adequadamente para manter a integridade da estrutura da lista. Aqui está um resumo do procedimento para remover um elemento de uma lista linear encadeada:

### Localização do Elemento a Ser Removido:

- Percorre-se a lista linear encadeada até encontrar o elemento que se deseja remover.

### Atualização dos Ponteiros:

- O ponteiro do nó anterior ao nó a ser removido é redirecionado para apontar para o nó seguinte ao nó a ser removido.
- O nó a ser removido é desvinculado da lista, liberando a memória alocada para ele.

### Liberação de Memória:

- Após a remoção do nó, é importante liberar a memória alocada para ele para evitar vazamentos de memória.

### Conclusão da Remoção:

- Após esses passos, o elemento é removido com sucesso da lista linear encadeada.

Esse processo de remoção em uma lista linear encadeada é eficiente, pois não requer a movimentação de todos os elementos da lista, apenas a atualização dos ponteiros necessários. Isso torna as operações de remoção ágeis e eficazes, mantendo a estrutura da lista consistente e organizada.

# Relacionamento entre Listas Lineares e Grafos

As listas lineares podem ser relacionadas aos grafos, especialmente em representações de grafos como listas de adjacência.

## Listas de Adjacência

Em um grafo, os vértices (ou nós) são conectados por arestas (ou arcos). Nas listas de adjacência, cada vértice do grafo é representado por uma lista encadeada contendo os vértices adjacentes a ele. Isso significa que, para cada vértice, há uma lista de seus vizinhos ou conexões.

### Exemplo

Considere um grafo não direcionado com quatro vértices (A, B, C, D) e as seguintes conexões:

- A está conectado a B e C.
- B está conectado a A e D.
- C está conectado a A e D.
- D está conectado a B e C.

Essa estrutura pode ser representada usando listas de adjacência da seguinte forma:

- A: [B, C]
- B: [A, D]
- C: [A, D]
- D: [B, C]

Neste exemplo, cada vértice é representado por uma lista encadeada contendo seus vizinhos. Isso mostra uma relação direta entre as listas encadeadas e os grafos, onde cada nó da lista representa um vértice no grafo e os elementos dentro da lista representam as conexões desse vértice com outros vértices.

## Utilidade e Aplicações

- **Eficiência:** As listas de adjacência permitem uma representação compacta de grafos esparsos, onde apenas uma fração das possíveis conexões está presente.
- **Facilidade de Manipulação:** As listas encadeadas facilitam operações como adição, remoção e busca de conexões em grafos.
- **Flexibilidade:** Listas de adjacência permitem a representação de grafos direcionados e não direcionados, além de serem adaptáveis a diferentes tipos de grafos e problemas.

Portanto, as listas lineares, especialmente as listas encadeadas, são comumente usadas na representação de grafos, facilitando operações como adição, remoção e busca de conexões.

# Pilhas: Estruturas de Dados LIFO
![image](https://github.com/MariaEduardaLeal/Estudos-Algoritmo/assets/71770176/df01afd6-7574-4da6-9533-72692258074c)

As pilhas são estruturas de dados fundamentais na computação que seguem o princípio LIFO (Last-In, First-Out), onde o último elemento inserido é o primeiro a ser removido. Aqui estão os principais pontos sobre pilhas:

## Funcionamento:

- Em uma pilha, os elementos são adicionados e removidos apenas em uma extremidade, chamada de topo.
- A operação de adicionar um elemento é chamada de "push", enquanto a remoção é chamada de "pop".
- O elemento mais recentemente adicionado é o primeiro a ser removido, seguindo a ordem LIFO.

## Aplicações:

- Pilhas são amplamente utilizadas em diversas áreas da computação, como análise de expressões matemáticas, algoritmos de backtracking, histórico de navegação em navegadores web e chamadas de função em linguagens de programação.
- São essenciais para implementar a funcionalidade "Desfazer" em editores de texto, permitindo reverter ações na ordem inversa em que foram realizadas.

## Implementação:

- Uma pilha pode ser implementada utilizando arrays ou listas encadeadas, onde o topo da pilha é controlado para adicionar e remover elementos.
- Operações comuns em pilhas incluem verificar se está vazia, ver o elemento no topo sem removê-lo e manipular elementos apenas no topo.

## Exemplo de Uso:

- Ao pensar em uma pilha de pratos em uma cozinha, onde os pratos são empilhados e removidos do topo, podemos visualizar o funcionamento básico de uma pilha de dados na programação.

Essas estruturas de dados são cruciais para muitas aplicações computacionais, fornecendo uma maneira eficiente de gerenciar dados de forma organizada e seguindo uma ordem específica de inserção e remoção.

### Exemplos de Criação e Manipulação de Pilhas em C e Python

#### Em C:

**Criação da Pilha em C:**

```c
Stack* pilha; // Declarando variável do tipo Stack
pilha = new(); // Criando uma Pilha
```

**Inserção e Remoção de Valores na Pilha em C:**
```c
push(pilha, 10); // Adicionando valores à pilha
push(pilha, 20);
float item_removido = pop(pilha); // Removendo valor da pilha
```

#### Em Python:

**Criação e Manipulação de Pilha em Python:**
```python
stack = [3, 4, 5]  # Criando uma pilha em Python
stack.append(6)  # Adicionando um item ao topo da pilha
stack.append(7)
stack.pop()  # Removendo um item do topo da pilha
```

**Exemplo de Utilização de Pilha em Python:**
```python
stack = []  # Inicializando uma pilha vazia
stack.append(10)  # Adicionando elementos à pilha
stack.append(20)
item_removido = stack.pop()  # Removendo elemento do topo da pilha
print(f"{item_removido} foi o item removido")
```
# Filas em Estruturas de Dados

As filas são estruturas de dados que seguem o princípio FIFO (First In, First Out), ou seja, o primeiro elemento a ser inserido em uma fila é o primeiro a ser removido. Aqui estão alguns pontos-chave sobre filas:

- Filas são casos especiais de listas.
- Nas listas, quando precisávamos criar um novo elemento, poderíamos inseri-lo ou removê-lo de qualquer posição da lista, exemplos:
  - Na primeira posição;
  - Na última posição; ou
  - Em qualquer parte no meio da lista.

## Filas

- Numa fila seguida: existe uma regra básica a ser:
  - Primeiro a Chegar é o Primeiro a Sair;
  - Do inglês: FIFO (First In, First Out).
- Um novo elemento da fila somente pode ser inserido na última posição (fim da fila).
- Um elemento só pode ser removido da primeira posição (início da fila).

## Implementação de Filas:

- Em linguagens como C e Python, as filas podem ser implementadas utilizando estruturas de dados como listas encadeadas ou vetores.
- Em C, a implementação de filas pode envolver alocação dinâmica de memória para os elementos da fila e manipulação de ponteiros para controlar o início e o fim da fila.
- Em Python, a estrutura de lista facilita a implementação de filas de forma mais simples e dinâmica.

## Operações em Filas:

- As operações básicas em uma fila incluem a inserção de elementos (enqueue) e a remoção de elementos (dequeue).
- Além disso, é comum ter operações para verificar se a fila está vazia, acessar o elemento no início da fila (front), e obter o tamanho da fila.

## Utilização de Filas:

- As filas são amplamente utilizadas em algoritmos e aplicações que requerem processamento de dados de forma sequencial, como simulações, sistemas de gerenciamento de tarefas, entre outros.
- Exemplos práticos de filas incluem a simulação de filas de espera em sistemas de atendimento e o controle de tarefas em sistemas operacionais.

## Estruturas Relacionadas:

- Além das filas, outras estruturas de dados como pilhas (stacks) e listas encadeadas são fundamentais para a organização e manipulação eficiente de dados em algoritmos e programas.

Em resumo, as filas são estruturas de dados essenciais que seguem a lógica FIFO, sendo úteis em diversas aplicações computacionais que exigem o processamento ordenado de elementos.
![image](https://github.com/MariaEduardaLeal/Estudos-Algoritmo/assets/71770176/5b6a4006-1bd6-4af5-8be6-db36072abcc8)
![image](https://github.com/MariaEduardaLeal/Estudos-Algoritmo/assets/71770176/510fdbbf-cb53-4e84-8149-a7f3f16615d1)
![image](https://github.com/MariaEduardaLeal/Estudos-Algoritmo/assets/71770176/070f2a1a-d29e-4586-888a-b1c04b775304)
![image](https://github.com/MariaEduardaLeal/Estudos-Algoritmo/assets/71770176/61147f88-3735-4a8d-862d-d821bd2f73ce)
![image](https://github.com/MariaEduardaLeal/Estudos-Algoritmo/assets/71770176/f2b9b2d4-1fe9-40f4-9daa-eb11d2f5c939)
![image](https://github.com/MariaEduardaLeal/Estudos-Algoritmo/assets/71770176/f4427328-338e-4788-a6e0-20a519694ac1)



#Sites que podem ser importantes:

- Listas
https://www.alura.com.br/artigos/estruturas-de-dados-introducao
https://www.cos.ufrj.br/~rfarias/cos121/aula_11.html
https://blog.grancursosonline.com.br/estrutura-de-dados-estrututra-lineares/
https://www.youtube.com/watch?v=rsRNu8-v0_0&list=PLrOyM49ctTx-l7WTi99OG6ZXxE5FCzPJi&index=4
https://www.youtube.com/watch?v=RW0oD2L_tSg&t=917s


- Grafos
https://www.ime.usp.br/~pf/algoritmos_para_grafos/aulas/graphdatastructs.html
https://www.youtube.com/watch?v=6YP0VGElhR8&t=303s
https://pt.khanacademy.org/computing/computer-science/algorithms/breadth-first-search/a/breadth-first-search-and-its-uses


- Pilhas
https://dev.to/iamjose/explorando-estruturas-de-dados-em-java-pilhas-e-filas-dc3
https://growthcode.com.br/algoritmos/pilha-estrutura-de-dados/
https://www.cos.ufrj.br/~rfarias/cos121/pilhas.html
https://www.linkedin.com/pulse/algoritmos-e-estrutura-de-dados-pilhas-bruno-botelho-de-souza/?originalSubdomain=pt


- Filas
http://docente.ifsc.edu.br/vilson.junior/ed/04_Listas_Filas_Pilhas.pdf 
https://gabrielbueno072.github.io/rea-aed/aula_pilha_fila.html
https://www.ime.usp.br/~pf/algoritmos/aulas/fila.html
