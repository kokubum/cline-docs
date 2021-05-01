# ADR 3: Atributos de Qualidade

- **ASSUNTO:** Racionalização sobre os atributos de qualidade adotados pelo projeto.
- **DATA:** 01/05/2021

## **Contexto**

---

Os atributos de qualidade são propriedades de um software que podem ser medidos e testados, por essas características ele pode definir o quão bem o nosso software é capaz de 
solucionar determinado problema.

## **Decisão**

---

- Backend:
  - Deveremos oferecer uma alta **performance**.
  - Deveremos oferecer **segurança** no manuseio dos dados.
  
- Frontend:
  - O sistema deve ser **modificável**.
  
## **Justificativa**
   
---
  
- Backend:
  - **Performance:** Pois no momento em que o usuário acessa a nossa aplicação ele deseja saber como está a situação daquela fila no momento em que ele está acessando, qualquer 
  tipo de atraso na resposta de uma ação do usuário pode resultar em informações divergentes da situação da fila.
  - **Segurança:**  É um atributo fundamental na aplicação pois lidamos com dados sensíveis do cliente como documentos pessoais e dados relacionados ao convênio médico do 
  usuário.
- Frontend:
  - **Modificabilidade:** Nossa solução está disponível tanto para pacientes quanto para clínicas que são os dois tipos de usuários de nossa aplicação e essa
  diferenciação no tipo de usuário exige que nosso sistema se modifique dependendo de qual usuário está acessando.
  
## **Status**

---

- [ ] Proposto
- [x] Aceito
- [ ] Depreciado
- [ ] Substituido

## **Consequências**

---

As consequências deverão ser definidas após a aplicação da decisão.
