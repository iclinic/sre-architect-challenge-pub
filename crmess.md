# CRMess

[![Test](https://github.com/iclinic/sre-architect-challenge-crmess-service/actions/workflows/test.yml/badge.svg?branch=main)](https://github.com/iclinic/sre-architect-challenge-crmess-service/actions/workflows/test.yml)
[![Coverage Status](https://coveralls.io/repos/github/iclinic/sre-architect-challenge-crmess-service/badge.svg?branch=main&t=uFYJ25)](https://coveralls.io/github/iclinic/sre-architect-challenge-crmess-service?branch=main)

Este serviço visa simular uma API instável de terceiros para o desafio
[CRMess](https://github.com/iclinic/sre-architect-challenge-pub).

Utilize o **CRMess** através da imagem docker `deviclinic/sre-tests-crmess`.

Exemplo de configuração do serviço utilizando `docker-compose`:

```yaml
version: '3.9'

services:
  crmess:
    image: deviclinic/sre-tests-crmess
    environment:
      CRMESS_PORT: '4000'
      CRMESS_HOSTNAME: localhost
      CRMESS_VALID_LIST: '1,2,3,4,5'
      CRMESS_INVALID_LIST: '6,7,8,9,10'
      CRMESS_NORMAL_PERCENTAGE: '100'
      CRMESS_HOLD_PERCENTAGE: '0'
      CRMESS_ERROR_PERCENTAGE: '0'
    ports:
      - 4000:4000
```

## Rotas

- `/v1/crm/validate/:crm` - Rota para validação de CRM
  - Parâmetros:
    - `:crm` - Um identificador único qualquer
  - Possíveis respostas:
    - Normal - Responderá de acordo com o esperado:
      - Válido - CRM está na lista de CRMs válidos (`200`):
        ```json
        {"result": "valid"}
        ```
      - Inválido - CRM está na lista de CRMs inválidos (`200`):
        ```json
        {"result": "invalid"}
        ```
      - Não encontrado - CRM não está na lista de CRMs válidos e inválidos
        (`404`):
        ```json
        {"result": "not_found"}
        ```

    - Travada - Não responderá nunca
    - Erro - Responderá de forma inesperada

- `/settings` - Rota para configuração do serviço
  - Funcionalidades:
    - Adicionar e remover CRM da lista de CRMs válidos
    - Adicionar e remover CRM da lista de CRMs inválidos
    - Alterar o percentual de ocorrências para respostas do tipo Normal,
      Travada (`hold`) e de Erro (`error`)

## Variáveis de Ambiente

- `CRMESS_PORT` - Altera a porta do servidor. Valor padrão: `4000`
- `CRMESS_HOSTNAME` - Altera o nome do servidor. Valor padrão: `localhost`
- `CRMESS_VALID_LIST` - Adiciona CRMs na lista de CRMs válidos. Valores devem
  ser separados com vírgula
- `CRMESS_INVALID_LIST` - Adiciona CRMs na lista de CRMs inválidos. Valores
  devem ser separados com vírgula
- `CRMESS_NORMAL_PERCENTAGE` - Percentual de requisições que devem receber uma
  resposta "Normal". Valor padrão: `100`
- `CRMESS_HOLD_PERCENTAGE` - Percentual de requisições que devem receber uma
  resposta "Travada". Valor padrão: `0`
- `CRMESS_ERROR_PERCENTAGE` - Percentual de requisições que devem receber uma
  resposta de "Erro". Valor padrão: `0`