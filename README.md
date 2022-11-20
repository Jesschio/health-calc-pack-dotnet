# health-calc-pack-dotnet
Biblioteca para Cálculos de Saúde (IMC e Macronutrientes) - Projeto do Curso de Pós-Graduação em Engenharia de Software da PUC-MG
# Diagrama do Projeto Health Calc Pack
A figura abaixo apresenta um diagrama com os requisitos funcionais e não funcionais, tecnologias e tabelas utilizados no projeto do Health Calc Pack:

<img src = "src\docshealthcalc\calc.png" alt = "healthcalcpack">

# Arquitetura

Utilizamos o padrão de arquitetura Onion, o qual divide a aplicação em três camadas (Domínio, Aplicação e Infraestrutura), sendo que cada camada possui sua própria responsabilidade.
Dessa forma, este modelo segue o seguinte princípio: "Nada em um círculo interno pode saber absolutamente nada sobre algo em um círculo externo. Isso inclui métodos, classes, variáveis ou qualquer outra entidade de software nomeada."  Robert C. Martin.
A camada de domínio contêm todas as regras de negócio do software que devem ser puramente lógicas, não realizando nenhuma operação de entrada ou saída.
Já a camada de aplicação é responsável por preparar o ambiente para seus modelos, a fim de que possam executar suas regras de negócio, ou seja, ela apenas chama métodos de objetos que implementam as interfaces que ela espera e esses objetos (da camada de infraestrutura) efetuam alguma operação de IO.
Por fim, a camada de infraestrutura é encarregada da implementação de todas as operações de entrada e saída necessárias para o software.

<img src = "src\docshealthcalc\onion.jpg" alt = "onion">

## Strategy Pattern

Strategy Pattern é um padrão de projeto comportamental, o qual permite que seja definida uma família de algoritmos, coloque-os em classes separadas e faça seus objetos intercambiáveis.
Sendo assim, o padrão sugere que seja dividido o algoritmo de uma classe principal em classes separadas (chamadas estratégias). 
A classe original, chamada contexto, deve conter um campo para armazenar uma referência para uma dessas estratégias. Então, quando o cliente passa a estratégia desejada para o contexto, este chama o método que irá acionar o algoritmo encapsulado dentro dela.
Dessa maneira, o contexto se torna independente das estratégias concretas, então torna-se possível adicionar novos algoritmos ou modificar os existentes sem modificar o código do contexto ou outras estratégias.

<img src = "src\docshealthcalc\estrutura.jpg" alt = "strategy"
