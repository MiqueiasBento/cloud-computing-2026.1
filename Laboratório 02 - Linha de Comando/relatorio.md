# Relatório do Laboratório 2 - Linha de Comando

## Questão 1
![Instancia Criada](./registros/1-instancia-com-meu-nome-criada.png)
Criação da instância com o nome "miqueias-bento".

![Instancia no CloudShell](./registros/2-cloudshell-da-instancia-iniciado.png)
Acesso ao CloudShell. 

## Questão 2
Para cada comando a seguir, ajuste para a sua máquina virtual (geralmente o id ou nome da máquina virtual) e execute.
Alguns comandos vão resultar num erro propositadamente.
Relate o resultado de cada um. Pode ser textual, pode ser um print de parte da tela.

* `aws ec2 describe-instances`  
![comando 01](./registros/informacoes-vm-comando-01.png)
  Listou todas as instâncias EC2 disponíveis na conta e região configuradas no ambiente da AWS CLI, retornando informações detalhadas sobre cada máquina virtual.

* `aws ec2 describe-instances --instance-ids i-1234567890abcdef0`  
![comando 02](./registros/informacoes-vm-comando-02.png)
  Consultou especificamente uma instância EC2 a partir do seu identificador único (`InstanceId`), retornando apenas os dados relacionados àquela máquina virtual.

* `aws ec2 describe-instances --output yaml --region us-east-1`  
![comando 03](./registros/informacoes-vm-comando-03.png)
  Listou as instâncias EC2 da região `us-east-1`, exibindo os resultados no formato YAML para facilitar a leitura estruturada das informações.

* `aws ec2 describe-instances --filters "Name=instance-type,Values=t2.nano"`  
![comando 04](./registros/informacoes-vm-comando-04.png) 
  Listou apenas as instâncias EC2 que possuíam o tipo `t2.nano`, permitindo identificar máquinas com essa configuração específica.  
  Minha VM não foi listada aqui.

* `aws ec2 describe-instances --filters "Name=instance-type,Values=t3.micro"`  
![comando 05](./registros/informacoes-vm-comando-05.png)
  Listou exclusivamente as instâncias do tipo `t3.micro`, retornando apenas máquinas virtuais compatíveis com esse perfil de hardware.  
  Minha VM foi listada aqui.

* `aws ec2 describe-instances --filters "Name=tag:Name,Values=umNomeQualquerDiferenteDaMinhaMV"`  
![comando 06](./registros/informacoes-vm-comando-06.png)
  Buscou instâncias EC2 com uma tag `Name` diferente do nome da máquina virtual criada, demonstrando o funcionamento de filtros por tags na AWS.  
  Minha VM não foi listada aqui.

* `aws ec2 describe-instances --filters "Name=tag:Name,Values=oNomeDaMinhaVM"`  
![comando 07](./registros/informacoes-vm-comando-07.png)
  Localizou a instância EC2 criada no laboratório por meio da tag `Name`, retornando apenas a máquina virtual correspondente.  
  Minha VM foi listada aqui.

* `aws ec2 describe-instances --filters "Name=tag:Name,Values=oNomeDaMinhaVM" --output yaml`  
![comando 08](./registros/informacoes-vm-comando-08.png)
  Consultou a instância EC2 pelo nome definido na tag `Name`, exibindo os resultados no formato YAML para melhor organização visual das informações retornadas.  
  Minha VM foi listada aqui.

* `aws ec2 describe-instances --query "Reservations[*].Instances[*].{Instance:InstanceId,Subnet:SubnetId}" --output json`  
![comando 09](./registros/informacoes-vm-comando-09.png)
  Extraiu apenas os identificadores das instâncias (`InstanceId`) e das sub-redes (`SubnetId`), utilizando consultas customizadas da AWS CLI e exibindo o resultado em formato JSON.  
  Minha VM foi listada aqui.

* `aws ec2 describe-instances --filters Name=instance-type,Values=t2.micro --query Reservations[*].Instances[*].[InstanceId] --output text`  
![comando 10](./registros/informacoes-vm-comando-10.png)
  Listou somente os identificadores das instâncias do tipo `t2.micro`, apresentando os resultados em formato texto simplificado.  
  Minha VM foi listada aqui.

* `aws ec2 start-instances --instance-ids i-1234567890abcdef0`  
![comando 11](./registros/informacoes-vm-comando-11.png)
  Iniciou uma instância EC2 previamente desligada, alterando seu estado para execução (`running`).

* `aws ec2 stop-instances --instance-ids i-1234567890abcdef0`  
![comando 12](./registros/informacoes-vm-comando-12.png)
  Interrompeu a execução de uma instância EC2 em funcionamento, alterando seu estado para parada (`stopping`).


## Questão 3
Os comandos a seguir criarão buckets no S3.
Dependendo da disponibilidade de nomes de buckets, você criará dois.
Ajuste os comandos conforme o nome e execute.
Alguns comandos vão resultar num erro propositadamente.
Relate o resultado de cada um. Pode ser textual, pode ser um print de parte da tela.

* `aws s3 ls`
    ![comando buckets 01](./registros/buckets-comando-01.png)
  Deveria listar todos os buckets S3 disponíveis na conta AWS configurada no ambiente.
  Não apareceu nenhum bucket, pois ainda não criei nenhum.

* `aws s3 mb s3://bucketA`
    ![comando buckets 02](./registros/buckets-comando-02.png)
  O comando apresentou erro porque os nomes de buckets no Amazon S3 precisam ser únicos globalmente. O nome informado já estava em uso ou já pertencia à conta utilizada.
  Ainda tentei várias vezes, só depois quando pesquisei foi que entendi.

* `aws s3 ls s3://bucketA`
  ![comando buckets 03](./registros/buckets-comando-03.png)
  O comando apresentou erro porque o bucket informado não existia no momento da execução.

* `cat > novo_arquivo.txt`
  ![Criando arquivo](./registros/buckets-comando-04.png)
  Criou um arquivo de texto chamado `novo_arquivo.txt` diretamente pelo terminal, permitindo inserir conteúdo manualmente.

* `aws s3 cp novo_arquivo.txt s3://bucketA`
  ![Criando arquivo](./registros/buckets-comando-05.png)
  O comando apresentou erro porque o bucket informado não existia no momento da execução.

* `aws s3 rb s3://bucketA`
  ![Criando arquivo](./registros/buckets-comando-06.png)
  O comando apresentou erro porque o bucket ainda continha objetos armazenados, e o Amazon S3 exige que o bucket esteja vazio antes de sua remoção.

* `aws s3 cp s3://bucketA/novo_arquivo.txt velho_arquivo.txt`
  ![Criando arquivo](./registros/buckets-comando-07.png)
  O comando apresentou erro porque o objeto informado não foi encontrado no bucket especificado.

* `aws s3 mb s3://bucketB`
  ![Criando arquivo](./registros/buckets-comando-08.png)
  Também apresentou erro, pois o nome do bucket informado já estava em uso ou já pertencia à conta utilizada.

* `aws s3 mv s3://bucketA/novo_arquivo.txt s3://bucketB/outro_novo_arquivo.txt`
  ![Criando arquivo](./registros/buckets-comando-09.png)
  O comando apresentou erro devido à inexistência do bucket informado ou restrições de acesso configuradas na conta AWS.

* `aws s3 rb s3://bucketA`
  ![Criando arquivo](./registros/buckets-comando-10.png)
  O comando apresentou erro porque o bucket informado já havia sido removido anteriormente.

* `aws s3 rb s3://bucketB --force`
  ![Criando arquivo](./registros/buckets-comando-11.png)
  O comando deveria remover automaticamente os objetos existentes no bucket antes de realizar sua exclusão definitiva utilizando a opção --force.
  Mas como o bucket não existia, o comando apresentou erro.
