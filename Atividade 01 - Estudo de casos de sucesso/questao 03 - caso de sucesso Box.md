# Estudo de Caso: Box

> **Fonte**: https://aws.amazon.com/pt/solutions/case-studies/box-case-study/

## Empresa

A Box é uma empresa global de soluções e serviços em nuvem inteiramente focada no compartilhamento seguro de arquivos empresariais, colaboração de equipes remotas de trabalho e gerenciamento de conteúdo ágil (gestão documental) dentro de amplas organizações e corporações corporativas.

## Desafio

Tendo em vista o contínuo impulsionamento dos modelos de trabalho distribuídos e remotos (home office e híbrido em grande volume no mundo pós-pandêmico moderno), o montante global de armazenamento e tráfego hospedado na plataforma Box avançou exponencialmente.
Esse crescimento da demanda levou a um aumento equivalente das instâncias e servidores em nuvem provisionados. Contudo, adotando a típica mentalidade cautelosa de infraestrutura chamada "*just in case*", provisionar excesso de capacidade prévia antes de faltar recurso para não causar inatividade à plataforma, a Box percebeu que os seus gastos cresceram de maneira desenfreada.
O desafio era encontrar os potenciais ocultos para sanar desperdício com serviços e recursos mantidos ociosos sem comprometer em nada a estabilidade corporativa, o repasse de download e velocidade aos usuários globais.

## Por que usar a Amazon?

Numa plataforma que já era fortemente atrelada à Amazon, a Box apenas percebeu que precisava utilizar melhor não a força bruta da AWS, mas sim as ferramentas inteligentes.
A preferência por escalar as soluções de redução na Amazon ocorreu devido à utilização primária do **AWS Well-Architected Framework**. Os Arquitetos de Soluções Executivos da AWS realizaram painéis conjuntos de acompanhamento e "*deep dive*" nas contas da Box com foco na otimização da cadeia de FinOps (Finanças na Nuvem). A AWS oferecia também várias classes escalares de armazenamento (que permitiam reduzir consideravelmente os custos fixos sem esforço de engenharia contínuo) e mapeamento profundo do tráfego.

## Benefícios

Com as melhorias baseadas no AWS Well-Architected Framework, a Box alcançou:

- **Economia total de mais de US$ 2,23 milhões por ano**.
- **US$ 1,1 milhão economizados** com roteamento inteligente de tráfego, o que também aumentou a velocidade de download.
- **US$ 438 mil poupados** ao evitar tráfego desnecessário entre diferentes Zonas de Disponibilidade (AZs).
- **US$ 500 mil reduzidos** com a limpeza automática de discos (EBS) e backups (snapshots) sem uso.
- **US$ 192 mil economizados** ao filtrar apenas eventos essenciais no monitoramento do AWS CloudTrail.

## Arquitetura

As mudanças focaram em três áreas principais:

- **Amazon S3 e Glacier**: Uso de regras automáticas para mover arquivos pouco acessados para camadas de armazenamento mais baratas.
- **Amazon EBS**: Exclusão automática de volumes de disco que não estavam conectados a nenhum serviço.
- **Roteamento de Rede**: Otimização do tráfego interno para reduzir custos de transferência e melhorar a latência.
- **AWS CloudTrail**: Configuração de filtros para registrar apenas eventos críticos de auditoria e conformidade.
