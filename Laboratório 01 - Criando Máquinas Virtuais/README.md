# Laboratório 1 - Criando Máquinas Virtuais

Crie um documento para relatar toda a prática ([acesso](./relatario.md)).  
Nele você vai incluir para as questões a seguir comprovações com prints das telas e respostas das questões.  

## Questão 1

- Inicie o ambiente prático do Sandbox.
- Uma vez pronto, acesse "Details", depois em "Show" e faça download da chave SSH (mantenha em segurança) em "Download PEM". Você vai utilizar esta chave localmente mais adiante.
- **Faça um print da tela "Credentials"** e explique o que é e para que serve uma chave PEM.
- OBS: Nunca exponha suas credenciais de acesso!!!

## Questão 2

- Acesse o **EC2**.
- Vá até "Instâncias" e clique em "Executar Instâncias".
- Você vai criar duas instâncias Linux com as seguintes características:
  - Nomes - MinhaMaquinaVirtual1 e MinhaMaquinaVirtual2
  - Imagem - Escolha a imagem de aplicação e sistema operacional Amazon Linux
  - Par de chaves - selecione vockey

- **Inclua um print da tela da lista de instâncias**.
- Identifique os seguintes campos para cada instância e copie as informações:
  - Endereço IPv4 público
  - DNS pública
  - Tipo de instância
  - Tamanho, tipo e IOPS do armazenamento
  - Grupos de segurança e regras de entrada

## Questão 3

- Selecione "MinhaMaquinaVirtual1", clique em "Conectar" e acesse a aba "Conexão de instância do **EC2**".
- Identifique o nome do usuário padrão.
- **Inclua um print da tela**.
- Clique em "Conectar".
- **Faça um print da tela do terminal que apareceu**.

- Selecione "MinhaMaquinaVirtual2", clique em "Conectar" e acesse a aba "Cliente SSH".
- Identifique o comando para conexão SSH.
- **Inclua um print da tela**.
- Na tela do terminal da "MinhaMaquinaVirtual1" cole o comando SSH e explique o que ocorreu.
- **Faça um print da tela do terminal com o que aconteceu**.

- Acesse o terminal da máquina física que você está fazendo o laboratório - Windows ou Linux.
- No local onde você estiver acessando, utilize o comando SSH para acesso a "MinhaMaquinaVirtual2". Se o nome da chave não for o mesmo nome da chave que você fez download, atualize o comando.
- **Faça um print da tela do terminal de que aconteceu**.

## Questão 4

- A partir da "MinhaMaquinaVirtual2" digite o comando ping para a o ip da "MinhaMaquinaVirtual1".
- **Faça um print da tela do terminal de que aconteceu**.
- Relate o que ocorreu e explique o motivo e a solução.
- Acesse o grupo de segurança da "MinhaMaquinaVirtual1" e acesse "Editar regras de entrada".
- Qual a relação dessa tela com o ocorrido após o comando ping?
- Clique em "Adicionar regra", selecione "ICMP personalizado - IPv4" e no "Bloco CIDR" selecione "0.0.0.0/0". Clique em "Salvar regras".
- **Tire um print da tela com a nova regra**.
- Refaça o comando do ping e relate o resultado.
- **Faça um print da tela do terminal de que aconteceu**.

## Questão 5

- Vá até "Instâncias" e clique em "Executar Instâncias".
- Você vai criar uma instância Windows com as seguintes características:
  - Nome - MeuWindows
  - Imagem - Escolha a imagem de aplicação e sistema operacional Windows
  - Par de chaves - selecione vockey

- Selecione "MeuWindows", clique em "Ações", "Segurança" e "Obter senha do windows".
- Carregue a chave PEM que você fez download nessa tela.
- Clique em "Desincriptografar senha" e **salve o nome de usuário e a senha**.
- **Tire um print da tela**.

- Na tela das instâncias, selecione "MeuWindows", clique em "Conectar", aba "Cliente RDP".
- Explique o que é um cliente RDP.
- Clique em "Fazer download de arquivo de área de trabalho remota".
- Execute o arquivo.
- Faça o login com o usuário e senha obtidos.
- **Tire um print da tela de "MeuWindows"**
