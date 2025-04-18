# DesafioControleFluxo

## DESAFIO PROPOSTO

Este projeto tem como objetivo exercitar o conteúdo apresentado no módulo de Controle de Fluxo por meio da codificação de um sistema simples, conforme o seguinte cenário:

O sistema deverá receber dois parâmetros via terminal que representarão dois números inteiros. Com esses dois números, você deverá:
- Calcular a quantidade de interações utilizando um loop `for`.
- Realizar a impressão no console (`System.out.print`) dos números incrementados, um por vez.

### Requisitos:
1. **Exemplo de funcionamento**:
   - Se os números fornecidos forem `12` e `30`, haverá uma interação com 18 ocorrências, exibindo:
     ```
     Imprimindo o número 1
     Imprimindo o número 2
     ...
     Imprimindo o número 18
     ```

2. **Validação**:
   - Caso o primeiro número seja maior que o segundo, o sistema deverá lançar uma exceção personalizada chamada `ParametrosInvalidosException`.
   - A exceção exibirá a mensagem: `"O segundo parâmetro deve ser maior que o primeiro"`.

### Estrutura do Projeto:
- O projeto possui duas classes:
  1. **Contador.java**: Responsável por receber os parâmetros, validar, e executar a lógica de contagem.
  2. **ParametrosInvalidosException.java**: Representa a exceção de negócio no sistema.

---

## ALTERAÇÕES REALIZADAS NO CÓDIGO

### **Classe Contador.java**
1. **Entrada de Dados**:
   - Incluída a utilização da classe `Scanner` para capturar os números inteiros do terminal.

2. **Validação dos Parâmetros**:
   - Implementado a lógica para verificar se o primeiro parâmetro é maior que o segundo. Caso seja, a exceção personalizada `ParametrosInvalidosException` é lançada:
     ```java
     if (parametroUm > parametroDois) {
         throw new ParametrosInvalidosException();
     }
     ```

3. **Tratamento de Exceções**:
   - Implementado um bloco `try-catch` para capturar e tratar a exceção personalizada, exibindo a mensagem apropriada:
     ```java
     try {
         contar(parametroUm, parametroDois);
     } catch (ParametrosInvalidosException exception) {
         System.out.println(exception.getMessage());
     }
     ```

4. **Criação do `for`**:
   - Criado o loop de contagem para que os números incrementados iniciem no valor `1` e terminem no total de interações, calculado como a diferença entre os dois parâmetros:
     ```java
     for (int i = 1; i <= contagem; i++) {
         System.out.println("Imprimindo o número " + i);
     }
     ```

### **Classe ParametrosInvalidosException.java**
1. **Definição da Mensagem**:
   - Criada a classe `ParametrosInvalidosException` com o construtor configurado para inicializar a mensagem corretamente ao utilizar o método `getMessage()`:
     ```java
     public class ParametrosInvalidosException extends Exception {
         public ParametrosInvalidosException() {
             super("O segundo parâmetro deve ser maior que o primeiro");
         }
     }
     ```

---

## INSTRUÇÕES PARA EXECUÇÃO

1. Clone o repositório ou copie os arquivos `Contador.java` e `ParametrosInvalidosException.java` para seu ambiente de desenvolvimento.
2. Compile o código utilizando o comando:
   ```
    javac Contador.java ParametrosInvalidosException.java
   ```
3. Execute o programa:
   ```
    java Contador
   ```
4. Insira os parâmetros solicitados e observe os resultados no console.



