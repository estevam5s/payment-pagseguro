# Biblioteca (lib) PagSeguro-Payment
![JavaScript](https://github.com/MikeCodesDotNET/ColoredBadges/blob/master/svg/dev/languages/js.svg)
![NodeJS](https://github.com/MikeCodesDotNET/ColoredBadges/blob/master/svg/dev/frameworks/nodejs.svg)
![NPM](https://github.com/MikeCodesDotNET/ColoredBadges/blob/master/svg/dev/services/npm.svg)

## Descrição

Biblioteca NPM implementada em JavaScript para o ambiente de pagamento recorrente disponibilizado pelo PagSeguro. Através das funções do arquivo <a href="https://github.com/estevam5s/API-PagSeguro-JavaScript/blob/master/index.js">index.js</a> as requisições HTTP da <a href="https://dev.pagseguro.uol.com.br/reference/api-recorrencia">API PagSeguro</a> são executadas.

---

# Documentação

1. **Pagamento Recorrência**
    1. <a href="https://github.com/estevam5s/API-PagSeguro-JavaScript/blob/master/docs/Pagamento%20Recorrente/Providers%20-%20Fluxo%20b%C3%A1sico.md">Providers - Fluxo básico</a>
    2. <a href="https://github.com/estevam5s/API-PagSeguro-JavaScript/blob/master/docs/Pagamento%20Recorrente/Providers%20-%20Cancelamento.md">Providers - Cancelamento</a>
    3. <a href="https://github.com/estevam5s/API-PagSeguro-JavaScript/blob/master/docs/Pagamento%20Recorrente/Providers%20-%20Altera%C3%A7%C3%A3o.md">Providers - Alteração</a>
    4. <a href="https://github.com/estevam5s/API-PagSeguro-JavaScript/blob/master/docs/Pagamento%20Recorrente/Providers%20-%20Consulta.md">Providers - Consulta</a>
2. **Boleto**
   1. <a href="https://github.com/estevam5s/API-PagSeguro-JavaScript/blob/master/docs/Boleto/Providers%20-%20Gerar%20Boleto.md">Providers - Gerar Boleto</a> 
3. **Checkout Transparente**
   1. <a href="https://github.com/estevam5s/API-PagSeguro-JavaScript/blob/master/docs/Checkout%20Transparente/Providers.md">Primeiros passos</a>
   2. <a href="https://github.com/estevam5s/API-PagSeguro-JavaScript/blob/master/docs/Checkout%20Transparente/Processando%20o%20Checkout.md">Processando o Checkout</a>

---

# Importações
Instale a biblioteca <a href="https://www.npmjs.com/package/pagseguro-payment">PagSeguro-Payment</a> e importe para seu projeto JavaScript.

```bash
npm i pagseguro-payment
```

```javascript
const pagseguro_payment = require("pagseguro-payment");
```

## Método construtor
O método construtor da API requer a passagem de um parâmetro JSON conforme o <a href="https://github.com/estevam5s/API-PagSeguro-JavaScript/blob/master/credentials.json">credentials.json</a>. Os dados de sua conta PagSeguro devem ser inseridos em suas respectivas variáveis (*email* e *token*).
As URLs do objeto *credentials* abaixo estão para o ambiente real, podendo ser alteradas para o ambiente de testes (sandbox) inserindo ".sandbox" após o "ws" de cada uma.
```javascript
const credentials = {
    "email": "",
    "token": "",
    "auth": "https://ws.pagseguro.uol.com.br/",
    "preapprovals": "https://ws.pagseguro.uol.com.br/pre-approvals",
    "preapprovals_request": "https://ws.pagseguro.uol.com.br/pre-approvals/request",
    "preapprovals_payment": "https://ws.pagseguro.uol.com.br/pre-approvals/payment",
    "recurring_payment": "https://ws.pagseguro.uol.com.br/recurring-payment",
    "transactions": "https://ws.pagseguro.uol.com.br/v2/transactions",
    "session":" https://ws.pagseguro.uol.com.br/v2/sessions/"
}
const pagseguroPayment = new pagseguro_payment(credentials);
```
Caso você não saiba gerar um *token*, basta seguir o tutorial no link: https://www.youtube.com/watch?v=Taaa0H6j5Ug
>Não se esqueça de manter seus dados sempre seguros!

---

# Exemplo

Um exemplo básico de execução da API está no arquivo <a href="https://github.com/estevam5s/API-PagSeguro-JavaScript/blob/master/src/test.js">src/test.js</a>. Para executá-lo, basta clonar o repositório e executar os seguintes comandos no terminal:
```bash
npm install
```
```bash
npm test
```

### Criado por: [Estevam Souza](https://github.com/estevam5s/)
