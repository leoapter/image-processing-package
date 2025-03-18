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
1. Criar conta no Test PyPI
2. Publicar no Test PyPI
3. Instalar o pacote usando Test PyPI
4. Testar pacote
5. Criar conta no PyPI
6. Publicar no PyPI
7. Instalar o pacote usando PyPI

## Comando para publicar no Test PyPI
```bash
python -m twine upload --repository-url https://test.pypi.org/legacy/ dist/*
```

# Criando contas no PyPI
- [Criar conta no Test PyPI](https://test.pypi.org/account/register/)
- [Criar conta no PyPI](https://pypi.org/account/register/)

## Comando para instalar o pacote do PyPI
```bash
python -m pip install package_name
```
