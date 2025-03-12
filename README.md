# lista.01 - Antônio Augusto



# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

Resposta: Letra A -> Quando se declara variáveis em JavaScript do tipo var elas são referenciadas no topo do código mas as inteiração de valores a elas só é dado no local onde esses valores foram colocados na sequência lógica do código, portanto, no primeiro caso ele reconhece que existe a variável x mas ela não contém valor, sendo assim considerada undefined. No caso de variáveis do tipo let elas não são de escopo global como no caso do tipo var, portanto, incluir caminhos no código direcionados a variáveis do tipo let antes de declará-las é errado já que é considerado um local fora do escopo dessa variável do tipo let, caso isso seja feito ocorrerá um erro de código.

**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

Resposta: Letra A -> Quando for usar um if que apresenta mais de uma condição é necessário que ambas apresentem essa condição separadamente. No caso do código acima apenas é apresentada essa condição na variável b e a variável a passa pela condição independente do seu valor. Se no local do console log fosse colocado console.log(soma(0,2)) não seria retornado a frase de Erro: número inválido que é a que seria esperada, mas sim retornaria 0 + 2.

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

Resposta: Letra B -> Quando se executa um switch com diversos casos cada caso tem que ocorrer um break para cessar o processo de verificação. No caso acima ele lê o valor no caso do eletrônico e insere o valor de 1000 no preço, mas como esse caso não tem um break ele roda o próximo e adiquire o valor de 200 mas nesse caso ele já encontra um break e quebra o switch e definine o valor final como 200 e imprime. Se tivesse um break no caso do eletrônico ele imprimiria 1000.
______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

d) 24

Resposta: Letra D -> A variável resultado pega o array de numeros e no primeiro caso .map ele pega cada valor do array e multiplica por 2, no segunda caso .filter ele filtra os números maiores que 5, já no terceiro caso ele faz a soma para que reste apenas um número. Dessa forma o array fica nessa orde: [2, 4, 6, 8, 10] -> [6, 8, 10] -> 24 (Nunca tinha visto essas operações)
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

Resposta: Letra C -> A operação .splice apresenta alguns parâmetros que são eles: por onde começa a tirar elementos de um array tendo em vista os index do array, quantos elementos serão retirados e depois se ocorrerá a reinteração desses locais no array. No caso apresentado ele apresenta os seguintes parâmetros -> (1, 2, "abacaxi", "manga") <- dessa forma ele quer dizer que os elementos a serem tirados começam no index 1, que são tirados 2 elementos e que esses são repostos como os valores de abacaxi e manga chegando, assim, no caso da letra C. 
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

Resposta: Letra A -> Classes em Java Script são declaradas usando o prefixo class e com elas é possível criar subclasses utilizando os seus atributos e métodos, para isso é necessário utilizar um  extends e informar o nome da classe que está sendo usada como a classe pai 
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

Resposta: Letra A -> ✅Item I: O uso de 'extends Pessoa' indica que a classe Funcionaria esta herdando da classe Pessoa e ao usar super(nome, idade) ele acessa os atribudos da classe Pessoa. ✅Item II: O método apresentar() da classe Funcionario sobrepôe o apresentar() da classe Pessoa mas faz isso incrementando o método da classe Pessoa dentro dele usando super.apresentar(). ❌Item III: Já foi visto nos itens anteriores que é possível ter uma herança de classe com classes e subclasses.
______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

Respota: Letra B -> Em POO você pode ter um classe que herda atributos de uma outra classe e com isso pode ser criado um método que responda a mensagem de maneira diferente em cada classe para que seja respondida a mesma pergunta mas de maneira diferente. Caso esse método tenha maneiras diferentes de resposta mas que estejam em uma mesma classe não irá funcionar já que o JavaScript pega só o último método criado.
______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```
Resposta:
```javascript

 function somaArray(numeros) {
   var soma = 0  // declarando a variável soma
    for (let i = 0; i < numeros.length; i++) { // o correto é numeros.length não numeros.size
        soma += 2*numeros[i]; // para somar todos os números o correto é usar += e não =
    }
    return soma;
} 
console.log(somaArray([1, 2, 3, 4]));

```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

Resposta: A herança nesse contexto acontece com o método extends Produto quando for declarada a classe Livro, após isso dentro do constructor eu posso usar um spuer() para puxar os atributor da classe Produto. Para modificar o método eu preciso declarar um método calcularDesconto() dentro da classe Livro e colocar para aplicar um desconto de 20% sobre o preço.
Exemplo:
```javascript

class Produto {
    constructor(nome, preco)
    {
      this.nome = nome;
      this.preco = preco;
    }

    calcularDesconto()
    {
      this.preco *= 0.9
      console.log(this.preco)
    }
}

class Livro extends Produto{
  constructor(nome,preco)
  {
    super(nome,preco)
  }

  calcularDesconto()
  {
    this.preco *= 0.8
    console.log(this.preco)
  }
}
```
