# Projeto de Sistema Bancário em Python

## Descrição
Este projeto implementa um **Sistema Bancário** utilizando os princípios da **Programação Orientada a Objetos (POO)** em Python. O sistema simula as operações bancárias comuns, como depósitos, saques e o gerenciamento de contas correntes, utilizando uma estrutura de classes e interfaces bem definidas. A estrutura foi baseada em um diagrama de classes UML que define a relação entre `Cliente`, `Conta`, `Transacao` e outras entidades.

## Funcionalidades

### 1. Cadastro de Contas
- Cada cliente pode possuir uma ou mais contas.
- As contas são associadas a um cliente no momento de sua criação.
- Uma conta pode ser criada com o método `nova_conta(cliente: Cliente, numero: int)`.

### 2. Operações Bancárias
#### Saque
- A operação de saque é realizada através do método `sacar(valor: float)` na classe `Conta`.
- A operação de saque verifica o saldo da conta e o limite da conta corrente antes de realizar a transação.

#### Depósito
- O depósito é feito usando o método `depositar(valor: float)`.
- A transação de depósito é registrada no histórico da conta.

#### Histórico de Transações
- Cada conta mantém um histórico de todas as transações realizadas (saques e depósitos).
- O histórico é gerido pela classe `Historico`, e as transações são adicionadas com o método `adicionar_transacao(transacao: Transacao)`.

### 3. Agrupamento de Dados e Interface de Transações
- As transações, como `Deposito` e `Saque`, são implementadas por meio de uma interface `Transacao` que define o método `registrar(conta: Conta)`.
- A partir dessa interface, diferentes tipos de transações podem ser registradas e associadas ao histórico da conta.

### 4. Conta Corrente
- A classe `ContaCorrente` é uma especialização da classe `Conta` que inclui:
  - Limite de saque.
  - Limite de número de saques.

## Classes e Estrutura

### 1. **Cliente**
- A classe `Cliente` armazena as informações do cliente (endereço e lista de contas).
- Também há uma classe `PessoaFisica`, que é uma extensão de `Cliente`, e inclui informações como CPF e nome.

### 2. **Conta**
- A classe `Conta` gerencia o saldo, número da conta, agência, cliente e histórico de transações.
- Métodos principais:
  - `saldo()`: Retorna o saldo atual da conta.
  - `sacar(valor: float)`: Permite realizar saques.
  - `depositar(valor: float)`: Permite realizar depósitos.

### 3. **ContaCorrente**
- Especializa a classe `Conta` e adiciona atributos de limite de saque e número máximo de saques permitidos.

### 4. **Transação**
- Interface que define o método `registrar(conta: Conta)` para implementação de diferentes transações.
- Tipos de transações:
  - `Deposito`
  - `Saque`

### 5. **Histórico**
- Armazena e gerencia todas as transações associadas a uma conta específica.

## Diagrama de Classes
Aqui está uma representação visual da estrutura de classes do projeto:
![Diagrama de Classes](./Images/Trilha%20Python%20-%20desafio.png)

## Implementação
Aqui está um print da implementação do código, mostrando os resultados obtidos.
![Resultados](./Images/Trilha%20Python%20-%20desafio.png)
