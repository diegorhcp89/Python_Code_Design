# Python_Code_Design# Calculadora API

Esta API fornece três calculadoras para processamento matemático de números enviados por requisições HTTP. Cada calculadora realiza uma série de operações matemáticas específicas e retorna os resultados de forma estruturada em formato JSON.

## Estrutura do Projeto

O projeto é baseado no **Flask**, um micro-framework para Python, e foi estruturado em torno de diferentes classes de calculadora que implementam a lógica de cálculo específica. As rotas da API são configuradas para executar cada calculadora de forma independente, dependendo do tipo de requisição.

### Calculadora 1

A **Calculadora 1** realiza uma série de operações matemáticas, como dividir um número por 3, processar esse número em duas etapas e retornar o resultado final após essas operações.

- **Rota**: `/calculator/1`
- **Método**: `POST`
- **Entrada**: JSON com a chave `number` (um número).
- **Saída**: JSON com o resultado calculado.

#### Exemplo de entrada:
```json
{
  "number": 1
}

#### Exemplo de saída:
{
  "data": {
    "Calculator": 1,
    "result": 14.25
  }
}

### Calculadora 2

A **Calculadora 2** recebe uma lista de números, realiza um cálculo complexo em cada número e então aplica uma derivação padrão usando um driver. O resultado final é retornado como resposta.

- **Rota**: `/calculator/2`
- **Método**: `POST`
- **Entrada**: JSON com a chave `numbers` (uma lista de números).
- **Saída**: JSON com o resultado calculado.

#### Exemplo de entrada:
```json
{
  "numbers": [2.12, 4.62, 1.32]
}


#### Exemplo de saída:
{
  "data": {
    "Calculator": 2,
    "result": 0.33
  }
}

### Calculadora 3

A **Calculadora 3** calcula a variância de uma lista de números e a multiplicação de todos os números da lista. Se a variância for menor que a multiplicação, será gerado um erro. Caso contrário, o valor da variância é retornado.

- **Rota**: `/calculator/3`
- **Método**: `POST`
- **Entrada**: JSON com a chave `numbers` (uma lista de números).
- **Saída**: JSON com o valor da variância ou erro se a condição não for atendida.

#### Exemplo de entrada:
```json
{
  "numbers": [1, 1, 1, 1, 100]
}

{
  "data": {
    "Calculator": 3,
    "value": 1000000,
    "Sucess": True
  }
}

## Como Executar o projeto

### Executar o ServidorInstalar Dependências: Utilize o pip para instalar as dependências necessárias:**

pip install -r requirements.txt

### Executar o Servidor**:

python app.py

### O servidor estará rodando na porta padrão do Flask (5000). Você pode acessar as rotas da API em:

- **http://127.0.0.1:5000/calculator/1**
- **http://127.0.0.1:5000/calculator/2**
- **http://127.0.0.1:5000/calculator/3**

## Testes

A API possui testes implementados usando o A API possui testes implementados usando o **Pytest** para garantir que as funcionalidades de cada calculadora estão funcionando corretamente. Para rodar os testes, utilize o comando:pytest para garantir que as funcionalidades de cada calculadora estão funcionando corretamente. Para rodar os testes, utilize o comando:

pytest

## Dependências

- **Flask: Framework web para construção da API.
- **pytest: Framework para execução dos testes unitários.
- **Numpy (para calculadora 2): Usado para manipulação de arrays e cálculos de variância.