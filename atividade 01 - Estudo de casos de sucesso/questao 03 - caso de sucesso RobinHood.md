# Estudo de Caso: Robinhood

> **Fonte:** https://aws.amazon.com/pt/solutions/case-studies/robinhood-case-study/

## Empresa
A Robinhood Markets, Inc. é uma empresa de serviços financeiros fundada em 2013, que fornece serviços de negociação e investimento para milhões de usuários. A plataforma é conhecida por democratizar as finanças para todos e pioneira na negociação de ações sem comissões.

## Desafio
Para manter sua plataforma segura e os usuários protegidos, a equipe de Crimes Financeiros (FinCrimes) da Robinhood monitora ativamente atividades suspeitas que possam indicar lavagem de dinheiro e outros crimes. O grande desafio era que, conforme o tráfego na plataforma aumentava, o número de alertas também crescia exponencialmente. 

Embora algumas partes do processo fossem automatizadas, grande parte da investigação permanecia manual. Os analistas precisavam revisar montanhas de dados estruturados e não estruturados para cada alerta gerado. A Robinhood precisava escalar rapidamente esses fluxos de trabalho de investigação de forma eficiente e em conformidade estrita com as regulamentações do setor e manter as proteções contra lavagem de dinheiro em dia.

## Por que usar a Amazon?
A Robinhood escolheu a Amazon Web Services (AWS) e especificamente o Amazon Bedrock pela necessidade de uma solução que combinasse Inteligência Artificial Generativa, escalabilidade para alto volume de alertas, e altíssimos padrões de segurança e controle.

A decisão foi tomada pelo fato de poder rodar os Modelos de Linguagem de Grande Escala (LLMs) dentro da sua própria Nuvem Privada Virtual (VPC - Virtual Private Cloud) operada pela AWS, garantindo que os dados sensíveis dos clientes nunca saíssem do seu controle. A confiabilidade, a segurança embutida, bem como a facilidade de orquestrar infraestrutura atrelada ao Amazon Bedrock validaram a escolha pela Amazon.

## Benefícios
- **Ganho de Eficiência de 20%**: A empresa alcançou cerca de 20% de ganho de eficiência cumulativa em seus fluxos de trabalho de rotina de investigação.
- **Redução do tempo de análise**: O tempo gasto na coleta, leitura e contextualização de dados processuais diminuiu drasticamente, uma vez que o agente de inteligência artificial assume a maior parte do trabalho braçal.
- **Precisão e Segurança**: com a validação robusta da arquitetura, os investigadores recebem sumários consistentes e de alta qualidade em que podem confiar verdadeiramente, com um mecanismo anti-alucinação aplicado a todas as respostas de IA geradas.
- **Preparação para o Futuro / Conformidade Regulatória**: A empresa estabeleceu a criação de um novo padrão (benchmark) na indústria para apoiar investigações de crimes financeiros de forma auditável e responsável através da IA.

## Arquitetura

Sobre a arquitetura não é falado em si como ela funciona, mas é falado dos rescursos usados e que a arquitetura implementada baseada em IA chama-se "FinCrimes Agent" (Agente de Crimes Financeiros). É um sistema em múltiplas camadas que combina a análise através de LLMs com orquestração altamente escalável na AWS. Os recursos usados destacados são:

- **Amazon Bedrock**: Usado para executar os modelos, na qual a Robinhood utiliza o modelo Claude da Anthropic (Haiku e Sonnet) assim como o DeepSeek. Modelos diferentes também são escolhidos para tarefas diferentes, visando o melhor custo-benefício, acurácia e performance. O serviço gerenciado foi primário no contexto da VPC.
- **Amazon RDS (Relational Database Service)**: A solução utiliza este banco de dados relacional para gerenciar e persistir a fila de tarefas de comunicação assíncrona entre todos os agentes que perfazem a arquitetura. Ele orquestra os processos determinando sequências e ferramentas.
- **Orquestração Multi-Agente Assíncrona**: Quando um alerta é gerado pelo sistema transacional, o fluxo de detecção é iniciado. Vários agentes menores realizam tarefas especializadas de maneira independente.
- **Agentes de Validação e Feedback Loop (Humano e Sintético)**: Cada agente produtor de dados está pareado a um agente verificador. O fluxo do relatório analítico de crime só prossegue para a área do dashboard final quando o verificador atesta que a saída gerada não contém alucinações (hallucination check). O sistema salva logs de auditoria detalhados que são essenciais para as equipes de governança e adequação e, ao fim, mantém um **humano no ciclo de vida** para ratificar ou não as tomadas de decisão.
