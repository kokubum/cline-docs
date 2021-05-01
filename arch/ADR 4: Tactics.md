# ADR 2: Padrões de Projeto

- **ASSUNTO:** Racionalização sobre as táticas que devem ser utilizadas.
- **DATA:** 01/05/2021

## **Contexto**

---

As táticas são decisões de design relacionadas aos atributos de qualidade. As táticas contribuem para que se tenha maior êxito na tentativa de alcançar os atributos de
qualidade desejados na aplicação.

## **Decisão**

---

- Backend:
  - Para o atributo de **performance** vamos focar em diminuir a sobrecarga no processamento e administrar a quantidade de requisições feitas.
  - Para o atributo de **segurança** iremos verificar se o usuário que está realizando a requisição é válido e também encriptar os dados sensíveis.
- Frontend:
  - Para o atributo de **modificabilidade** iremos separar a aplicação em módulos.

## **Justificativa**

---

- Backend:
  - Diminuindo a sobrecarga no processamento conseguimos levar uma resposta para o usuário de forma mais rápida e eficaz, e administrando a quantidade de requisições feitas
  possibilita que não tenhamos uma fila de requisições o que ajuda a não ter atraso nas respostas e nem sobrecarregarmos o servidor com requisições desnecessárias.
  - Verificando a validade do usuário com o nosso banco de dados possibilita que os usuários sem acesso à aplicação não extraia informações do nosso banco de dados e a
  encriptação dos dados sensíveis ajuda a manter o sigilo dos dados salvos no nosso banco.
- Frontend:
  - Separando a aplicação em módulos teremos diferentes partes da aplicação habilitadas dependendo do tipo de usuário logado, dessa forma há uma maior facilidade adaptar a 
  aplicação para a clínica utilizar ou para o paciente utilizar.

## **Status**

---

- [ ] Proposto
- [x] Aceito
- [ ] Depreciado
- [ ] Substituido

## **Consequências**

---

As consequências deverão ser definidas após a aplicação da decisão.
