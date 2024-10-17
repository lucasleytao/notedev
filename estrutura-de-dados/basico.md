## Estrutura de Dados: Resumo Técnico

Estudar estruturas de dados é fundamental para criar algoritmos eficientes e lidar com a gestão de dados em sistemas complexos. Aqui está o que é essencial:

---

### 1. **Arrays (Vetores/Listas)**
   - **O que é**: Uma coleção de elementos, onde cada elemento pode ser acessado pelo seu índice. Tamanho fixo (em C, Java) ou dinâmico (Python, JavaScript).
   - **Operações**:
     - Acesso: O(1)
     - Inserção: O(n) (no pior caso, se precisar expandir)
     - Exclusão: O(n)
   - **Uso**: Armazenar itens que precisam ser acessados em ordem ou por índice.

   Arrays são uma das estruturas mais básicas. Eles armazenam múltiplos valores em uma única variável, acessíveis através de índices.

**Exemplo em JavaScript**:
```javascript
let arr = [10, 20, 30, 40];
console.log(arr[2]);  // índice [2] = 30
arr.push(50);         // Inserir no final
console.log(arr);     // [10, 20, 30, 40, 50]
```

**Exemplo em Python**:
```python
arr = [10, 20, 30, 40]
print(arr[2])  # 30
arr.append(50)  # Inserir no final
print(arr)  # [10, 20, 30, 40, 50]
```
---

### 2. **Linked Lists (Listas Ligadas)**
   - **O que é**: Uma sequência de nós, onde cada nó contém um valor e um ponteiro para o próximo nó. Versões: **Singly Linked List** (única ligação) e **Doubly Linked List** (ligação dupla).
   - **Operações**:
     - Inserção: O(1) (se feita no início)
     - Busca: O(n)
     - Exclusão: O(1) (se no início)
   - **Uso**: Quando inserções/remover itens frequentes são mais importantes do que o acesso por índice.

   Uma lista ligada é uma estrutura linear onde cada elemento (nó) contém um valor e uma referência (ponteiro) para o próximo nó.

**Exemplo em JavaScript**:
```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
  }

  insert(value) {
    const newNode = new Node(value);
    if (!this.head) {
      this.head = newNode;
    } else {
      let current = this.head;
      while (current.next) {
        current = current.next;
      }
      current.next = newNode;
    }
  }

  display() {
    let current = this.head;
    while (current) {
      console.log(current.value);
      current = current.next;
    }
  }
}

const list = new LinkedList();
list.insert(10);
list.insert(20);
list.display();  // 10, 20
```

**Exemplo em Python**:
```python
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert(self, value):
        new_node = Node(value)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node

    def display(self):
        current = self.head
        while current:
            print(current.value)
            current = current.next

list = LinkedList()
list.insert(10)
list.insert(20)
list.display()  # 10, 20
```
---

### 3. **Stacks (Pilhas)**
   - **O que é**: Estrutura do tipo LIFO (Last In, First Out). Você só pode acessar ou remover o último item inserido.
   - **Operações**:
     - `push`: O(1)
     - `pop`: O(1)
     - `peek`: O(1)
   - **Uso**: Pilhas de execução, sistema de desfazer/refazer.

   Pilhas seguem o princípio LIFO (Last In, First Out), ou seja, o último elemento inserido é o primeiro a ser removido.

**Exemplo em JavaScript**:
```javascript
let stack = [];
stack.push(10);  // Insere 10
stack.push(20);  // Insere 20
console.log(stack.pop());  // Remove e imprime 20
```

**Exemplo em Python**:
```python
stack = []
stack.append(10)  # Insere 10
stack.append(20)  # Insere 20
print(stack.pop())  # Remove e imprime 20
```
---

### 4. **Queues (Filas)**
   - **O que é**: Estrutura do tipo FIFO (First In, First Out), onde o primeiro elemento adicionado é o primeiro removido.
   - **Operações**:
     - `enqueue`: O(1)
     - `dequeue`: O(1)
   - **Uso**: Filas de impressão, processamento de tarefas.

   Filas seguem o princípio FIFO (First In, First Out), ou seja, o primeiro elemento inserido é o primeiro a ser removido.

**Exemplo em JavaScript**:
```javascript
let queue = [];
queue.push(10);  // Enfileira 10
queue.push(20);  // Enfileira 20
console.log(queue.shift());  // Remove e imprime 10
```

**Exemplo em Python**:
```python
from collections import deque
queue = deque()
queue.append(10)  # Enfileira 10
queue.append(20)  # Enfileira 20
print(queue.popleft())  # Remove e imprime 10
```
---

### 5. **Hash Tables (Tabelas Hash)**
   - **O que é**: Estrutura que associa uma **chave** a um **valor** usando uma função hash. Ideal para buscas rápidas.
   - **Operações**:
     - Inserção: O(1) (na média)
     - Busca: O(1) (na média)
     - Exclusão: O(1)
   - **Uso**: Armazenar dados de forma eficiente para buscas rápidas, como um dicionário.

   Uma tabela hash é uma estrutura de dados que associa chaves a valores, permitindo a recuperação de dados de forma rápida.

**Exemplo em JavaScript**:
```javascript
let hashTable = {
  "Lucas": 30,
  "Ana": 25,
};
console.log(hashTable["Lucas"]);  // 30
```

**Exemplo em Python**:
```python
hash_table = {
    "Lucas": 30,
    "Ana": 25
}
print(hash_table["Lucas"])  # 30
```
---

### 6. **Árvores Binárias de Busca (Binary Search Trees)**
   - **O que é**: Estrutura hierárquica, onde cada nó possui filhos. A versão mais comum é a **árvore binária**, onde cada nó tem no máximo dois filhos.
   - **Operações**:
     - Inserção: O(log n) (em árvores balanceadas)
     - Busca: O(log n)
     - Exclusão: O(log n)
   - **Tipos**:
     - **Binary Search Tree (BST)**: Árvores onde o filho esquerdo é menor que o pai e o filho direito é maior.
     - **Heap**: Árvore que mantém a propriedade de "heap", onde o maior (ou menor) elemento é sempre a raiz.
   - **Uso**: Algoritmos de busca (BST), organização de prioridade (Heaps).

   Uma árvore binária de busca organiza dados de maneira que para cada nó, os valores menores estão à esquerda e os maiores estão à direita.

**Exemplo em JavaScript**:
```javascript
class Node {
  constructor(data) {
    this.data = data;
    this.left = null;
    this.right = null;
  }
}

class BinarySearchTree {
  constructor() {
    this.root = null;
  }

  insert(data) {
    const newNode = new Node(data);
    if (!this.root) {
      this.root = newNode;
    } else {
      this.insertNode(this.root, newNode);
    }
  }

  insertNode(node, newNode) {
    if (newNode.data < node.data) {
      if (!node.left) {
        node.left = newNode;
      } else {
        this.insertNode(node.left, newNode);
      }
    } else {
      if (!node.right) {
        node.right = newNode;
      } else {
        this.insertNode(node.right, newNode);
      }
    }
  }

  find(data) {
    return this.findNode(this.root, data);
  }

  findNode(node, data) {
    if (!node) return null;
    if (data < node.data) return this.findNode(node.left, data);
    if (data > node.data) return this.findNode(node.right, data);
    return node;
  }
}

const bst = new BinarySearchTree();
bst.insert(8);
bst.insert(3);
bst.insert(10);
console.log(bst.find(3));  // Encontra 3
```

**Exemplo em Python**:
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

class BinarySearchTree:
    def __init__(self):
        self.root = None

    def insert(self, data):
        if self.root is None:
            self.root = Node(data)
        else:
            self._insert(self.root, data)

    def _insert(self, node, data):
        if data < node.data:
            if node.left is None:
                node.left = Node(data)
            else:
                self._insert(node.left, data)
        else:
            if node.right is None:
                node.right = Node(data)
            else:
                self._insert(node.right, data)

    def find(self, data):
        return self._find(self.root, data)

    def _find(self, node, data):
        if node is None:
            return None
        if data < node.data:
            return self._find(node.left, data)
        elif data > node.data:
            return self._find(node.right, data)
        else:
            return node

bst = BinarySearchTree()
bst.insert(8)
bst.insert(3)
bst.insert(10)
print(bst.find(3).data)  # Encontra 3
```
---

### 7. **Graphs (Grafos)**
   - **O que é**: Conjunto de **vértices** conectados por **arestas**. Pode ser **direcionado** ou **não-direcionado**.
   - **Operações**:
     - Busca de caminho (BFS, DFS)
     - Encontrar ciclos, caminhos mais curtos
   - **Uso**: Redes sociais, mapas, otimização de rotas, análise de redes.

   Grafos são coleções de nós (vértices) conectados por arestas, representando relações ou caminhos.

**Exemplo em JavaScript**:
```javascript
class Graph {
  constructor() {
    this.adjacencyList = {};
  }

  addVertex(vertex) {
    if (!this.adjacencyList[vertex]) {
      this.adjacencyList[vertex] = [];
    }
  }

  addEdge(vertex1, vertex2) {
    this.adjacencyList[vertex1].push(vertex2);
    this.adjacencyList[vertex2].push(vertex1);
  }

  display() {
    for (let vertex in this.adjacencyList) {
      console.log(vertex, ":", this.adjacencyList[vertex]);
    }
  }
}

const graph = new Graph();
graph.addVertex("A");
graph.addVertex("B");
graph.addEdge("A", "B");
graph.display();
// A : [ 'B' ]
// B : [ 'A' ]
```

**Exemplo em Python**:
```python
class Graph:
    def __init__(self):
        self.adjacency_list = {}

    def add_vertex(self, vertex):
        if vertex not in self.adjacency_list:
            self.adjacency_list[vertex] = []

    def add_edge(self, vertex1, vertex2):
        self.adjacency_list[vertex1].append(vertex2)
        self.adjacency_list[vertex2].append(vertex1)

    def display(self):
        for vertex in self.adjacency_list:
            print(vertex, ":", self.adjacency_list[vertex])

graph = Graph()
graph.add_vertex("A")
graph.add_vertex("B")
graph.add_edge("A", "B")
graph.display()
# A : ['B']
# B : ['A']
```
---

### 8. **Heaps (Max-Heap)**
   - **O que é**: Árvore binária completa onde o valor de cada nó pai é maior (ou menor) que os filhos.
   - **Operações**:
     - Inserção: O(log n)
     - Remoção: O(log n)
     - Busca pelo maior/menor: O(1)
   - **Uso**: Gerenciamento de prioridade, algoritmos como Dijkstra.

   Heaps são estruturas de dados baseadas em árvores que mantêm a propriedade de heap: o maior ou menor elemento está sempre na raiz.

**Exemplo em JavaScript**:
```javascript
class MaxHeap {
  constructor() {
    this.heap = [];
  }

  insert(value) {
    this.heap.push(value);
    this.bubbleUp();
  }

  bubbleUp() {
    let index = this.heap.length - 1;
    const element = this.heap[index];
    while (index > 0) {
      let parentIndex = Math.floor((index - 1) / 2);
      let parent = this.heap[parentIndex];
      if (parent >= element) break;
      this.heap[index] = parent;
      index = parentIndex;
    }
    this.heap[index] = element;
  }

  extractMax() {
    const max = this.heap[0];
    const end = this.heap.pop();
    if (this.heap.length > 0) {
      this.heap[0] = end;
      this.sinkDown();
    }
    return max;
  }

  sinkDown() {
    let index = 0;
    const length = this.heap.length;
    const element = this.heap[0];
    while (true) {
      let leftChildIndex = 2 * index + 1;
      let rightChildIndex = 2 * index + 2;
      let leftChild, rightChild;
      let swap = null;
      if (leftChildIndex < length) {
        leftChild = this.heap[leftChildIndex];
        if (leftChild > element) {
          swap = leftChildIndex;
        }
      }
      if (rightChild

Index < length) {
        rightChild = this.heap[rightChildIndex];
        if ((swap === null && rightChild > element) || (swap !== null && rightChild > leftChild)) {
          swap = rightChildIndex;
        }
      }
      if (swap === null) break;
      this.heap[index] = this.heap[swap];
      index = swap;
    }
    this.heap[index] = element;
  }
}

const maxHeap = new MaxHeap();
maxHeap.insert(10);
maxHeap.insert(20);
console.log(maxHeap.extractMax());  // 20
```

**Exemplo em Python**:
```python
import heapq

class MaxHeap:
    def __init__(self):
        self.heap = []

    def insert(self, value):
        heapq.heappush(self.heap, -value)  # Negativo para simular max-heap

    def extract_max(self):
        return -heapq.heappop(self.heap)

max_heap = MaxHeap()
max_heap.insert(10)
max_heap.insert(20)
print(max_heap.extract_max())  # 20
```
---

### 9. **Tries (Árvore de Prefixos)**
   - **O que é**: Árvore usada para armazenar strings, onde cada nó representa um caractere. É eficiente para buscas de prefixos.
   - **Operações**:
     - Inserção: O(m), onde m é o comprimento da string
     - Busca: O(m)
   - **Uso**: Auto-complete, sistemas de busca de palavras.

   Tries são árvores especializadas usadas principalmente para busca rápida de strings, como em dicionários ou auto-complete.

**Exemplo em JavaScript**:
```javascript
class TrieNode {
  constructor() {
    this.children = {};
    this.isEndOfWord = false;
  }
}

class Trie {
  constructor() {
    this.root = new TrieNode();
  }

  insert(word) {
    let node = this.root;
    for (let char of word) {
      if (!node.children[char]) {
        node.children[char] = new TrieNode();
      }
      node = node.children[char];
    }
    node.isEndOfWord = true;
  }

  search(word) {
    let node = this.root;
    for (let char of word) {
      if (!node.children[char]) {
        return false;
      }
      node = node.children[char];
    }
    return node.isEndOfWord;
  }
}

const trie = new Trie();
trie.insert("hello");
console.log(trie.search("hello"));  // true
```

**Exemplo em Python**:
```python
class TrieNode:
    def __init__(self):
        self.children = {}
        self.is_end_of_word = False

class Trie:
    def __init__(self):
        self.root = TrieNode()

    def insert(self, word):
        node = self.root
        for char in word:
            if char not in node.children:
                node.children[char] = TrieNode()
            node = node.children[char]
        node.is_end_of_word = True

    def search(self, word):
        node = self.root
        for char in word:
            if char not in node.children:
                return False
            node = node.children[char]
        return node.is_end_of_word

trie = Trie()
trie.insert("hello")
print(trie.search("hello"))  # True
```
---

### 10. **Sets (Conjuntos)**
   - **O que é**: Uma coleção de elementos únicos.
   - **Operações**:
     - Inserção: O(1)
     - Remoção: O(1)
     - Busca: O(1)
   - **Uso**: Verificação de existência rápida, eliminação de duplicatas.

   Sets são coleções que armazenam valores únicos, sem duplicatas. Eles são úteis quando você deseja garantir que não haja elementos repetidos em uma coleção.

#### Exemplo em JavaScript
```javascript
// Criando um Set
const mySet = new Set();

// Adicionando valores
mySet.add(1);
mySet.add(2);
mySet.add(3);
mySet.add(2);  // Duplicata, não será adicionada

console.log(mySet);  // Set { 1, 2, 3 }

// Verificando a presença de um elemento
console.log(mySet.has(2));  // true
console.log(mySet.has(4));  // false

// Removendo um elemento
mySet.delete(2);
console.log(mySet);  // Set { 1, 3 }

// Convertendo um Set em Array
const myArray = Array.from(mySet);
console.log(myArray);  // [ 1, 3 ]
```

#### Exemplo em Python
```python
# Criando um set
my_set = {1, 2, 3}

# Adicionando valores
my_set.add(4)
my_set.add(2)  # Duplicata, não será adicionada

print(my_set)  # {1, 2, 3, 4}

# Verificando a presença de um elemento
print(2 in my_set)  # True
print(5 in my_set)  # False

# Removendo um elemento
my_set.remove(3)
print(my_set)  # {1, 2, 4}

# Convertendo um set em lista
my_list = list(my_set)
print(my_list)  # [1, 2, 4]
```
---

### 11. **Algoritmos de Busca e Ordenação**
   - **Busca Linear**: O(n)
   - **Busca Binária**: O(log n) (aplicável em listas ordenadas)
   - **Ordenação**: Bubble Sort (O(n²)), Merge Sort (O(n log n)), Quick Sort (O(n log n)).

A **Busca por Ordenação** (ou ordenação) é uma técnica para organizar elementos em uma coleção de acordo com uma ordem específica (crescente ou decrescente). Existem vários algoritmos de ordenação, e aqui estão exemplos de alguns deles.

### **Exemplo: Ordenação por Bolha (Bubble Sort)** ###

A **ordenação por bolha** é um dos algoritmos mais simples de ordenação, que funciona repetidamente passando pela lista, comparando elementos adjacentes e trocando-os se estiverem na ordem errada.

##### Exemplo em JavaScript
```javascript
function bubbleSort(arr) {
  const n = arr.length;
  for (let i = 0; i < n - 1; i++) {
    for (let j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        // Troca
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
      }
    }
  }
  return arr;
}

const unsortedArray = [5, 3, 8, 4, 2];
const sortedArray = bubbleSort(unsortedArray);
console.log(sortedArray);  // [2, 3, 4, 5, 8]
```

##### Exemplo em Python
```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n - 1):
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                # Troca
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
    return arr

unsorted_array = [5, 3, 8, 4, 2]
sorted_array = bubble_sort(unsorted_array)
print(sorted_array)  # [2, 3, 4, 5, 8]
```

### **Exemplo: Ordenação Rápida (Quick Sort)**

A **ordenação rápida** é um algoritmo eficiente que utiliza o método de divisão e conquista para classificar os elementos.

##### Exemplo em JavaScript
```javascript
function quickSort(arr) {
  if (arr.length <= 1) return arr;

  const pivot = arr[arr.length - 1]; // Escolhendo o último elemento como pivô
  const left = [];
  const right = [];

  for (let i = 0; i < arr.length - 1; i++) {
    if (arr[i] < pivot) {
      left.push(arr[i]);
    } else {
      right.push(arr[i]);
    }
  }

  return [...quickSort(left), pivot, ...quickSort(right)];
}

const unsortedArray = [5, 3, 8, 4, 2];
const sortedArray = quickSort(unsortedArray);
console.log(sortedArray);  // [2, 3, 4, 5, 8]
```

##### Exemplo em Python
```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr

    pivot = arr[-1]  # Escolhendo o último elemento como pivô
    left = []
    right = []

    for i in range(len(arr) - 1):
        if arr[i] < pivot:
            left.append(arr[i])
        else:
            right.append(arr[i])

    return quick_sort(left) + [pivot] + quick_sort(right)

unsorted_array = [5, 3, 8, 4, 2]
sorted_array = quick_sort(unsorted_array)
print(sorted_array)  # [2, 3, 4, 5, 8]
```

### **Exemplo: Merge Sort**

O **Merge Sort** é um algoritmo de ordenação eficiente que utiliza o método de divisão e conquista. Ele divide a lista em sublistas, as ordena e depois as combina (merge) em uma única lista ordenada. Vamos ver um exemplo em JavaScript e Python.

#### Exemplo em JavaScript
```javascript
function mergeSort(arr) {
  // Caso base: se o array tem zero ou um elemento, já está ordenado
  if (arr.length <= 1) return arr; 

  // Encontra o índice do meio
  const mid = Math.floor(arr.length / 2); 
  // Ordena a metade esquerda
  const left = mergeSort(arr.slice(0, mid)); 
  // Ordena a metade direita
  const right = mergeSort(arr.slice(mid)); 

  // Mescla as metades ordenadas e retorna
  return merge(left, right); 
}

function merge(left, right) {
  const result = []; // Array para armazenar o resultado
  let i = 0; // Ponteiro para a metade esquerda
  let j = 0; // Ponteiro para a metade direita

  // Mescla os dois arrays ordenados
  while (i < left.length && j < right.length) {
    // Compara os elementos das metades e adiciona o menor ao resultado
    if (left[i] < right[j]) {
      result.push(left[i]);
      i++; // Move o ponteiro da metade esquerda
    } else {
      result.push(right[j]);
      j++; // Move o ponteiro da metade direita
    }
  }

  // Adiciona os elementos restantes da metade esquerda ou direita
  return result.concat(left.slice(i)).concat(right.slice(j));
}

const unsortedArray = [5, 3, 8, 4, 2];
const sortedArray = mergeSort(unsortedArray);
console.log(sortedArray);  // [2, 3, 4, 5, 8]
```

#### Exemplo em Python
```python
def merge_sort(arr):
    # Caso base: se o array tem zero ou um elemento, já está ordenado
    if len(arr) <= 1:  
        return arr

    # Encontra o índice do meio
    mid = len(arr) // 2  
    # Ordena a metade esquerda
    left = merge_sort(arr[:mid])  
    # Ordena a metade direita
    right = merge_sort(arr[mid:])  

    # Mescla as metades ordenadas e retorna
    return merge(left, right)  

def merge(left, right):
    result = []  # Lista para armazenar o resultado
    i = 0  # Ponteiro para a metade esquerda
    j = 0  # Ponteiro para a metade direita

    # Mescla os dois arrays ordenados
    while i < len(left) and j < len(right):
        # Compara os elementos das metades e adiciona o menor ao resultado
        if left[i] < right[j]:
            result.append(left[i])
            i += 1  # Move o ponteiro da metade esquerda
        else:
            result.append(right[j])
            j += 1  # Move o ponteiro da metade direita

    # Adiciona os elementos restantes da metade esquerda ou direita
    result.extend(left[i:])
    result.extend(right[j:])
    
    return result

unsorted_array = [5, 3, 8, 4, 2]
sorted_array = merge_sort(unsorted_array)
print(sorted_array)  # [2, 3, 4, 5, 8]
```

### Como o Merge Sort Funciona

1. **Divisão**: O array é dividido recursivamente em duas metades até que cada sublista contenha um único elemento.
2. **Mesclagem**: As sublistas são mescladas de volta em ordem crescente. Durante esse processo, os elementos são comparados e colocados na ordem correta.

O Merge Sort é um algoritmo estável e tem complexidade de tempo de \(O(n \log n)\), o que o torna eficiente para listas grandes.

---

### **Recursão**

Recursão significa que uma função chama a si mesma durante sua execução para resolver um problema. Em outras palavras, a função divide o problema em subproblemas menores, resolve esses subproblemas e combina os resultados para chegar à solução final. 

### Como Funciona a Recursão

1. **Caso Base**: É uma condição que para a recursão, impedindo que a função continue chamando a si mesma indefinidamente. É essencial para evitar loops infinitos. Por exemplo, em um algoritmo de busca, o caso base pode ser quando você chega a um valor específico ou a um limite.

2. **Chamadas Recursivas**: Quando a função chama a si mesma com um novo conjunto de argumentos, geralmente mais simples ou menores do que os argumentos originais. Isso ajuda a reduzir o problema até que o caso base seja alcançado.

### Exemplo Simples

Considere uma função que calcula o fatorial de um número \( n \) (representado por \( n! \)), que é o produto de todos os números inteiros de \( 1 \) até \( n \). O fatorial pode ser definido recursivamente da seguinte maneira:

- \( 0! = 1 \) (caso base)
- \( n! = n \times (n - 1)! \) (chamada recursiva)

#### Exemplo em JavaScript
```javascript
function factorial(n) {
  if (n === 0) {
    return 1;  // Caso base
  }
  return n * factorial(n - 1);  // Chamada recursiva
}

console.log(factorial(5));  // 120
```

#### Exemplo em Python
```python
def factorial(n):
    if n == 0:
        return 1  # Caso base
    return n * factorial(n - 1)  # Chamada recursiva

print(factorial(5))  # 120
```
A **recursão** é uma técnica poderosa em programação, frequentemente usada em algoritmos que se beneficiam de resolver subproblemas de forma repetitiva. É importante ter sempre um caso base definido para evitar loops infinitos e garantir que a função termine em algum momento.

---

### Exercício Prático 1: 10 Questões

1. **Arrays**: Crie um array que armazene 5 números inteiros e imprima o terceiro número.
   - **JavaScript**:
     ```javascript
     let arr = [5, 10, 15, 20, 25];
     console.log(arr[2]);  // 15
     ```

2. **Listas Ligadas**: Implemente uma lista ligada simples com operações de inserção e exclusão.

3. **Pilhas (Stack)**: Crie uma pilha e implemente as operações de `push` e `pop`. Simule uma pilha de pratos onde o último prato adicionado é o primeiro a ser retirado.

4. **Filas (Queue)**: Implemente uma fila para armazenar nomes de clientes, onde o primeiro a entrar será o primeiro a ser atendido.

5. **Tabela Hash**: Crie uma tabela hash que armazene nomes e idades. Realize uma busca pelo nome e retorne a idade associada.

6. **Árvore Binária**: Implemente uma árvore binária de busca e adicione os seguintes valores: 8, 3, 10, 1, 6, 14. Em seguida, faça uma busca pelo valor 6.

7. **Busca Linear**: Escreva uma função que receba uma lista de números e um número alvo e retorne o índice do número alvo ou `-1` se não for encontrado (implementação de busca linear).

8. **Heap**: Implemente uma estrutura de heap que insira os seguintes números: 20, 10, 15, 5, 30. Depois, remova o maior valor e imprima o heap resultante.

9. **Trie**: Implemente uma estrutura de Trie para armazenar as palavras "carro", "casa", "cachorro" e faça uma busca pela palavra "casa".

10. **Conjuntos (Set)**: Implemente um conjunto que armazene valores únicos. Insira os valores 1, 2, 3, 3, 4, 5 e imprima o conjunto final (deve eliminar duplicatas).

Esses exercícios ajudarão você a praticar e consolidar o aprendizado de estruturas de dados em diferentes linguagens.

---

### Exercício Prático 2: 20 Questões

1. Implemente uma função que reverta um array.
2. Crie uma função que retorne a soma de todos os números pares de um array.
3. Dada uma string, conte quantas vezes cada letra aparece nela.
4. Crie um algoritmo que converta um número binário para decimal.
5. Implemente uma fila circular com um tamanho fixo.
6. Implemente uma função que retorne o N-ésimo número da sequência de Fibonacci.
7. Implemente um sistema simples de contagem regressiva (timer) que mostre no console a contagem a cada segundo.
8. Crie uma função que calcule o MDC (Máximo Divisor Comum) entre dois números.
9. Implemente um algoritmo para validar se uma string contém apenas caracteres alfabéticos.
10. Implemente uma função que verifique se uma lista é um palíndromo (mesmo valor ao contrário).
11. Crie uma função que receba duas listas e retorne uma lista com os elementos comuns entre elas.
12. Implemente uma função que conte quantos elementos duplicados existem em um array.
13. Dado um grafo representado por uma matriz de adjacências, crie uma função que verifique se há um caminho entre dois vértices.
14. Implemente uma função que, dada uma árvore binária de busca, retorne o maior valor presente nela.
15. Crie um algoritmo que balanceie uma árvore binária.
16. Implemente uma função que encontre o menor elemento em uma heap (min-heap).
17. Crie um programa que simule o funcionamento de uma pilha de pratos: insira e remova pratos.
18. Implemente um algoritmo que busque um elemento em uma árvore Trie.
19. Crie uma função que realize uma busca em profundidade (DFS) em um grafo.
20. Implemente uma função para ordenar uma lista utilizando o algoritmo de ordenação por bolha (bubble sort).