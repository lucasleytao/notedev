## Entidade, tipo, classe e objeto

## **Termos**

Termos em POO, com exemplos em TypeScript:

1. **Entidade**: Representa algo do mundo real, algo que queremos modelar em código. Pode ser uma pessoa, carro, produto, etc.
   - Exemplo de entidade: um **Animal**.

2. **Tipo**: Define que valores ou comportamentos algo pode ter. Em TypeScript, além de classes, também podemos ter tipos específicos que definem quais **propriedades ou valores** uma entidade pode ter.
   - Exemplo de tipo em TypeScript:
     ```typescript
     type Animal = {
       especie: string;
       nome: string;
       idade: number;
     };
     ```

3. **Objeto**: É uma instância real de uma classe ou tipo. Quando criamos um objeto, estamos criando um exemplo de uma entidade no código, com valores específicos.
   - Exemplo de objeto em TypeScript:

     ```typescript
     // instacia de classe

     const gato1 = new Animal("Gato", "Mimi", 2);
     gato1.miar();  // Saída: Mimi, está miando!
     ```
     
     ```typescript
     //instancia de tipo

     const gato1: Animal = {
     	especie: "Gato",
     	nome: "Mimi",
     	idade: 3,
     };
     ```

4. **Classe**: É a definição ou o molde de uma entidade. Ela descreve as propriedades (atributos) e comportamentos (métodos) de uma entidade, mas não é uma instância real.
   - Exemplo de classe em TypeScript:
     ```typescript
     class Animal {
       especie: string;
       nome: string;
       idade: number;

       constructor(especie: string, nome: string, idade: number) {
         this.especie = especie;
         this.nome = nome;
         this.idade = idade;
       }
       miar() {
         console.log(`${this.nome}, está miando!`);
       }
     }
     ```

**Resumo**:
- **Entidade**: Algo do mundo real que você quer modelar (Animal).
- **Tipo**: Define as propriedades de um grupo de dados (tipo `Animal`).
- **Objeto**: Uma instância concreta da classe ou tipo (objeto `gato1`).
- **Classe**: O molde que define os atributos e comportamentos (classe `Animal`).

## **Aplicação**

Vamos aplicar a ideia de **tipo** e **classe** usando a entidade **Animal**, criando dois objetos de **gato** e um objeto de **cachorro**.

### Exemplo com **Tipo** em TypeScript:

No caso do **tipo**, estamos apenas descrevendo a estrutura de um **Animal**, sem métodos ou comportamentos. Vamos criar objetos para **gato** e **cachorro** com base nesse tipo.

```typescript
// Definindo o tipo Animal
type Animal = {
  especie: string;
  nome: string;
  idade: number;
};

// Criando dois objetos do tipo Animal para gatos
const gato1: Animal = {
  especie: "Gato",
  nome: "Mimi",
  idade: 3,
};

const gato2: Animal = {
  especie: "Gato",
  nome: "Tom",
  idade: 2,
};

// Criando um objeto do tipo Animal para cachorro
const cachorro: Animal = {
  especie: "Cachorro",
  nome: "Rex",
  idade: 5,
};

console.log(gato1.nome); // Saída: Mimi
console.log(cachorro.especie); // Saída: Cachorro
```

Aqui:
- Definimos um **tipo `Animal`** que contém as propriedades `especie`, `nome`, e `idade`.
- Criamos dois objetos para os gatos (`gato1` e `gato2`) e um objeto para o cachorro (`cachorro`).
- Esses objetos seguem a estrutura definida pelo tipo, mas **não têm comportamentos**, apenas armazenam dados.

### Exemplo com **Classe** em TypeScript:

Agora, vamos usar uma **classe** para a entidade **Animal**, que terá tanto **propriedades** quanto **comportamentos** (métodos), ou seja, pode criar instâncias (objetos) e ter métodos para manipular essas instâncias. Por exemplo, o comportamento de **fazerSom**.

```typescript
// Definindo a classe Animal
class Animal {
  especie: string;
  nome: string;
  idade: number;

  constructor(especie: string, nome: string, idade: number) {
    this.especie = especie;
    this.nome = nome;
    this.idade = idade;
  }

  // Método que define um comportamento do animal
  fazerSom() {
    if (this.especie === "Gato") {
      console.log(`${this.nome} faz: Miau!`);
    } else if (this.especie === "Cachorro") {
      console.log(`${this.nome} faz: Au au!`);
    }
  }
}

// Criando dois objetos da classe Animal para gatos
const gato1 = new Animal("Gato", "Mimi", 3);
const gato2 = new Animal("Gato", "Tom", 2);

// Criando um objeto da classe Animal para cachorro
const cachorro = new Animal("Cachorro", "Rex", 5);

// Chamando o método fazerSom
gato1.fazerSom();  // Saída: Mimi diz: Miau!
gato2.fazerSom();  // Saída: Tom diz: Miau!
cachorro.fazerSom(); // Saída: Rex diz: Au au!
```

Aqui:
- **Classe `Animal`** define tanto as propriedades (`especie`, `nome`, `idade`) quanto um comportamento (`fazerSom()`).
- **Objetos `gato1`, `gato2`, e `cachorro`** são instâncias da classe `Animal` e possuem tanto os dados quanto o comportamento de **fazerSom**.
- Cada animal pode **realizar uma ação** (fazerSom) com base na sua espécie.

### Comparação Final:
- **Tipo `Animal`**: Define apenas a **estrutura dos dados** (espécie, nome, idade), sem comportamentos. Não cria instâncias e nem construtores.
  - Exemplo de uso:
    ```typescript
    type Animal = {
      especie: string;
      nome: string;
      idade: number;
    };
    ```

- **Classe `Animal`**: Define tanto a **estrutura dos dados** quanto os **comportamentos** (como o método `fazerSom`).
  - Exemplo de uso:
    ```typescript
    class Animal {
      especie: string;
      fazerSom() { /* ... */ }
    }
    ```

Esse é um exemplo simples de como tipos e classes funcionam em TypeScript com a entidade **Animal** e os objetos **gato** e **cachorro**!