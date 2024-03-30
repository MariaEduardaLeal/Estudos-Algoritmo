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



