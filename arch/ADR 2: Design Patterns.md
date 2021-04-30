# ADR 2: Padrões de Projeto

- **ASSUNTO:** Racionalização sobre os padrões de projeto que devem ser utilizados.
- **DATA:** 30/04/2021

## **Contexto**

---

A aplicação exige muita **lógica de negócio** a ser tratada devido a complexidade da sua resolução, além da persistência dos dados para que as informações não sejam perdidas.

O projeto deve futuramente ser capaz de expandir, de forma a atingir uma grande quantidade de Clínicas associadas, o que traz a real necessidade de um sistema escalável mas que também leve em consideração um processo de desenvolvimento que se adeque ao tempo médio de entrega, ou seja, uma alternativa acessível que não insira complexidade desnecessária.

## **Decisão**

---

- Vamos utilizar o **Repository Pattern**.
- Backend:
  - Será utilizado o **Facade Pattern** também conhecido no mundo da API como a **Service Layer**, mas se aproximando mais da estrutura da **Service** do **DDD**, dessa forma, teremos um design baseado na ideia **Service - Repository**.
  - Vamos utilizar também o **Singleton Pattern**.
- Frontend:
  - Vamos utilizar o **Stream Pattern**.

## **Justificativa**

---

- Backend
  - Linguagens como nodeJs para o backend possuem diversos frameworks ORM que abstraem a camada do banco de dados e suas manipulações de forma a nos fornecer uma camada de Repositories pronta associada a cada model, o que torna o **Reposytory Pattern** um dos mais adequados para se trabalhar.
  - Como os repositories dos ORMs ja guardam lógicas de manipulação de entidades (modelo do banco de dados), a utilização de uma camada a mais que separe os controllers dos repositories pareceu-se necessária para o armazenamento da lógica de negócio mais complexa, usando assim a ideia do **Facade Pattern** .
  - Como foi dito, buscamos uma alternativa que `não insira complexidade desnecessária`. Visando isso, como os repositories ja possuem abstrações de lógica, a separação completa deles através da **Service Layer** tradicional adiciona nada mais, nesse momento, do que redundância e complexidade a algo que poderia ser evitado com um possível acesso aos repositories pelos próprios controllers, o que nos levou a optar pela ideia de **Services do DDD**.
  - O **Singleton Pattern** será utilizado devido a injeção de dependência dos repositories e serviçõs na camada de controller, visto que eles possuem comportamentos que não mudam durante toda aplicação.
- Frontend
  - Visando remover a lógica dos models do flutter, a utilização do **Repository Pattern** ajudaria na separação de funções, de forma a deixar o Model apenas com o que atribuições necessárias, migrando a lógica para os repositories.
  - Como o flutter vai ser o framework utilizado, temos acesso a libs como o **StreamBuilder** que facilitam a manipulaçao e criação de streams para lidar com o fluxo de dados **View - Model/Model - View/ View - API/ API -View**.

## **Status**

---

- [ ] Proposto
- [x] Aceito
- [ ] Depreciado
- [ ] Substituido

## **Consequências**

---

As consequências deverão ser definidas após a aplicação da decisão.
