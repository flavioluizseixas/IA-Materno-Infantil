# Tarefa 1

Nesta tarefa, você irá trabalhar com um DataFrame representando informações fictícias de pacientes em uma clínica de saúde. O objetivo é realizar algumas transformações nos dados e gerar um resumo de estatísticas para obter informações úteis sobre o estado de saúde dos pacientes.

## Objetivo:

- Criar um DataFrame a partir dos dados fornecidos no código.
- Realizar transformações nos dados, como filtrar informações e criar novas colunas.
- Calcular a média de uma variável relevante e gerar uma soma de uma outra variável.
- Interpretar os resultados e tirar conclusões sobre o grupo de pacientes.

## Instruções:
1. Criação do DataFrame:
- Você vai criar um DataFrame que contém informações de pacientes com as seguintes colunas:
    - Nome: Nome do paciente.
    - Idade: Idade do paciente.
    - Peso: Peso do paciente (em kg).
    - Altura: Altura do paciente (em metros).
    - Pressão Sistólica: Medida da pressão arterial sistólica (em mmHg).
    - Diagnóstico: Condição diagnosticada ("Hipertensão", "Normal").
    - Colesterol: Nível de colesterol total (mg/dL).
2. Transformações de Dados:
- Criar uma Coluna de IMC: Com base no peso e altura, calcule o Índice de Massa Corporal (IMC) para cada paciente e adicione uma nova coluna IMC ao DataFrame.
Fórmula do IMC: $$IMC=Peso/Altura^2$$
- Filtrar Pacientes com Hipertensão: Extraia apenas os pacientes com diagnóstico de hipertensão.
3. ​Cálculos e Resumo:
- Calcular a Média do IMC: Calcule a média do IMC dos pacientes com hipertensão.
- Somar o Colesterol: Calcule a soma dos níveis de colesterol de todos os pacientes.
4. Conclusão: Com base nos cálculos, tire conclusões sobre o grupo de pacientes analisado.