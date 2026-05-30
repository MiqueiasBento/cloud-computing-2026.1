# Relatório: Laboratório 6 - Ajuste a escala e o balanceamento de carga da arquitetura

Relatório descrevendo as atividades executadas no laboratório focado na implementação de Auto Scaling e Monitoramento(Módulo 10), utilizando Application Load Balancer (ALB) e Auto Scaling Groups.

---

## Registros

![Estrutura inicial e objetivo final](./registros/1-estrutura-inicial-e-objetivo-final.png)
Visualização do diagrama da arquitetura proposta para a implementação de balanceamento de carga e auto-scaling.

![Criando imagem da instância](./registros/2-criando-imagem-da-instancia.png)
Criei uma Amazon Machine Image (AMI) personalizada a partir de uma instância EC2 configurada previamente.

![Criação e configuração do grupo de destino](./registros/3-criacao-e-configuracao-grupo-de-destino.png)
Criei e configurei um grupo de destino (Target Group) para gerenciar e direcionar o tráfego do balanceador.

![Balanceador de cargas criado](./registros/4-balanceador-de-cargas-criado.png)
Criei um Application Load Balancer (ALB) para distribuir as conexões de entrada entre as zonas de disponibilidade.

![Criando modelo de execução](./registros/5-criando-modelo-de-execução.png)
Configurei o modelo de execução (Launch Template) contendo os parâmetros de hardware, rede e a AMI gerada.

![Grupo de auto scaling configurado](./registros/6-grupo-de-auto-scaling-configurado.png)
Criei o Auto Scaling Group vinculando as sub-redes e especificando os limites mínimo, desejado e máximo.

![Instâncias iniciadas pelo auto scaling](./registros/7-instâncias-iniciadas-pelo-auto-scaling.png)
Verificação da ativação e a inicialização automática das instâncias EC2 pelo serviço de escalabilidade.

![Instâncias iniciadas com teste de carga](./registros/8-instancias-iniciadas-com-teste-de-carga.png)
Monitoramento da escala horizontal e a criação de instâncias adicionais após a aplicação de estresse de carga na CPU.

![Finalizando encerrando a instância](./registros/9-finalizando-encerrando-a-instancia.png)
Desligamento manual dos recursos para validar a recuperação automática e a política de redução da infraestrutura.

![Resultado final](./registros/10-resultado-final.png)
Finalização do lab e pontuação recebida.
