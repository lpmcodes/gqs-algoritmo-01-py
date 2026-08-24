# Análise [gqs-algoritmo-01-py] — Palíndromos

## Nível 1: Entendendo o funcionamento

### Objetivo do código

O programa tem como objetivo verificar se uma palavra ou frase é um **palíndromo**, ou seja, se ela continua igual quando lida de trás para frente.

Antes de realizar a comparação, o código faz alguns ajustes no texto. Caracteres que não são relevantes para a análise, como espaços e pontuações, são removidos, e todas as letras são convertidas para minúsculas. Depois disso, o texto é invertido e comparado com sua versão original já tratada.

Se os dois resultados forem iguais, o retorno será `True`. Caso sejam diferentes, o resultado será `False`.

### Como executar

1. Escolha ou altere as frases utilizadas nas variáveis `texto1` e `texto2`.
2. Acesse o site [Online Python](https://www.online-python.com/?utm_source=chatgpt.com).
3. Copie o conteúdo presente no arquivo `DesafioLogica.py`.
4. Cole o código no editor onde está o arquivo `main.py`, substituindo o conteúdo existente.
5. Clique no botão **RUN** para executar o programa.

### Exemplo de saída

Considerando as seguintes variáveis:

```python
texto1 = "A sacada da casa de cadasa"

texto2 = "Socorram-me, subi no ônibus em Marrocos"
```

O programa apresentará o seguinte resultado:

```text
Teste 1: False
Teste 2: True
```

Isso acontece porque a primeira frase não possui a mesma sequência de caracteres quando invertida, enquanto a segunda continua igual mesmo após a leitura no sentido contrário.

---

## Nível 2: Engenharia Reversa e Análise do Comportamento

### Funcionamento do código principal

O programa utiliza uma estrutura que verifica se o arquivo atual está sendo executado diretamente como arquivo principal. Quando essa condição é verdadeira, toda a rotina definida no programa é iniciada.

### Análise da função

```python
def analisar(entrada):
```

Essa função recebe um valor chamado `entrada`, que corresponde ao texto que será analisado pelo programa.

```python
if entrada is None:
```

Essa condição verifica se foi enviada alguma informação para a função. Caso a entrada seja inexistente, o programa encerra a análise e retorna:

```python
return False
```

Em seguida, ocorre o tratamento da string:

```python
limpa = re.sub(r'[^a-zA-Z0-9]', '', entrada).lower()
```

Nessa etapa, o programa remove os caracteres que não correspondem a letras ou números e converte todas as letras para minúsculas. Dessa forma, diferenças entre letras maiúsculas e minúsculas não interferem no resultado da comparação.

Depois, a string tratada é invertida:

```python
invertida = limpa[::-1]
```

O uso de `[::-1]` permite criar uma nova versão da string com todos os caracteres na ordem contrária.

Por último, o programa compara os dois valores:

```python
return limpa == invertida
```

Se a versão original tratada for exatamente igual à versão invertida, a função retorna `True`. Caso contrário, retorna `False`.

---

## Análise dos testes

No primeiro exemplo:

```text
A sacada da casa de cadasa
```

Após o tratamento do texto, os espaços e caracteres desnecessários são removidos, resultando em uma sequência que não permanece igual quando invertida. Por esse motivo, o resultado apresentado é:

```text
False
```

Já no segundo exemplo:

```text
Socorram-me, subi no ônibus em Marrocos
```

Após a remoção dos espaços, pontuações e diferenças entre maiúsculas e minúsculas, a sequência resultante permanece igual quando lida de trás para frente.

Portanto, o programa retorna:

```text
True
```

---

## Sobre o autor

Este projeto foi desenvolvido a partir de um fork do repositório original do Prof. Daniel Paiva:

[Repositório gqs-algoritmo-01-py](https://github.com/danhpaiva/gqs-algoritmo-01-py?utm_source=chatgpt.com)

A documentação e análise deste projeto foram realizadas por:

**Nome:** Lucas Paiva Magalhães
**RA:** 4251925101
**GitHub:** https://github.com/lpmcodes
**LinkedIn:** https://www.linkedin.com/in/lucaspaiva3/
**E-mail:** lucas.paivamagalhaes@gmail.com