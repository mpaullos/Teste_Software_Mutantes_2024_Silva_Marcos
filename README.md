# Teste de Software - Mutantes

## Tutorial

Link para o meu repositório: [https://github.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos](https://github.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos)

Repositório base: [https://github.com/JoshData/python-email-validator](https://github.com/JoshData/python-email-validator)

**email-validator:** Validate Email Addresses  
Uma robusta biblioteca de validação de sintaxe de e-mail e de entrega para Python.

### 1º Passo 

É necessário fazer o download do repositório ou o clone do mesmo para sua máquina.

```bash
git clone https://github.com/JoshData/python-email-validator.git
```

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/1.png" alt="Imagem mostrando o comando git clone" />

Em seguida, após a extração ou o clone do repositório, você deve seguir os passos de execução no arquivo `README.md` do repositório `python-email-validator`.

### 2º Passo 

Com a IDE de sua escolha, abra o folder do `python-email-validator`.

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/2.png" alt="Imagem mostrando a IDE com o folder aberto" />

Feito isso, crie um ambiente virtual para instalar as bibliotecas de dependências. O comando para criar esse ambiente é:

```bash
python3 -m venv /home/marcospaulo/Downloads/python-email-validator-main/venv
```

**OBS:** O caminho (`path`) deve ser o local onde foi feito o download ou o clone do repositório.

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/3.png" alt="Imagem mostrando o terminal com o comando para criar o ambiente virtual" />

Certifique-se de que está aparecendo `(venv)` no terminal.

### 3º Passo

É necessário instalar as dependências listadas no arquivo `test_requirements.txt`. Além disso, você deve instalar o `mutmut`, pois ele não está incluído nos requisitos do repositório. Use os seguintes comandos:

```bash
pip3 install -r test_requirements.txt
pip3 install mutmut
pip install email-validator
```

### 4º Passo

Com as dependências instaladas, é hora de realizar os testes!

Execute os seguintes comandos:

```bash
pytest -vv tests/test_deliverability.py
```

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/4.png" alt="Imagem mostrando o terminal executando o pytest" />

```bash
pytest -vv tests/test_deliverability.py --cov=tests
```

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/5.png" alt="Imagem mostrando o terminal executando o pytest com cobertura" />

```bash
pytest -vv tests/test_deliverability.py --cov=tests --cov-branch --cov-report html
```

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/6.png" alt="Imagem mostrando o terminal executando o pytest com cobertura detalhada" />

Dentro do arquivo `index.html`, você encontrará informações detalhadas sobre os testes.

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/7.png" alt="Imagem mostrando o relatório de cobertura no HTML" />
<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/8.png" alt="Outra imagem do relatório de cobertura no HTML" />

### 5º Passo

Agora, utilize a biblioteca `mutmut`. O teste escolhido possui uma cobertura de 100%. Vamos verificar se essa cobertura se mantém com o `mutmut`.

Execute o seguinte comando:

```bash
mutmut run --paths-to-mutate=/home/marcospaulo/Downloads/python-email-validator-main/tests/test_deliverability.py
```

Após a execução do teste, aguarde o procedimento ser finalizado.

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/9.png" alt="Imagem mostrando o resultado dos testes após o mutmut" />

O arquivo `test_deliverability.py` matou 57 mutantes, teve 1 execução suspeita, e 5 mutantes permaneceram vivos.

Para verificar os resultados, use:

```bash
mutmut results
```

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/10.png" alt="Imagem mostrando o resultado dos mutantes" />

Para exibir detalhes de um mutante específico:

```bash
mutmut show 45
```

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/11.png" alt="Imagem mostrando os detalhes de um mutante específico" />

Para gerar um relatório HTML:

```bash
mutmut html
```

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/12.png" alt="Imagem mostrando o relatório HTML gerado pelo mutmut" />

### 6º Passo

Após abrir o HTML, adicione as sugestões do `mutmut` ou crie novos testes.

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/13.png" alt="Imagem mostrando a correção de um mutante no código" />

Na imagem, é possível perceber que um mutante foi corrigido, restando agora apenas 4.

**Código antigo:**

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/14.png" alt="Imagem mostrando o código antigo" />

**Melhoria:**

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/15.png" alt="Imagem mostrando a melhoria no código" />

**Resultado Final:**

<img src="https://raw.githubusercontent.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/main/artefatos/images/16.png" alt="Imagem mostrando o resultado final após as correções" />

[Artefatos gerados no testes](https://github.com/mpaullos/Teste_Software_Mutantes_2024_Silva_Marcos/tree/main/artefatos)
