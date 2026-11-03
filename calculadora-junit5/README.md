# Calculadora — Java 17, JUnit 5 e Mockito

Projeto Maven baseado no tutorial fornecido.

## Requisitos
- JDK 17
- IntelliJ IDEA (ou outra IDE Java)
- Maven 3.9+ (opcional se usar o Maven integrado do IntelliJ)
- Internet no primeiro build para baixar as dependências

## Estrutura
- `Calculadora`: operações matemáticas básicas.
- `HistoricoOperacoes`: contrato para registrar operações.
- `CalculadoraService`: executa operações e registra os resultados.
- `HistoricoEmMemoria`: implementação simples do histórico.
- `App`: demonstração executável.
- `CalculadoraTest`: casos CT01 a CT05 com JUnit 5.
- `CalculadoraServiceTest`: casos CT06 a CT10 com Mockito.

## Executar
Na raiz do projeto:

```bash
mvn clean test
mvn clean package
```

Para executar a demonstração:

```bash
mvn compile
java -cp target/classes projeto.calculadora.App
```

No IntelliJ, abra a pasta do projeto, aguarde a sincronização Maven e execute `App` ou os testes pelos ícones verdes.

## Resultado esperado dos testes
10 testes executados, 0 falhas e 0 erros (`BUILD SUCCESS`).

## Plano de testes
Identificador: PT-CALC-001  
Objetivo: verificar as operações da calculadora e a integração do serviço com o histórico.

Escopo: soma, subtração, multiplicação, divisão, tratamento de divisão por zero e interações do serviço com o histórico.

Fora do escopo: persistência real em banco/arquivo/API, interface gráfica, desempenho, carga e segurança.

Ambiente: JDK 17, Maven 3.9+, JUnit Jupiter 5.14.4, Mockito 5.20.0 e IntelliJ IDEA.

Critérios de saída: todos os 10 casos executados e aprovados; `mvn clean package` finalizado com `BUILD SUCCESS`.

## Casos de teste
| ID | Cenário | Entrada | Resultado esperado |
|---|---|---|---|
| CT01 | Soma | `soma(1, 2)` | `3` |
| CT02 | Subtração | `sub(2, 1)` | `1` |
| CT03 | Multiplicação | `mult(4, 7)` | `28` |
| CT04 | Divisão exata | `divisao(12.0, 3.0)` | `4.0` |
| CT05 | Divisão por zero | `divisao(12.0, 0.0)` | `ArithmeticException` com mensagem definida |
| CT06 | Soma e registro | `somar(2, 3)` | Retorna `5` e registra `2 + 3` |
| CT07 | Registro único | `subtrair(10, 4)` | Registra uma vez `10 - 4` |
| CT08 | Argumentos do histórico | `multiplicar(4, 7)` | Captura `4 * 7` e `28.0` |
| CT09 | Divisão por zero no serviço | `dividir(12.0, 0.0)` | Propaga exceção e não registra |
| CT10 | Ordem das chamadas | `dividir(12.0, 3.0)` | Calcula antes de registrar |

## Registro de execução
Preencha esta tabela depois de executar os testes:

| ID | Data | Executor | Status | Evidência / observações |
|---|---|---|---|---|
| CT01 | | | | |
| CT02 | | | | |
| CT03 | | | | |
| CT04 | | | | |
| CT05 | | | | |
| CT06 | | | | |
| CT07 | | | | |
| CT08 | | | | |
| CT09 | | | | |
| CT10 | | | | |
