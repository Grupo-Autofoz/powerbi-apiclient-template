## Template do Client do PowerBI em Vue.js ( com documentação )
# AVISO: TEMPLATE DE INTEGRAÇÃO COM O POWERBI, NÃO É UM PROJETO, NÃO MEXER, SERVE APENAS COMO BASE DE CONHECIMENTO E LISTA DE DOCUMENTAÇÃO DA MICROSOFT

## Links úteis:
-> [Documentação Microsoft](https://learn.microsoft.com/en-us/rest/api/power-bi/): Contém toda as chamadas de API possíveis

-> [Repositório demo oficial da Microsoft](https://github.com/microsoft/powerbi-client-vue-js): Contém o código-fonte oficial do pacote para Vue.js chamado ```powerbi-client-vue-js``` juntamente com um exemplo de implantação (aviso: o exemplo é em JavaScript, portando é necessário adaptar em TypeScript)

-> [Vídeo ensinando a implementação em React.js](https://youtu.be/A5KFY5Jh1Uc): Mesmo usando uma tecnologia diferente do Vue.js, o tutorial ensina como conseguir todos os tokens necessários para as integrações usando o primeiro link informado nesse documento

## Informações importantes
- Os BI's devem estar dentro de um WORKSPACE para a API funcionar em plena capacidade, pois isso fornece o `groupId` usado como parametro em diversas chamadas

- Para gerar o token de integração master, deve ser em: [Reports GenerateTokenInGroup](https://learn.microsoft.com/en-us/rest/api/power-bi/embed-token/reports-generate-token-in-group), onde deverá ser informado:
  - Como Parametros:
    - O `groupId` do relatório, em que o usuário gerador do token deve ser administrador
    - O `reportId` do relaório
  - Como Body:
    - As opções dadas na própria página: `accessLevel` para o nível de acesso, `lifetimeMinutes` para o tempo de expiração do token (em minutos)
