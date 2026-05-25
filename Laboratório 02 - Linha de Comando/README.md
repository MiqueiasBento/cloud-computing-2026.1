# Laboratório 2 - Linha de Comando
Crie um documento para relatar toda a prática.

Nele você vai incluir para as questões a seguir comprovações com prints das telas e respostas das questões.

## Questão 1
Crie uma máquina virtual de nome igual ao seu nome.  
Obtenha as informações do ip público ou DNS público.  
Infos:
- ID: i-00cab09033b7fde26
- Nome: miqueias-bento
- IP Público: 100.53.68.143
- IP Privado: 172.31.15.113

Obtenha a informação do ID da instância.  
No topo da página, acesse o "CloudShell". Basta clicar no ícone do ">_".  
No terminal que aparecer, clique no topo à direita a opção "Abrir na nova guia do navegador".  
Tire um print da tela na nova aba.

## Questão 2
Para cada comando a seguir, ajuste para a sua máquina virtual (geralmente o id ou nome da máquina virtual) e execute.
Alguns comandos vão resultar num erro propositadamente.
Relate o resultado de cada um. Pode ser textual, pode ser um print de parte da tela.

- `aws ec2 describe-instances`
- `aws ec2 describe-instances --instance-ids i-1234567890abcdef0`
- `aws ec2 describe-instances --output yaml --region us-east-1`
- `aws ec2 describe-instances --filters "Name=instance-type,Values=t2.nano"`
- `aws ec2 describe-instances --filters "Name=instance-type,Values=t3.micro"`
- `aws ec2 describe-instances --filters "Name=tag:Name,Values=umNomeQualquerDiferenteDaMinhaMV"`
- `aws ec2 describe-instances --filters "Name=tag:Name,Values=oNomeDaMinhaVM"`
- `aws ec2 describe-instances --filters "Name=tag:Name,Values=oNomeDaMinhaVM" --output yaml`
- `aws ec2 describe-instances --query "Reservations[*].Instances[*].{Instance:InstanceId,Subnet:SubnetId}" --output json`
- `aws ec2 describe-instances --filters Name=instance-type,Values=t2.micro --query Reservations[*].Instances[*].[InstanceId] --output text`
- `aws ec2 start-instances --instance-ids i-1234567890abcdef0`
- `aws ec2 stop-instances --instance-ids i-1234567890abcdef0`

## Questão 3
Os comandos a seguir criarão buckets no S3.
Dependendo da disponibilidade de nomes de buckets, você criará dois.
Ajuste os comandos conforme o nome e execute.
Alguns comandos vão resultar num erro propositadamente.
Relate o resultado de cada um. Pode ser textual, pode ser um print de parte da tela.

- `aws s3 ls`
- `aws s3 mb s3://bucketA`
- `aws s3 ls s3://bucketA`
- `cat > novo_arquivo.txt`
- `aws s3 cp novo_arquivo.txt s3://bucketA`
- `aws s3 rb s3://bucketA`
- `aws s3 cp s3://bucketA/novo_arquivo.txt velho_arquivo.txt`
- `aws s3 mb s3://bucketB`
- `aws s3 mv s3://bucketA/novo_arquivo.txt s3://bucketB/outro_novo_arquivo.txt`
- `aws s3 rb s3://bucketA`
- `aws s3 rb s3://bucketB --force`