# Criando uma Instância EC2 na AWS (Passo a Passo)

Hoje eu aprendi como criar uma instância EC2 na AWS usando o Free Tier, ideal para fins de estudo. Abaixo descrevo todo o processo que segui:

## Acesso ao EC2

    Primeiramente, acessei minha conta na AWS e procurei pelo serviço EC2 no console.

    Iniciando a Criação da Instância

    Dentro do painel do EC2, cliquei na opção *“Executar uma instância”*.

## Configuração da Instância

    Na tela de configuração, preenchi os seguintes campos:

    Nome da instância: Escrevi EC2 - First para facilitar a identificação.

    Imagem da instância (AMI): Escolhi o Amazon Linux, pois está incluído no Free Tier e é recomendado para testes.

    Tipo de instância: Selecionei o tipo t2.micro, também incluído no Free Tier.

    Par de chaves (Key Pair):

    Criei um novo par de chaves com um nome fácil de lembrar.

    Escolhi o formato .pem, pois estou usando Linux e preciso do arquivo para me conectar via SSH.

    Salvei o arquivo .pem na minha máquina, pois ele será necessário para a conexão.

### Configuração do .pem WSL

[Passo a Passo para configuração do .pem no linux WSL](https://github.com/JhuliaNovelli/aws-cloud-journey/blob/main/Amazon%20EC2/arquivo(.pem).md)

### Configuração do WSL no Windows

[Passo a Passo para configuração do WSL]()


## Configuração de Rede

    Marquei a opção para permitir tráfego SSH de qualquer lugar (0.0.0.0/0), já que o uso é apenas para estudo.

## Armazenamento

    Mantive o valor padrão de 8 GB, o suficiente para os testes iniciais.

### Revisão e Execução

    Revisei todas as configurações no painel lateral da AWS e cliquei em Executar instância.

## Conectando à Instância

    Com a instância já em execução, fui até a aba Instâncias no painel do EC2.

    Cliquei sobre o ID da instância criada.

    Na nova tela, selecionei a opção *“Conectar”*.

    Escolhi a opção Cliente SSH e copiei o comando fornecido pela AWS. Ele veio mais ou menos assim:

`ssh -i "ec2-key.pem" ec2-user@ec2-XX-XXX-XXX-XXX.us-east-2.compute.amazonaws.com`

## Acessando via Terminal

    Abri o terminal no meu computador e naveguei até a pasta onde salvei o arquivo .pem.

    Colei o comando SSH que copiei da AWS.

    Quando apareceu a mensagem:

`Are you sure you want to continue connecting (yes/no/[fingerprint])?`
    Digitei yes.

Pronto! Consegui acessar minha instância EC2 e estou agora conectada a uma máquina virtual na nuvem, criada do zero por mim!