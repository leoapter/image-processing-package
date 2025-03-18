# Tutorial Empacotamento

# Modularização
## Módulo
Objeto que serve como unidade organizacional do código que é carregado pelo comando `import`.
## Vantagens da modularização:
- Legibilidade
- Manutenção
- Reaproveitamento de código

# Pacote em Python
## Pacote
Coleção de módulos com hierarquia.

## Vantagens de criar um pacote:
- Facilidade de compartilhamento
- Facilidade de instalação

## Conceitos:
- **PyPI**: Repositório público oficial de pacotes em Python.
- **Wheel e Sdist**: Dois tipos de distribuições.
- **Setuptools**: Pacote usado em `setup.py` para gerar as distribuições.
- **Twine**: Pacote usado para subir as distribuições no repositório PyPI.

# Criando o projeto e gerando as distribuições
Descomplicando a criação de pacotes em Python.

## Arquivo `README.md`
Usado para informações gerais e instruções específicas 

## Arquivo `requirements.txt`
Usado para especificar as dependências que devem ser instaladas com o pacote. Opcionalmente, podem ser especificadas as versões.

## Arquivo `setup.py`
Usado para especificar como o pacote deve ser construído.
[Documentação](https://setuptools.readthedocs.io/en/latest/setuptools.html)

# Distribuição do Pacote
Para subir o pacote, é necessário criar uma distribuição binária(wheel) ou uma distribuição de código fonte(sdist) source distribution).
As versões mais recentes do `pip` instalam primeiramente a versão binária e usam a distribuição de código fonte apenas se necessário.
De qualquer forma, iremos criar ambas as distribuições.

## Passos para distribuição do pacote  
1. Acessar a raiz do projeto
2. Aplicar os comandos de instalação
3. Aplicar os comandos de distribuição
   
## Comandos de instalação
```bash
python -m pip install --upgrade pip
pip install twine
pip install setuptools
```

## Comandos de distribuições
```bash
python setup.py sdist bdist_wheel
```

# Publicação do Pacote
Após concluída a distribuição utilizando os comandos de instalação e distribuição, é necessária subir e publicar o pacote no repositório do Pypi.
É uma boa prática antes de subir diretamente ao Pypim testar no Test Pypi. Uma vez concluido que está tudo ok, subir e publicar no Pypi.

## Passos para subir o pacote  
1. Criar conta no Test PyPi
2. Publicar no Test PyPi
3. Instalar o pacote usando Test PyPi
4. Testar pacote
5. Criar conta no PyPi
6. Publicar no PyPi
7. Instalar o pacote usando PyPi

# Criando contas no PyPi
- [Criar conta no Test PyPI](https://test.pypi.org/account/register/)
- [Criar conta no PyPI](https://pypi.org/account/register/)
O site vai solicitar nome, e-mail, nome_usuário, senha.
É recomendado utilizar o mesmo e-mail e nome_usuário do GitHub.
Após o cadastro será solicitado confirmar o seu-email

## Comando para publicar no Test PyPi
```bash
python -m twine upload --repository-url https://test.pypi.org/legacy/ dist/*
```
O site vai solicitar o seu ususário e senha.
Após publicar, será enviado o link para verificar se tudo esta ok no site (test.pypi.org/project/nome_do_pacote).
Estando tudo ok, instale o pacote do Teste Pypi no seu repositório para fins de teste

# Comando para instalar o pacote do teste PyPi no seu repositório local
```bash
python -m pip install package_name
```
Estando tudo ok, publique no Pypi

## Comando para publicar no PyPi
```bash
python -m twine upload --repository-url https://upload.pypi.org/legacy/ dist/*
```

Finalmente instale o pacote do Pypi no seu repositório para fins de teste
# Comando para instalar o pacote do PyPi no seu repositório local
```bash
python -m pip install package_name
```
