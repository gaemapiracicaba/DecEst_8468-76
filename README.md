# Decreto Estadual 8.468/1976

<br>

Por meio do [Decreto Estadual 8.468](https://www.cetesb.sp.gov.br/Institucional/documentos/Dec8468.pdf), de 08.09.1976, que *"aprova o Regulamento da Lei n° 997, de 31 de maio de 1976, que dispõe sobre a prevenção e o controle da poluição do meio ambiente"*, são mencionados, dentre outros assuntos, os padrões de qualidade de águas interiores e padrões de lançamento de efluentes.

<br>

**Padrão de Qualidade**

- Artigo 10: Cursos d'água Classe 1
- Artigo 11: Cursos d'água Classe 2
- Artigo 12: Cursos d'água Classe 3
- Artigo 13: Cursos d'água Classe 4

**Padrão de Lançamento**

- Artigo 18: Lançamento em curso d'água (corpo receptor)
- Artigo 19-A: Lançamento na Rede de Esgoto

<br>

----

### Objetivo

O presente repositório objetiva disponibilizar os parâmetros de qualidade em formato tabular, adequado para utilização em análises computacionais.

----

### Como usar?

Para obter as informações da tabela, basta ajustar o "padrao_qualidade" e o "parametro_descricao".

```python
import pandas as pd

# Read Data
url = 'https://raw.githubusercontent.com/gaemapiracicaba/norma_dec_8468-76/main/data/tab_DecEst8468.xlsx'
df = pd.read_excel(url, index_col=0)

# Filter Data
df = df.loc[
    (df['padrao_qualidade'] == 'Classe 2') & 
    (df['parametro_descricao'] == 'Oxigênio Dissolvido'),
]

# Check and Get Results
if len(df) == 1:
    data = df.to_dict(orient='records')[0]
    display(data)
else:
    print('Erro')
```

<br>

O resultado será um dicionário contendo as seguintes informações:

```python
{'padrao_qualidade': 'Classe 2',
 'parametro_descricao': 'Oxigênio Dissolvido',
 'parametro_sigla': 'OD',
 'valor_minimo_permitido': 5.0,
 'valor_maximo_permitido': nan,
 'unidade': 'mg/l ',
 'norma_referencia': 'Inciso V, Art. 11',
 'norma_texto': 'Oxigênio Dissolvido (OD), em qualquer amostra, não inferior a 5 mg/l (cinco miligramas por litro)'}
```

----

### *ToDo*

1. Tabular parâmetros de lançamento (Art. 18 e 19)
