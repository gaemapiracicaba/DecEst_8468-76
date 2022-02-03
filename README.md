# Decreto Estadual 8.468/1976

<br>

Por meio do [Decreto Estadual 8.468](https://www.cetesb.sp.gov.br/Institucional/documentos/Dec8468.pdf), de 08.09.1976, que *"aprova o Regulamento da Lei n° 997, de 31 de maio de 1976, que dispõe sobre a prevenção e o controle da poluição do meio ambiente"*, são aptresentados, dentre outros assuntos, os padrões de qualidade de águas interiores e padrões de lançamento de efluentes.

A lei sofreu diversas alterações, sendo a última pelo Decreto Estadual 54.487/09.

<br>

**Padrão de Qualidade**

- Artigo 10: Cursos d'água Classe 1
- Artigo 11: Cursos d'água Classe 2
- Artigo 12: Cursos d'água Classe 3
- Artigo 13: Cursos d'água Classe 4

<br>

**Padrão de Lançamento**

- Artigo 18: Lançamento em curso d'água (corpo receptor)
- Artigo 19-A: Lançamento na Rede de Esgoto

<br>

----

### Objetivo

<br>

O projeto objetiva disponibilizar os parâmetros de qualidade em formato adequado para utilização em análises computacionais.

<br>

----

### Como Instalar?

<br>

```python
pip install decreto-estadual-8468 --upgrade
```

<br>

----

### Como usar?

<br>

Para obter as informações da tabela, basta ajustar o *classe* e o *parametro*.

```python
from decreto_estadual_8468 import *

# Get Table
df_8468, list_classes = get_8468_parameters()

# Filter Data by "Classe"
df_8468, list_parametros = filter_by_classe(df_8468, classe='Classe 2')

# Filter Data by "Parâmetros"
dict_8468 = filter_by_parameters(df_8468, parametro='Oxigênio Dissolvido')
print(dict_8468)

# Set Tipo
set_type_desconformidade(dict_8468)
```

<br>

O resultado será um dicionário contendo as seguintes informações:

```python
{'tipo_padrao': 'qualidade',
 'padrao_qualidade': 'Classe 2',
 'parametro_descricao': 'Oxigênio Dissolvido',
 'parametro_sigla': 'OD',
 'valor_minimo_permitido': 5.0,
 'valor_maximo_permitido': nan,
 'unidade': 'mg/l ',
 'norma_referencia': 'Inciso V, Art. 11',
 'norma_texto': 'Oxigênio Dissolvido (OD), em qualquer amostra, não inferior a 5 mg/l (cinco miligramas por litro)'}
 ```

<br>

Caso queira testar, segue um [*Google Colab*](https://colab.research.google.com/drive/1QZjsB6i8w_BAyMm3z4CB0_liSYOFQpdy).

<br>

----

### *ToDo*

1. <strike>Tabular Parâmetros de Lançamento (Art. 18 e 19)</strike>
