# Relatório: Atividade Lab - AWS Lambda

Atividade laboratório focada no serviço AWS Lambda, abordando desde a criação da função até a configuração de gatilhos e implementação de código.

## Relatos

A execução deste lab se complicou por algumas operações não serem de forma clara ou seguindo o mesmo fluxo que era indicado na instrução, sendo necessários ajustes pontuais em permissões de segurança para a correta inicialização dos recursos, um desses problemas foi a configuração de Role, mas uma vez resolvidas as pendências de configuração de Role, o processo de deploy e teste das funções seguiu conforme já estava instruído, permitindo a validação da lógica implementada e a integração com gatilhos de eventos.

---

## Execução Realizada

![Iniciando criação da Lambda function](./registros-lab-lambda/1-iniciando-criacao-lambda-function.png)
Início do provisionamento da função Lambda no console da AWS, com a definição do ambiente de execução e configurações básicas de acesso.

![Problema para criar função](./registros-lab-lambda/2-problema-para-criar-funcao.png)
Identificação de um impedimento durante a criação da função devido a inconsistências nas permissões de Role atribuídas.

![Configuração de Role faltante](./registros-lab-lambda/3-configuracao-de-role-que-faltava.png)
Realização do ajuste manual nas políticas do IAM, assegurando que a função possuísse os privilégios necessários para sua execução.

![Lambda criada com sucesso](./registros-lab-lambda/4-lambda-criada-sucesso.png)
Confirmação da criação da função após as correções de segurança, apresentando o ambiente pronto para o desenvolvimento do código.

![Configurando gatilho](./registros-lab-lambda/5-configurando-gatilho.png)
Associação de gatilhos à função para automação do disparo baseado em eventos específicos do ambiente AWS.

![Codificando a função Lambda](./registros-lab-lambda/6-codificando-lambda-function.png)
Implementação da lógica de negócio através do editor de código integrado, seguida da configuração dos parâmetros de teste.

![Função Lambda atualizada](./registros-lab-lambda/7-funcao-lambda-atualizada.png)
Efetivação do deploy da nova versão do código, registrando a atualização bem-sucedida da função no ambiente de computação sem servidor.

![Verificação de recursos](./registros-lab-lambda/8-instancia%20interrompida.png)
Monitoramento do comportamento dos recursos computacionais durante os ciclos de execução e testes da função.

![Pontuação final](./registros-lab-lambda/pontuacao-final.png)
Registro da conclusão total das etapas propostas, com a pontuação final pelo laboratório.
