# Relatório: Laboratório 4 - Como trabalhar com o EBS

Relatório para documentar a execução do laboratório voltado ao Amazon Elastic Block Store (EBS). 
O Lab foi executado desde a criação e anexação de novos volumes de armazenamento a instâncias EC2, passando pela configuração dos sistemas de arquivos a nível de sistema operacional, até as rotinas de backup e restauração de dados por meio de snapshots.

## Relato da Atividade

Algumas dificuldades que eu tive:
- O registro visual do exato momento de anexação do volume inicial à instância não foi capturado em imagem, no entanto, a operação foi realizada integralmente através do console da AWS.
- O acesso ao terminal da instância EC2 foi conduzido por meio do EC2 Instance Connect, recurso que fornece acesso SSH interativo diretamente pelo navegador.
- Houve um obstáculo temporário ao tentar a conexão padronizada, causado por ligeiras discrepâncias no material traduzido. A resolução consistiu na execução da conexão como administrador pela mesma ferramenta (EC2 Instance Connect).
- No Passo 5 do guia, havia a orientação para exclusão de um arquivo. Como tal arquivo não havia sido gerado ou modificado em passos anteriores, essa exclusão pôde ser ignorada sem que houvesse prejuízo para a correta validação e pontuação final do laboratório.

---

## Passos da Execução

![Iniciando instância Lab EC2](./registros-lab-4/1-iniciando-instancia-lab-ec2.png)
Painel do Amazon EC2 demonstrando o estado de inicialização da instância base designada para o laboratório, a qual será alvo das subsequentes configurações de disco.

![Criação de novo volume personalizado](./registros-lab-4/2-criacao-novo-volume-personalizado.png)
Acesso ao menu de Volumes do EBS para a criação de um armazenamento de blocos personalizado, estipulando atributos como o tipo de disco, a capacidade alocada e a zona de disponibilidade (garantindo sua compatibilidade com a instância alvo).

![Confirmação do volume anexado ao EC2](./registros-lab-4/3-confirmacao-colume-anexado-ec2.png)
Comprovação no console de gerenciamento indicando que a rotina de anexação (attach) vinculou de maneira bem-sucedida o volume recém-criado à instância EC2 em execução.

![Conectando à instância do EC2](./registros-lab-4/4-conectando-instancia-do-ec2.png)
Início do procedimento para estabelecimento de conexão SSH com a instância EC2, pré-requisito fundamental para lidar com o volume bruto recém-atrelado.

![Problema na conexão com EC2](./registros-lab-4/5-problema-para-se-conecntar-o-ec2.png)
Sinalização de um erro momentâneo de conectividade, resultante de problemas com chaves SSH ou de rotas, que instigou uma abordagem alternativa documentada no relato.

![Conexão estabelecida com sucesso](./registros-lab-4/6-consegui-fazer-conexao.png)
Acesso definitivo e bem-sucedido ao ambiente de linha de comando Linux, efetuado através do uso do AWS EC2 Instance Connect.

![Criando e configurando o sistema de arquivos](./registros-lab-4/7-criando-e-configurando-sistema-de-arquivos.png)
Uso de comandos administrativos de terminal (`lsblk`, `mkfs`, `mount`) para reconhecer o novo disco em bloco, formatá-lo com o respectivo sistema de arquivos e montá-lo na hierarquia de diretórios da máquina.

![Criando snapshot do volume](./registros-lab-4/8-criando-snapshot-no-volume.png)
Acompanhamento através do console da AWS da inicialização da criação de um Snapshot sobre o volume, gerando uma imagem de backup pontual contendo os dados presentes no momento.

![Deletando arquivo para teste do snapshot](./registros-lab-4/9-deletando-arquivo-snapshot.png)
Demonstração efetuada no terminal executando comandos operacionais (como tentar remover arquivos do volume) para criar um cenário de perda de dados e comprovar a necessidade de um sistema de recuperação.

![Volume criado a partir do snapshot](./registros-lab-4/10-volume-criado-com-snapshot.png)
Etapa de criação de um novo e independente volume EBS cuja referência original de dados apontou para o Snapshot recém-registrado, constituindo a via de restauração efetiva.

![Montagem da restauração dos volumes](./registros-lab-4/11-montagem-da-restauracao-de-volumes.png)
Validação final do processo confirmando que o sistema operacional, ao montar o volume restaurado na máquina virtual, recupera totalmente a estrutura e a integridade de dados contidas no backup original.

![Resultado final](./registros-lab-4/pontuacao-final.png)
Pontuação final obtida no laboratório.