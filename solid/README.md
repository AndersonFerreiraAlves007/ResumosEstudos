# SOLID

é uma junção de princípios e boas práticas que visam melhorar a arquitetura e design de um projeto.

## S - Single Responsibility Principle

Uma classe deve ter apenas um objetivo, apenas um função ou funções similares.

## O - Open-Closed Principle

As classes devem ser abertas para extensão, mas fechadas para modificações.

Alterar uma classe pai é perigoso, pois pode quebrar outras classes já feitas.

## L - Liskov Substitution Principle

As classes derivadas devem ser substituíveis pelas suas classes bases.

## I - Interface Segregation Principle

Classes não devem ser forçadas a depender de métodos que não usam.

## D - Dependency Inversion Principle

Módulos de alto nível não devem depender de módulos de baixo nível. Ambos devem depender da abstração.

Abstrações não devem depender de detalhes. Os detalhes devem depender das abstrações.

# Benefícios

## Segurança

As classes se tornam mais seguras graças a divisão de de responsabilidade e é mais difícil de ser quebradas.

## Manutenção

Com as responsabilidades divididas é mais fácil dar manutenção, principalmente se não foi você quem desenvolvel a aplicação.

## Reutilizável

Não é necessário reescrever o mesmo código para executar uma mesma tarefa.
