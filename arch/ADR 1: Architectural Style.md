# ADR 1: Estilo Arquitetural

- **ASSUNTO:** Racionalização sobre o estilo arquitetural a ser adotado pelo projeto.
- **DATA:** 29/04/2021

## **Contexto**

---

O projeto CLine tem como objetivo facilitar situações indesejáveis quanto ao tempo de espera de um paciente que muitas vezes passa horas em filas esperando por um atendimento.

Dessa forma, através da construção de uma aplicação, é buscado que as filas de diversas Clínicas possam ser monitoradas, evitando deslocamentos desnecessários e entregando um maior conforto e adaptabilidade ao usuário, de forma que ele possa:

- Visualizar a fila do atendimento de determinado médico da Clínica.
- Visualizar o possível tempo de espera, caso ele se cadastre naquele momento.
- Cadastrar suas informaçoes (plano, identidade) para ser inserido na fila.

Tudo isso sem precisar sair de casa.

A equipe CLine possui 2 desenvolvedores com uma disponibilidade de 30h/semana, sendo que o projeto deve ser entregue na data:

- **31/05/2021 ou 12/06/2021**.

Possuindo assim, um tempo relativo de praticamente 1 mês de arquiteturação e desenvolvimento.

Os desenvolvedores possuem experiência com linguagens como **nodeJs**, **typescript**, **flutter**, **express** e com desenvolvimento principalmente de API's e aplicações mobile/web.

## **Decisão**

---

- Vamos separar as duas camadas mais superficiais da nossa aplicação em um **Backend** e um **Frontend**.
- Backend:
  - Vamos utilizar a arquitetura de camadas **MVC (Model-View-Controller)**.
  - Vamos utilizar a linguagem nodeJs com Typescript.
- Frontend:
  - Vamos utilizar a arquitetura de camadas MVVM **(Model-View-ViewModel)**
  - Vamos utilizar o framework Flutter.

## **Justificativa**

---

- Desacoplamento **Back/Front**

  - Essa opção foi definida devido ao fato de que os desenvolvedores da equipe já possuem experiência em projetos dessa estrutura, tanto no desenvolvimento de API's como no processo de integração com um client de Frontend.

- Backend
  - Arquitetura MVC
    - MVC é uma arquitetura comumente conhecida pela sua aplicação na estruturação de sistemas de API, pois o problema de acoplamento para testes da View, que até então era resolvido pelo contrato View-Presenter, é completamente descartado para essa situação, ja que tal abstração é lidada pelo framework da API, nos deixando com as camadas de controller e models, desacoplados e testáveis.
    - Por ser uma arquitetura conhecida, a sua implementação pode ser dada de forma a se adequar ao tempo pequeno para entrega do projeto.
  - NodeJs e Typescript
    - São linguagens de domínio dos desenvolvedores da equipe, sem contar que o typescript fornece uma tipagem forte que previne erros e manutenção, além de features que facilitam a utilização do javascript através do paradigma de Orientação a Objeto.
- Frontend
  - Flutter
    - Framework de domínio dos desenvolvedores da equipe e utilizado principalmente para aplicações mobile, o que resolve a questão principal citada: `Tudo isso sem precisar sair de casa`.
  - Arquitetura MVVM
    - Devido a escolha do Flutter, temos bibliotecas que nos fornecem utilitários como o **StreamBuilder** que facilita a estruturação e utilização do **MVVM** e ao mesmo tempo resolve problemas como o **gerenciamento de estados**. Além disso, essa arquitetura fornece um desacoplamento em alto nível das camadas de View das camadas de Model, e uma camada completamente de baixo nivel, que é o ViewModel.

## **Status**

---

- Proposto

## **Consequências**

---

As consequências deverão ser definidas após a aplicação da decisão.
