# Questão 03
Como arquiteto de nuvem, você precisa fazer uma estimativa para uma empresa que deseja começar a migração para a nuvem. Atualmente, no datacenter on premises, eles possuem um conjunto de máquinas que totalizam 64 cores e 128 GB de RAM, executando um sistema Linux sem custo de licença, cada uma com disco de 256GB para suportar a instalação do sistema operacional com todas as dependências. Segundo o projetista da aplicação, qualquer quantidade de máquinas virtuais será suficiente, desde que no total somem a mesma ou maior quantidade de cores e memória RAM, mas o mesmo disco de 256 GB por instância. O gerente financeiro afirma que não vê problema em fazer pagamentos adiantados, desde que o custo mensal seria reduzido. Já o gerente de relacionamentos exige que a aplicação seja hospedada no Brasil, pois é uma exigência de alguns clientes.

Além dos servidores de aplicação, os desenvolvedores precisam de um banco de dados Oracle para uma base da dados de 512 GB, porém ainda não possuem a licença. A carga não é tão grande, portanto uma instância de 2 cores e no mínimo 4GB é suficiente, mas eles não desejam se responsabilizar pela configuração do sistema operacional da instância, e nem dos detalhes de configuração e atualizações de segurança do servidor de banco de dados.

Seu papel nesta atividade é fazer uma estimativa para o cenário acima usando a Calculadora de preços da AWS. Você deve pesquisar na documentação da AWS quais os serviços de criação de máquinas virtuais e de fornecimento de bancos de dados Oracle gerenciados e informar os requisitos do cenário. Qualquer campo da estimativa que não mencionado na descrição deve ser configurado para uma opção que reduza o custo mensal da estimativa.

Para compartilhar sua resposta, gere o link da estimativa. Inclua o link da estimativa no arquivo a ser enviado e explique o processo que suportou sua decisão (mínimo 10 linhas).

---

## Configurações da Estimativa — AWS

### Amazon EC2 (Servidores de Aplicação)

| Campo | Valor |
|---|---|
| **Região** | América do Sul — São Paulo |
| **Instância** | c6g.16xlarge |
| **Número de instâncias** | 1 |
| **Sistema operacional** | Linux |
| **Locação** | Instâncias compartilhadas |
| **Carga de trabalho** | Uso constante |
| **Estratégia de preço** | Compute Savings Plans — 3 anos, sem pagamento adiantado |
| **Monitoramento** | Desabilitado |
| **Transferência de dados** | Não selecionada (0 TB) |

---

### Amazon RDS Custom for Oracle (Banco de Dados)

| Campo | Valor |
|---|---|
| **Região** | América do Sul — São Paulo |
| **Serviço** | Amazon RDS Custom for Oracle |
| **Tipo de instância** | db.m5.large (2 vCPUs, 8 GiB RAM) |
| **Número de instâncias** | 1 |
| **Edição Oracle** | Enterprise |
| **Armazenamento** | 512 GB SSD gp2 |
| **Opção de implantação** | Multi-AZ |
| **Modelo de preço** | On-Demand |
| **Utilização** | 100% (uso constante) |

---

### Custos Totais da Estimativa

| Serviço | Custo mensal | Custo anual (12 meses) |
|---|---|---|
| **Amazon EC2** | $ 1.323,56 | $ 15.882,76 |
| **Amazon RDS Custom for Oracle** | $ 628,16 | $ 7.537,97 |
| **Total geral** | **$ 1.951,72** | **$ 23.420,64** |

> Custo inicial: $ 0,00 — nenhum pagamento adiantado foi aplicado.

**Link para as estimativas:**
[estimativas de migração.csv](./estimativas/Estimativa%20de%20migração%20AWS%20-%20EC2%20e%20RDS.csv)

---

## Relatório Final — Decisões e Justificativas

Para os servidores de aplicação, foi utilizado o serviço **Amazon EC2** com uma instância do tipo **c6g.16xlarge**, pertencente à família c6g — baseada em processadores ARM Graviton2 da AWS. Essa família oferece excelente desempenho para cargas Linux com custo inferior às famílias baseadas em x86, o que se alinha ao objetivo de reduzir o custo mensal. A instância conta com 64 vCPUs e 128 GiB de RAM, atendendo exatamente os requisitos mínimos informados pelo projetista sem necessidade de múltiplas instâncias. O sistema operacional escolhido foi Linux, sem custo de licença. A região configurada foi **sa-east-1 (São Paulo)**, atendendo à exigência do gerente de relacionamentos quanto à hospedagem no Brasil.

A estratégia de preço adotada para o EC2 foi o **Compute Savings Plans com compromisso de 3 anos sem pagamento adiantado**, que oferece desconto significativo frente ao modelo On-Demand. Embora o gerente financeiro tenha declarado aceitar pagamentos adiantados, a opção "No Upfront" também reduz o custo mensal sem exigir desembolso inicial, o que representa uma decisão financeiramente conservadora e igualmente válida.

Para o banco de dados, foi utilizado o **Amazon RDS Custom for Oracle**, serviço gerenciado da AWS que abstrai do cliente a responsabilidade pela configuração do sistema operacional, aplicação de patches e atualizações de segurança — atendendo diretamente à exigência dos desenvolvedores. A instância **db.m5.large** foi mantida por atender o mínimo de 2 vCPUs e superar o requisito de 4 GiB de RAM com 8 GiB disponíveis. O armazenamento foi configurado em 512 GB com SSD gp2, conforme especificado. A edição Oracle Enterprise foi selecionada, com licença já inclusa no modelo RDS Custom. A implantação foi configurada como **Multi-AZ**, o que garante alta disponibilidade com réplica automática em uma segunda zona — uma boa prática para ambientes de produção, ainda que eleve o custo em relação à implantação em zona única.

> Vale destacar que busquei ajuda do Claude para entender sobre os tipos de instância e suas configurações, e foi ele quem deu a dica de quais utilizar, porém ainda fiz o ajuste para ficar condizente com o enunciado da questão.
