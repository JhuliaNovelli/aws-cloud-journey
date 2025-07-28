# Arquivo .pem na maquina Linux - usando o WSL

### Após o download 

1. Criei uma pasta segura para armazenar a chave

            No terminal do WSL, criei a pasta .ssh dentro do meu diretório home, que é o local padrão para armazenar chaves SSH:


`mkdir -p ~/.ssh`

2. Copiei o arquivo .pem para o WSL

    O arquivo .pem foi baixado na pasta de Downloads do Windows. Então, acessei esse diretório a partir do WSL e copiei o arquivo para dentro da pasta .ssh:


`cd /mnt/c/Users/meu-usuario/Downloads`
`cp minha-chave.pem ~/.ssh/`

    Obs: Substituí meu-usuario pelo meu nome de usuário do Windows, e minha-chave.pem pelo nome do meu arquivo de chave.

3. Apliquei as permissões corretas na chave

    Para garantir que o SSH funcione corretamente, dei permissão segura ao arquivo .pem. Isso evita que outras pessoas tenham acesso de leitura a ele:
`cd ~/.ssh`
`chmod 400 minha-chave.pem`

4. Conectei à minha instância EC2

Com tudo pronto, usei o comando SSH fornecido pela AWS para acessar minha instância EC2. 

### Configuração do WSL no Windows

[Passo a Passo para configuração do WSL](https://github.com/JhuliaNovelli/linux-fundamentals/blob/main/config-wsl.md)
