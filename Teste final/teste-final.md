# Teste final AWS Academy Foundations

---

1. Qual requisito de TI levaria um arquiteto a escolher um modelo de serviço de nuvem de infraestrutura como serviço (laaS)?
* Uma empresa deseja manter o controle de suas aplicações mas evitar a manutenção de servidores e sistemas operacionais.
* **Uma empresa deseja manter o maior nível de flexibilidade sobre seus recursos de TI.**
* Uma empresa deseja executar uma instância gerenciada para o marketplace.
* Uma empresa deseja usar uma solução de e-mail baseada na Web.

> Justificativa: O modelo IaaS oferece o maior nível de controle e gerenciamento sobre os recursos de computação, armazenamento e rede. As outras opções descrevem modelos como PaaS (evitar manutenção de SO) ou SaaS (e-mail na Web), que tiram essa flexibilidade do cliente.

---

2. Como as economias de escala ajudam os clientes a migrar da computação on-premises para a computação em nuvem?
* Os clientes podem implantar recursos globalmente.
* Os clientes têm controle total da infraestrutura.
* **Os clientes podem alcançar custos variáveis mais baixos e dimensionar infraestrutura além do possível on-premises.**
* Os clientes podem dimensionar servidores horizontalmente.

> Justificativa: Como a AWS agrega o uso de centenas de milhares de clientes, ela consegue adquirir recursos em massa por custos muito menores, repassando essa economia na forma de preços variáveis reduzidos. Isso é o que a AWS chama de "beneficiar-se de economias de escala massivas".

---

3. Qual declaração descreve com precisão os preços da AWS?
* As empresas devem assinar um contrato de longo prazo para poder pagar apenas pelo que usam.
* Transferências de dados de saída não são cobradas.
* **Descontos baseados em volume estão disponíveis quando o uso aumenta (em alguns serviços).**
* As empresas podem reservar capacidade para alguns serviços, mas isso não afeta o custo.

> Justificativa: Serviços como o Amazon S3 e o EC2 oferecem preços em camadas, onde o custo por gigabyte ou por transferência diminui à medida que o seu volume de uso aumenta. As outras alternativas estão erradas porque a AWS não exige contratos de longo prazo para o "pague pelo que usar", cobra por dados de saída e reservas reduzem custos drasticamente.

---

4. Um profissional de nuvem deseja visualizar seus custos da AWS por tipo de instância do EC2 nos últimos três meses. Qual ferramenta ou recurso da AWS deve ser usado?
* Calculadora de Preços da AWS
* **AWS Cost Explorer**
* Página do AWS Bills
* AWS Budgets

> Justificativa: O Cost Explorer permite visualizar, analisar e filtrar graficamente seus custos históricos e uso detalhado por até 12 meses atrás. Você pode agrupar os dados especificamente por dimensão, como o tipo de instância do EC2, para identificar tendências.

---

5. Qual declaração sobre locais de borda é verdadeira?
* Os caches de borda regionais são usados para armazenar dados em cache que são atualizados com frequência e devem ser atualizados continuamente.
* Os pontos de presença da AWS fornecem de dois a três locais de borda por Região.
* A rede global da AWS inclui um grande número de caches de borda regionais e um número menor de locais de borda para entregar conteúdo aos usuários.
* **O Amazon CloudFront usa locais de borda e caches de borda regionais para entregar conteúdo com menor latência.**

> Justificativa: O CloudFront combina locais de borda (Edge Locations) mais próximos dos usuários com caches regionais (que guardam volumes maiores de dados) para otimizar a entrega global e reduzir a latência. A alternativa sobre a rede global inverte os conceitos, pois na verdade existem mais locais de borda do que caches regionais.

---

6. Um administrador de conta da AWS deseja conceder acesso temporário entre contas que permite que usuários externos acessem recursos específicos em sua própria conta. Qual ação se alinharia com a prática recomendada do uso de sessões temporárias?
* **Criar uma função do AWS Identity and Access Management (AWS IAM) que possa ser assumida por usuários externos e conceda permissões para recursos específicos.**
* Criar um grupo do AWS Identity and Access Management (AWS IAM), conceder permissões de recursos e, em seguida, adicionar usuários do IAM ao grupo.
* Criar uma nova conta de usuário do AWS Identity and Access Management (AWS IAM) para cada usuário que precisar de acesso.
* Criar uma política do AWS Identity and Access Management (AWS IAM) que permita que usuários externos acessem recursos específicos.

> Justificativa: As funções (Roles) do IAM são o mecanismo padrão da AWS para delegar acesso temporário e seguro a usuários externos (cross-account) sem a necessidade de criar credenciais de longo prazo ou usuários permanentes.

---

7. Uma empresa deve gerar relatórios de quaisquer alterações em suas configurações da instância do Amazon EC2. Qual serviço da AWS deve ser usado?
* AWS CloudTrail
* **AWS Config**
* Amazon CloudWatch
* AWS Artifact

>Justificativa: O AWS Config é o serviço específico para monitorar, registrar e avaliar continuamente as alterações de configuração dos seus recursos da AWS. O CloudTrail registra ações e histórico de chamadas de API, enquanto o Config foca no estado do recurso ao longo do tempo.

---

8. Um administrador de redes deseja configurar uma sub-rede pública e rotear o tráfego de entrada e saída de e para uma instância do Amazon EC2 na sub-rede pública para a internet pública. Qual recurso da nuvem privada virtual (VPC) deve ser usado?
* O Compartilhamento da VPC
* Um gateway de Network Address Translation (NAT)
* **Um gateway de internet**
* Uma lista de controle de acesso (ACL) à rede

> Justificativa: Para que uma sub-rede seja considerada pública, ela obrigatoriamente precisa de uma tabela de rotas conectada a um Internet Gateway (IGW) para permitir comunicação bidirecional com a internet. O gateway NAT serve apenas para tráfego de saída vindo de sub-redes privadas.

---

9. Qual requisito sugere configurar o Amazon Route 53 com roteamento de latência?
* Uma empresa deseja detectar interrupções de site e redirecionar automaticamente os clientes para um local íntegro.
* Uma empresa deseja executar testes A/B e rotear tráfego para locais diferentes com base em uma porcentagem de tráfego.
* Uma empresa deseja rotear tráfego somente para locais onde tenha direitos de distribuição.
* **Uma empresa deseja rotear tráfego para a Região que proporciona a experiência mais rápida com base em medições de desempenho.**

> Justificativa: O roteamento por latência direciona as requisições dos usuários para a região da AWS que apresentar o menor atraso de rede (menor latência) para aquele usuário específico. As outras opções descrevem roteamento por política de failover (detecção de interrupções), ponderado (testes A/B) ou geolocalização.

---

10. Um desenvolvedor está testando um protótipo no Amazon EC2. As instâncias são terminadas após os testes, mas a aplicação requer computação ininterrupta durante o processamento. Qual tipo de preço de instância do Amazon EC2 atende à necessidade com o menor custo?
* **Instância sob demanda**
* Instância reservada programada
* Instância spot
* Instância reservada

> Justificativa: Como o processamento precisa ser ininterrupto e o ambiente é de testes pontuais (sem compromisso de longo prazo), as instâncias Sob Demanda (On-Demand) oferecem o menor custo sem risco de interrupção. As instâncias Spot seriam mais baratas, mas não garantem computação ininterrupta, pois a AWS pode recuperá-las a qualquer momento.

---

11. Um desenvolvedor precisa de armazenamento temporário em bloco para dados em cache em uma instância do Amazon EC2. Qual opção deve ser escolhida?
* **Armazenamento de instâncias do Amazon EC2**
* Amazon S3
* Amazon Elastic Block Store (Amazon EBS)
* Amazon Elastic File System (Amazon EFS)

> Justificativa: O Instance Store oferece armazenamento em bloco temporário (efêmero) fisicamente anexado ao servidor de hospedagem, sendo ideal para caches, buffers e dados temporários de altíssima velocidade. O EBS também é armazenamento em bloco, mas é persistente e sobrevive à interrupção da instância, tornando o Instance Store a escolha mais econômica e específica para caches voláteis.

---

12. Qual cenário é adequado para o armazenamento do Amazon Elastic File System (Amazon EFS)?
* Uma empresa deseja desenvolver um data lake do tamanho de um petabyte para analytics.
* **Uma empresa precisa conceder acesso de leitura e gravação a um sistema de arquivo de rede (NFS) a todas as instâncias do Amazon EC2 em sua nuvem privada virtual (VPC).**
* Uma empresa deseja hospedar um site.
* Uma empresa precisa de armazenamento temporário de arquivos para suas aplicações em execução no Amazon EC2.

> Justificativa: O Amazon EFS é um serviço de sistema de arquivos Linux totalmente gerenciado que suporta o protocolo NFSv4, permitindo que centenas de instâncias EC2 compartilhem e acessem simultaneamente os mesmos dados armazenados.

---

13. Uma empresa faz upload de formulários PDF no Amazon S3 que precisam ser retidos
por um ano. Os formulários raramente são acessados depois de uma semana, mas precisam estar disponíveis dentro de um dia quando solicitados. Qual política de ciclo de vida é a mais econômica para suas necessidades?
* Mover objetos do Amazon S3 Standard para o Amazon S3 Standard - Infrequent Access depois de sete dias.
* Mover objetos do Amazon S3 Standard para o Amazon S3 One Zone-Infrequent Access depois de sete dias. Excluir os objetos depois de 365 dias.
* **Mover objetos do Amazon S3 Standard para o Amazon S3 Glacier depois de sete dias. Excluí-los depois de 365 dias.**
* Mover objetos do Amazon Standard-Infrequent Access para o Amazon S3 Standard depois de uma semana.

> Justificativa: O Glacier é a classe de armazenamento de arquivamento de mais baixo custo, ideal para dados raramente acessados que toleram um tempo de recuperação de algumas horas (atendendo ao requisito de "disponível dentro de um dia"). A regra também cumpre o ciclo de vida completo ao deletar os arquivos após o período obrigatório de 1 ano (365 dias).

---

14. Qual cenário descreve um bom caso de uso para o armazenamento do Amazon S3 Standard?
* **Hospedar imagens de sites.**
* Compartilhar um sistema de arquivos NFS.
* Atuar como um armazenamento de instância do EC2.
* Executar um banco de dados relacional.

> Justificativa: O S3 Standard foi projetado para dados de alta disponibilidade e acesso frequente, sendo perfeito para servir ativos estáticos da web, como imagens e vídeos. Ele não pode ser usado como banco de dados relacional (requer EBS/RDS) ou sistema NFS (requer EFS).

---

15. Qual recurso do Amazon RDS uma empresa deve configurar para ativar alta disponibilidade?
* Armazenamento de IOPS provisionado.
* **Implantação multi-AZ.**
* O Criptografia com chaves do AWS Key Management Service (AWS KMS).
* Implantação de nuvem privada virtual (VPC).

> Justificativa: A implantação Multi-AZ (Multi-Availability Zone) replica de forma síncrona os dados do seu banco de dados para uma instância secundária em uma zona de disponibilidade diferente. Caso a instância primária falhe, o RDS realiza um failover automático para a secundária, garantindo alta disponibilidade e tolerância a falhas.

---

16. Qual cenário melhor descreve um caso de uso para o Amazon Aurora?
* Uma empresa precisa executar um banco de dados da Oracle na nuvem.
* Uma empresa precisa de um banco de dados para armazenar dados semiestruturados.
* **Uma empresa precisa de um banco de dados altamente disponível compatível com PostgreSQL.**
* Uma empresa precisa de um data warehouse que possa ser consultado usando ferramentas padrão de business intelligence.

> Justificativa: O Amazon Aurora é um banco de dados relacional proprietário da AWS que foi desenvolvido especificamente para ser totalmente compatível com MySQL e PostgreSQL, oferecendo desempenho e disponibilidade até 3 vezes superior aos bancos tradicionais de código aberto.

---

17. Qual declaração reflete um princípio de design do pilar de segurança do AWS Well- Architected Framework?
* Não implantar uma solução para produção até ter certeza de que não há riscos de segurança.
* Descentralizar o gerenciamento de permissões.
* Garantir que a equipe está monitorando ativamente os riscos potenciais de forma manual.
* **Aplicar segurança em todas as camadas de uma arquitetura.**

> Justificativa: O princípio da "segurança em todas as camadas" (também conhecido como Defesa em Profundidade) defende que você deve proteger seus recursos não apenas no perímetro da rede, mas também nas instâncias, nos sistemas operacionais, no armazenamento e na própria aplicação. As outras opções estão incorretas porque o gerenciamento de permissões deve ser centralizado e os processos de monitoramento e proteção contra riscos devem ser automatizados ao máximo, em vez de manuais.

---

18. Que tipo de alerta pode ser emitido pelo AWS Trusted Advisor?
* **Um alerta de que a autenticação multifator (MFA) não está ativada em uma conta da AWS.**
* Um alerta de que um usuário do AWS Identity and Access Management (AWS IAM) solicitou alterações na cota de serviço.
* Um alerta de chamadas de API incomuns feitas em uma conta da AWS.
* Um alerta de acesso não autorizado em uma conta da AWS.

> Justificativa: O AWS Trusted Advisor analisa sua infraestrutura e fornece recomendações em tempo real seguindo as melhores práticas da AWS, incluindo uma verificação de segurança crucial que avisa se o MFA não estiver ativado no usuário Root da conta. Alertas de chamadas de API incomuns ou acessos não autorizados são de responsabilidade de serviços de segurança e monitoramento como o AWS CloudTrail e o Amazon GuardDuty.

---

19. Qual cenário deve ser tratado com um Network Load Balancer?
* Uma solução deve oferecer suporte ao roteamento de tráfego para uma aplicação em contêiner com base no conteúdo das solicitações recebidas.
* Uma solução deve balancear a carga das solicitações gRPC recebidas.
* Uma solução deve rotear o tráfego na camada 7 do modelo de interconexão de sistemas abertos (OSI).
* **Uma solução deve balancear a carga de milhões de solicitações por segundo, mantendo baixas latências.**

> Justificativa: O Network Load Balancer (NLB) opera na Camada 4 (Transporte) do modelo OSI e foi projetado especificamente para lidar com volumes massivos de tráfego (milhões de requisições por segundo) com ultra-baixa latência usando conexões TCP/UDP. O roteamento com base no conteúdo da solicitação e o suporte a gRPC na Camada 7 são características exclusivas do Application Load Balancer (ALB).

---

20. Qual declaração sobre o AWS Auto Scaling é verdadeira?
* O AWS Auto Scaling e o Amazon EC2 Auto Scaling são sinônimos.
**O AWS Auto Scaling pode ser usado para dimensionar automaticamente as tabelas e os índices do Amazon DynamoDB.**
* Você pode usar o Amazon EC2 Auto Scaling ou o AWS Auto Scaling, mas não os dois juntos.
* O AWS Auto Scaling pode ser usado para dimensionar automaticamente os bancos de dados do Amazon RDS.

> Justificativa: Enquanto o Amazon EC2 Auto Scaling lida estritamente com grupos de instâncias virtuais, o AWS Auto Scaling é uma ferramenta abrangente e unificada que gerencia o dimensionamento automático de múltiplos recursos de diferentes serviços da AWS, incluindo a capacidade de leitura/gravação de tabelas e índices globais do DynamoDB, réplicas do Aurora e tarefas do ECS.
