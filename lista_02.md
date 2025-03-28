# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?

A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.

______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'
______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".
______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Escolha a opção que responde corretamente:

D)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.

______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.

______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. 


```INICIO
    SE valor < 50 ENTAO
        ESCREVA "Frete não disponível!"

    SENAO, SE valor >= 50 E valor <= 199.99 ENTAO
        ESCREVA "Frete com custo adicional!"

    SENAO, SE valor >= 200 ENTAO
        ESCREVA "Frete grátis!"
FIM
```

Exemplo do código em javascript:
```javascript
const valor = 75;

if (valor < 50) {
  console.log(`Frete não disponível!`);
}
else if (valor >= 50 && valor <= 199.99) {
    console.log(`Frete com custo adicional!`);
}
else if (valor >= 200) {
    console.log(`Frete grátis!`);
}
```
______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

Implementação genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

```
INICIO
CLASSE Veiculo
    ATRIBUTOS:
        modelo
        ano
        quilometragem
        eficiencia

    MÉTODO Construtor(modelo, ano, quilometragem, eficiencia)
        ESTE.modelo ← modelo
        ESTE.ano ← ano
        ESTE.quilometragem ← quilometragem
        ESTE.eficiencia ← eficiencia

    MÉTODO CalcularConsumo()
        ESCREVA "Implementação genérica"
FIM CLASSE

CLASSE Carro HERDA Veiculo
    ATRIBUTOS:
        cor

    MÉTODO Construtor(modelo, ano, quilometragem, eficiencia, cor)
        CHAMAR SUPER(modelo, ano, quilometragem, eficiencia)
        ESTE.cor ← cor

    MÉTODO CalcularConsumo()
        ESCREVA "O carro ", ESTE.modelo, ", do ano de ", ESTE.ano, " e cor ", ESTE.cor, 
        " gasta ", (ESTE.quilometragem / ESTE.eficiencia), 
        " litros ao rodar ", ESTE.quilometragem, "km."
FIM CLASSE

CLASSE Moto HERDA Veiculo
    ATRIBUTOS:
        marca

    MÉTODO Construtor(modelo, ano, quilometragem, eficiencia, marca)
        CHAMAR SUPER(modelo, ano, quilometragem, eficiencia)
        ESTE.marca ← marca

    MÉTODO CalcularConsumo()
        ESCREVA "A moto ", ESTE.modelo, ", da marca ", ESTE.marca, " e ano ", ESTE.ano, 
        " gasta ", (ESTE.quilometragem / ESTE.eficiencia), 
        " litros ao rodar ", ESTE.quilometragem, "km."
FIM CLASSE
FIM
```

Exemplo do código em javascript:
```javascript
class Veiculo {
  constructor(modelo, ano, quilometragem, eficiencia) {
    this.modelo = modelo;
    this.ano = ano;
    this.quilometragem = quilometragem;
    this.eficiencia = eficiencia;
  }

  CalcularConsumo() {
    console.log("Implementação genérica");
  }
  
}

class Carro extends Veiculo {
  constructor(modelo, ano, quilometragem, eficiencia, cor) {
    super(modelo, ano, quilometragem, eficiencia);
    this.cor = cor;
  }

  CalcularConsumo() {
    console.log(`O carro ${this.modelo}, do ano de ${this.ano} e cor ${this.cor}, gasta ${this.quilometragem/this.eficiencia} litros ao rodar ${this.quilometragem}km.`);
  }
}

class Moto extends Veiculo {
  constructor(modelo, ano, quilometragem, eficiencia, marca) {
    super(modelo, ano, quilometragem, eficiencia);
    this.marca = marca;
  }

  CalcularConsumo() {
    console.log(`A moto ${this.modelo}, da marca ${this.marca} e ano ${this.ano}, gasta ${this.quilometragem/this.eficiencia} litros ao rodar ${this.quilometragem}km.`);
  }
}

const carro1 = new Carro ("SUV", 2025, 2789, 12, "cinza");
const moto1 = new Moto ("PCX", 2025, 563892, 45, "Honda");

carro1.CalcularConsumo();
moto1.CalcularConsumo();
```
______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
```
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.

```
INICIO

FUNÇÃO calcularTempoPouso (velocidadeInicial, desaceleracao, tempoMaximo, velocidadeSegura):
    tempo <- 0
    velocidade <- velocidadeInicial
    
    ENQUANTO velocidade > velocidadeSegura e tempo < tempoMaximo FAÇA:
        velocidade = velocidade - (desaceleracao * tempo)
        tempo = tempo + 1
    
    SE velocidade <= velocidadeSegura ENTÃO
        ESCREVA "Pouso seguro em ", tempo, " segundos."

    SENAO
        ESCREVA "Cuidado! Pouso inseguro devido a tempo máximo excedido."
FIM
```
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

Agora, implemente a função MultiplicarMatrizesInvestimento(matrizA, matrizB), que multiplica as duas matrizes, simulando o efeito de diferentes fatores de crescimento e impacto financeiro nos investimentos ao longo do tempo.

```
Função MultiplicarMatrizesInvestimento(matrizA, matrizB):   
    Se linhas(matrizA) ≠ colunas(matrizB) então:  
        Retornar "As matrizes não podem ser mltiplicadas. Elas têm dimensões diferentes."  
    Senão:  
        linhasFinal <- linhas(matrizA)  
        colunasFinal <- colunas(matrizB)  
        matrizResultado <- novaMatriz(linhasFinal, colunasFinal)  

        Retornar matrizResultado  

    Para i de 0 até linhasResultado - 1 e j de 0 até colunasResultado - 1 faça:
            soma <- 0
            Para k de 0 até colunas(matrizA) - 1 faça:
                soma <- soma + matrizA[i][k] * matrizB[k][j]
            matrizResultado[i][j] <- soma

# Exemplo 
investimentosAno1 <- [[1000, 2000], [1500, 2500]]
investimentosAno2 <- [[1.1, 1.2], [1.3, 1.1]]

resultado <- MultiplicarMatrizesInvestimento(investimentosAno1, investimentosAno2)
Escrever("Resultado dos investimentos:")
ImprimirMatriz(resultado)
```