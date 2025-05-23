---
"date": "2025-04-22"
"description": "Aprenda a exibir rótulos de porcentagem em gráficos de apresentações do PowerPoint sem esforço usando o Aspose.Slides para Python. Perfeito para aprimorar a visualização de dados."
"title": "Como exibir rótulos de porcentagem em gráficos usando Aspose.Slides para Python - Um guia completo"
"url": "/pt/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como exibir rótulos de porcentagem em gráficos usando Aspose.Slides para Python

## Introdução

Visualizar dados de forma eficaz é crucial em apresentações e relatórios, especialmente quando você deseja destacar proporções ou distribuições com clareza. Mas e se você precisar que essas porcentagens sejam exibidas diretamente em seus gráficos? Este guia completo o orientará no uso **Aspose.Slides para Python** para exibir valores percentuais como rótulos em um gráfico sem esforço.

### O que você aprenderá:
- Como criar e incorporar gráficos em apresentações do PowerPoint usando Aspose.Slides para Python.
- Exibindo pontos de dados como rótulos de porcentagem em seus gráficos.
- Salvar e gerenciar apresentações do PowerPoint com eficiência.

Pronto para começar a adicionar visuais interessantes aos seus dados? Vamos primeiro analisar o que você precisa antes de mergulhar no código!

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:
- **Aspose.Slides para Python**: Esta biblioteca é essencial para criar e manipular apresentações do PowerPoint programaticamente.
- **Ambiente Python**: Uma compreensão básica da programação Python e configuração do ambiente.
- **Gerenciador de Pacotes PIP**: Usado para instalar o Aspose.Slides.

## Configurando Aspose.Slides para Python

Para começar a usar o Aspose.Slides, primeiro você precisa instalá-lo:

```bash
pip install aspose.slides
```

### Etapas de aquisição de licença:
Você pode começar com um teste gratuito ou obter uma licença temporária para explorar todos os recursos do Aspose.Slides. Para uso prolongado, considere adquirir uma assinatura.

#### Inicialização e configuração básicas

Uma vez instalado, você inicializará seu ambiente de apresentação assim:

```python
import aspose.slides as slides

# Inicializar um objeto de apresentação
def create_presentation():
    with slides.Presentation() as presentation:
        # Seu código aqui
```

## Guia de Implementação

Agora que estamos configurados, vamos começar a exibir porcentagens em gráficos.

### Criando o gráfico e adicionando dados

#### Visão geral
Criaremos um gráfico de colunas empilhadas com rótulos de porcentagem para cada ponto de dados, permitindo que os visualizadores vejam as proporções exatas rapidamente.

##### Etapa 1: adicione um gráfico ao seu slide

```python
# Acesse o primeiro slide da sua apresentação
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Adicionar um gráfico de colunas empilhadas
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Este trecho de código adiciona um gráfico básico ao primeiro slide. O `add_chart` O método especifica o tipo de gráfico, sua posição e tamanho.

##### Etapa 2: Calcular os valores totais das categorias

```python
def calculate_totals(chart):
    total_for_category = []
    # Some os valores de todas as séries para cada categoria
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Este loop calcula o total de todos os pontos de dados nas séries, o que é crucial para cálculos percentuais.

#### Definindo rótulos de porcentagem

##### Etapa 3: Configurar pontos de dados da série

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Defina opções de rótulo padrão para ocultar informações não essenciais
        series.labels.default_data_label_format.show_legend_key = False
        
        # Calcular e definir rótulos de porcentagem
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Crie uma parte do texto com o valor percentual
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Limpar rótulos existentes e adicionar novo rótulo de porcentagem
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Ocultar outros elementos do rótulo de dados
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Este segmento processa cada ponto de dados para calcular sua porcentagem do total e o atribui como um rótulo.

### Salvando sua apresentação

```python
def save_presentation(presentation, output_directory):
    # Salve sua apresentação com modificações
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}