# Questão 02 - Calculadora de preços

Acesse a Calculadora de Preços da AWS (https://calculator.aws/).  
Crie um arquivo texto com as seguintes informações e estimativas.  
Laboratório didático de uma universidade:  
Quantas máquinas existem?  
Qual a capacidade das máquinas?  
Considere um laboratório didático ideal para uma disciplina de Computação Gráfica. Considere recursos das máquinas, espaço em disco, sistemas operacionais, quantidade de alunos, etc.  
Crie uma estimativa para uma máquina. Salve e disponibilize o link.  
Crie uma estimativa para um laboratório. Salve e disponibilize o link.  
Quantos laboratórios existem no bloco onde você tem aula?  
Crie uma estimativa para todos os laboratórios do bloco, salve e disponibilize o link.  
Refaça toda a prática (as três estimativas anteriores) agora utilizando a Calculadora de Preços do Google (https://cloud.google.com/products/calculator). Salve e disponibilize os links. Informe todos os valores de cada estimativa no texto, para fim de comparação.  
Faça uma breve descrição comparando as estimativas entre os dois provedores. Informe todos os valores de cada estimativa no texto, para fim de comparação.  

**Configurações desejadas:**   
1 Máquina:
- 4 GB de RAM DDR4
- Intel Core I7-2600 x 8
- 512 GB de HD

1 Laboratório: 24 máquinas  
1 Bloco: 3 laboratórios  

---

## Estimativa AWS — Laboratório de Computação Gráfica

### Configuração da Estimativa (1 Máquina)

| Campo | Valor |
|---|---|
| **Provedor** | Amazon Web Services (AWS) |
| **Região** | Leste dos EUA — Norte da Virgínia |
| **Serviço** | Amazon EC2 |
| **Carga de trabalho** | Uso constante |

---

### Especificações da Instância

| Campo | Valor |
|---|---|
| **Nome da instância** | g4dn.xlarge |
| **Família** | g4dn |
| **Categoria** | GPU Instance |
| **vCPUs** | 4 |
| **Memória RAM** | 16 GiB |
| **Armazenamento local** | 125 GB NVMe SSD |
| **Desempenho de rede** | Até 25 Gigabit |
| **Geração atual** | Sim |

---

### Custos por Número de Instâncias (On-Demand, uso constante)

| Instâncias | Custo/mês | Custo/ano |
|---|---|---|
| **1** (1 máquina) | $ 278,13 | $ 3.337,56 |
| **24** (1 laboratório) | $ 6.675,12 | $ 80.101,44 |
| **72** (3 laboratórios) | $ 20.025,36 | $ 240.304,32 |
  
**link para as estimativas:**  
[estimativa computador](./estimativas/Estimativa%20AWS%20-%20computador.pdf)  
[estimativa laboratório](./estimativas/Estimativa%20AWS%20-%20laborat%C3%B3rio.pdf)  
[estimativa bloco](./estimativas/Estimativa%20AWS%20-%20bloco.pdf)

---

### Relatório

**Relatório de Estimativa — AWS EC2**  
A quantidade de instâncias escolhidas foram 1 computador, 24 máquinas por laboratório e 72 máquinas por bloco (*pois no bloco 1 só temos 3 laboratórios  usados para aula, e não me recordo se temos com mais de 3 laboratórios*).

A estimativa foi realizada utilizando o serviço **Amazon EC2 (Elastic Compute Cloud)** da AWS, que permite provisionar servidores virtuais na nuvem com configurações flexíveis de hardware. O EC2 é o serviço de computação mais tradicional da AWS e o mais adequado para simular máquinas de laboratório, pois oferece controle direto sobre CPU, memória, armazenamento e sistema operacional.

A região escolhida foi **Leste dos Estados Unidos — Norte da Virgínia (us-east-1)**. Embora a AWS disponha de uma região em São Paulo (sa-east-1), que reduziria a latência para usuários brasileiros, a região da Virgínia apresenta custo significativamente menor para a mesma instância. Para fins acadêmicos e didáticos, onde o objetivo é a estimativa de custos e não a implantação real de um sistema em produção, essa escolha representa um bom custo-benefício.

A instância selecionada foi a **g4dn.xlarge**, pertencente à família g4dn, categorizada como GPU Instance. Essa escolha se justifica pela natureza da disciplina de Computação Gráfica, que exige poder de processamento gráfico para renderização, modelagem 3D e simulações visuais. A instância conta com 4 vCPUs, 16 GiB de memória RAM, 125 GB de armazenamento local NVMe SSD e desempenho de rede de até 25 Gigabit, além de uma GPU NVIDIA T4 integrada. Trata-se de uma instância de geração atual, o que garante melhor eficiência energética e de desempenho em relação a gerações anteriores.

O modelo de cobrança adotado foi o **On-Demand com uso constante**, ou seja, a máquina permanece ligada durante todos os dias do mês sem interrupções. Esse modelo não exige compromisso de longo prazo e é ideal para fins de estimativa, ainda que na prática um laboratório universitário pudesse se beneficiar do modelo Savings Plans, que oferece desconto de até 56%, reduzindo o custo efetivo de **$ 0,894/hora** para aproximadamente **$ 0,395/hora**.

---

## Estimativa Google Cloud — Dados da Configuração

| Campo | Valor |
|---|---|
| **Provedor** | Google Cloud Platform (GCP) |
| **Serviço** | Compute Engine |
| **Região** | us-east1 — Carolina do Sul |
| **Tipo de máquina** | f1-micro (1 vCPU, 0,9 GiB RAM) |
| **GPU** | NVIDIA T4 — 1 unidade |
| **Disco de inicialização** | 10 GB (Balanced Persistent Disk) |
| **Sistema operacional** | Linux (sem custo adicional) |
| **Modelo de provisionamento** | Regular (On-Demand) |
| **Uso mensal** | 730 horas (uso constante) |

---

### Custos por Número de Instâncias (Google Cloud)

| Instâncias | Custo/mês | Custo/ano |
|---|---|---|
| **1** (1 máquina) | $ 262,75 | $ 3.153,00 |
| **24** (1 laboratório) | $ 6.305,95 | $ 75.671,40 |
| **72** (3 laboratórios) | $ 18.917,86 | $ 226.814,16 |

---

### Tabela Comparativa — AWS vs Google Cloud

| Instâncias | AWS (mês) | GCP (mês) | Diferença |
|---|---|---|---|
| **1 máquina** | $ 278,13 | $ 262,75 | GCP ~5,5% mais barato |
| **1 laboratório (24)** | $ 6.675,12 | $ 6.305,95 | GCP ~5,5% mais barato |
| **3 laboratórios (72)** | $ 20.025,36 | $ 18.917,86 | GCP ~5,5% mais barato |

Links das estimativas:  
[Estimativa Google Cloud - 1 máquina](./estimativas/Estimativa%20Google%20Cloud%20-%20computador.csv)  
[Estimativa Google Cloud - 1 laboratório](./estimativas/Estimativa%20Google%20Cloud%20-%20laboratorio.csv)  
[Estimativa Google Cloud - 1 bloco](./estimativas/Estimativa%20Google%20Cloud%20-%20bloco.csv)

---

### Relatório

As estimativas foram realizadas nas calculadoras oficiais da AWS e do Google Cloud, simulando o provisionamento de instâncias com GPU para um laboratório didático de Computação Gráfica. Em ambos os provedores, foi adotado o modelo de uso constante (730 horas/mês), sistema operacional Linux sem custo de licença, e GPU NVIDIA T4 para suportar as demandas de processamento gráfico da disciplina.

Na AWS, foi utilizada a instância **g4dn.xlarge**, uma máquina pré-configurada com 4 vCPUs, 16 GiB de RAM e 125 GB de armazenamento NVMe SSD, com custo de **$ 278,13 por máquina/mês**. No Google Cloud, a configuração adotada foi a **f1-micro com GPU T4 anexada**, na região us-east1 (Carolina do Sul), com custo de **$ 262,75 por máquina/mês**. Vale destacar que as duas configurações não são estritamente equivalentes — a instância AWS é consideravelmente mais robusta em CPU e memória — o que deve ser levado em conta na interpretação dos valores.

Considerando os três cenários estimados — 1 máquina, 1 laboratório (24 máquinas) e um bloco completo (72 máquinas) — o Google Cloud apresentou custo aproximadamente **5,5% menor** em todos os casos. Para o cenário mais amplo, de 72 instâncias, a diferença mensal ficou em torno de **$ 1.107,50**, o que representa uma economia anual de aproximadamente **$ 13.290,00**. Embora a diferença percentual seja pequena, ela se torna relevante em escala, reforçando a importância de comparar provedores antes de qualquer decisão de infraestrutura em nuvem.
