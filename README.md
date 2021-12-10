# iClinic - Desafio SRE Arquiteto

Olá, pessoa arquiteta, bem-vinda ao desafio **CRMess**!

Antes de mais nada, gostaríamos de informar que priorizamos o seu bem-estar e o
seu tempo.

Acreditamos que a abordagem de oferecer um desafio é uma ótima forma de
conhecermos melhor como você atua como profissional. Além disso, com o desafio
você poderá mostrar toda a sua expertise com maior liberdade de contexto e
abordagem.

Entretanto, realizar um desafio pode consumir muito tempo e esforço se feito sem
parcimônia. Por isso, o desafio não deve afetar seu trabalho atual e/ou seu
momento de descanso e lazer. Planeje tal desenvolvimento, garantindo que você
consiga realizar um ótimo desafio de forma saudável e eficiente.

Para avaliarmos sua capacidade técnica, criamos um cenário fictício onde você é
uma pessoa arquiteta responsável por desenvolver uma prova de conceito.

Esta prova de conceito será apresentada por você para:

- Uma pessoa cliente que tem grande interesse em investir no projeto;
- Uma pessoa engenheira que irá avaliar a arquitetura do projeto e a qualidade
  do produto.

Para você se sair bem, leia atentamente este documento, desenvolva uma prova de
conceito que satisfaça os requisitos, utilizando de toda a sua expertise para
produzir um produto de alta qualidade.

Em caso de dúvidas, entre em contato.

Bom desafio!

## Parte 1: O projeto

Existe um sistema que valida o CRM de um médico para autenticar prescrições
médicas. Tal sistema, chamado de **CRMess**, é oferecido através de uma API REST
externa que costuma falhar, cair ou travar.

Infelizmente, **CRMess** é a única plataforma existente que consegue autenticar
CRM.

Após várias reuniões com _stakeholders_, você, como pessoa arquiteta, ficou
encarregada de desenvolver uma prova de conceito de um produto que permita
realizar e monitorar solicitações de validação de CRM através de uma API REST.

Uma pessoa cliente, dona de uma empresa parceira, tem grande interesse no
produto, pois o sistema desta empresa sofre com a instabilidade do **CRMess**.
Tal pessoa irá analisar sua prova de conceito com o objetivo de investir no
projeto caso a prova de conceito satisfaça os requisitos de negócio da empresa
dela.

Uma pessoa engenheira da empresa que você trabalha irá analisar sua prova de
conceito com o objetivo de confirmar se a prova de conceito satisfaz os
requisitos técnicos mínimos para viabilizar o projeto em larga escala.

### Requisitos de negócio

O sistema:

- Deve ser capaz de receber uma solicitação de validação de CRM;

- Deve ser capaz de apresentar o estado de uma solicitação;

- Deve ter apenas uma solicitação ativa por CRM;

- Deve ser capaz de se comunicar com o **CRMess** de forma que, eventualmente,
  consiga validar o CRM;

- Se CRM for válido, este deverá ser mantido pelo sistema por 7 dias;

- Se CRM válido já está sendo mantido pelo sistema, o sistema não deve se
  comunicar com o **CRMess**.

### Requisitos técnicos

Características:

- Deve ser composto por um ou mais microsserviços;

- Deve ser escalável horizontalmente e verticalmente;

- Deve ser amplamente configurável via variável de ambiente;

- Deve ser uma API REST JSON;

- Deve ser desenvolvido completamente em inglês.

Boas práticas:

- Clareza na estrutura do projeto, no código e nos testes;

- Testes devem focar em validar o comportamento do sistema;

- Usar ferramentas automatizadas de code styling e linting;

- Evitar erros de grafia;

- Deve existir uma documentação explicando as características técnicas do
  projeto;

- Deve existir uma documentação explicando como preparar o ambiente de
  desenvolvimento localmente;

- Deve existir uma documentação explicando como realizar os testes;

- Deve existir uma documentação explicando como subir o ambiente de produção.

Restrições:

- Não recomendamos o user de boilerplates e generators. Caso utilize, isole o
  gerador e/ou o boilerplate em um commit e apresente a diferença entre a
  estrutura inicial e as modificações que você implementou.

### Serviço CRMess

Para mais informações, acesse:
<https://github.com/iclinic/sre-architect-challenge-crmess-service/blob/main/README.md>

## Parte 2: A apresentação

Após o desenvolvimento, agende a apresentação e prepare-se de acordo com as
seguintes instruções:

- Inicie a apresentação priorizando a pessoa cliente:

  - Como utilizar o sistema;

  - O que o sistema resolve;

  - O que o sistema tem de melhor;

  - Quais seriam os próximos passos do projeto, se aceito;

  - Em um tempo máximo de 10 minutos de apresentação.

- Posteriormente, priorize a pessoa engenheira:

  - _Show me the code_: Apresente e descreva o projeto, o código, os testes,
    etc. Descreva ao longo da apresentação sua linha de raciocínio de forma a
    justificar suas decisões de desenvolvimento;

  - Testes automatizados: Rode a suíte de testes e apresente métricas de
    qualidade;

  - _What if_: Apresente o comportamento do sistema em casos especiais;

  - Em um tempo máximo de 20 minutos de apresentação.

- Após 30 minutos, a apresentação será obrigatoriamente encerrada.

Após a apresentação, as pessoas entrevistadoras irão realizar o _feedback_:

- Do ponto de vista da pessoa cliente:

  - Se o sistema satisfaz os requisitos de negócio;

  - Se a apresentação motivou um aceite do projeto.

- Do ponto de vista da pessoa engenheira:

  - Se o sistema satisfaz os requisitos técnicos;

  - Se a apresentação descreve bem as características técnicas do projeto.

Após o _feedback_, as pessoas entrevistadoras irão questionar detalhes técnicos
de sua implementação visando avaliar sua abordagem e suas competências técnicas.
