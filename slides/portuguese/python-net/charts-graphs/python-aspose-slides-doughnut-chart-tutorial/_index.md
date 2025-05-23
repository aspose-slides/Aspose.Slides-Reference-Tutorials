---
"date": "2025-04-22"
"description": "Aprenda a criar gráficos de rosca com Python e Aspose.Slides. Este guia passo a passo aborda configuração, personalização e práticas recomendadas para aprimorar suas apresentações."
"title": "Como criar gráficos de rosca em Python usando Aspose.Slides&#58; um guia passo a passo"
"url": "/pt/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar gráficos de rosca em Python usando Aspose.Slides: um guia passo a passo

No âmbito da visualização de dados, apresentar informações de forma eficaz pode impactar significativamente a compreensão e a tomada de decisões. Seja elaborando uma apresentação de negócios ou analisando conjuntos de dados complexos, os gráficos são ferramentas essenciais. Entre os vários tipos de gráficos, os gráficos de rosca oferecem uma maneira atraente de representar dados proporcionais com um furo central intuitivo. Este guia passo a passo o guiará pela criação de um gráfico de rosca em Python usando o Aspose.Slides — uma biblioteca poderosa para manipular apresentações.

## que você aprenderá
- Como configurar e usar o Aspose.Slides para Python
- O processo de adicionar um gráfico de rosca aos slides da sua apresentação
- Personalizando séries e categorias dentro do gráfico
- Ajustando elementos visuais como rótulos, cores e efeitos de explosão
- Melhores práticas para otimizar o desempenho com Aspose.Slides

## Pré-requisitos
Antes de começar, certifique-se de ter:
- **Ambiente Python**: Python 3.x instalado na sua máquina.
- **Aspose.Slides para Python**: Instale esta biblioteca usando pip.
- **Noções básicas de programação em Python**: Familiaridade com loops e programação orientada a objetos será útil.

## Configurando Aspose.Slides para Python
Para começar, instale a biblioteca Aspose.Slides via pip:

```bash
pip install aspose.slides
```

### Aquisição de Licença
O Aspose oferece um teste gratuito para testar recursos sem limitações por tempo limitado. Para obtê-lo:
1. Visite o [Teste grátis](https://releases.aspose.com/slides/python-net/) página.
2. Siga as instruções para baixar e aplicar sua licença temporária.

Para uso contínuo, considere adquirir uma assinatura do [Página de compra](https://purchase.aspose.com/buy).

### Inicialização básica
Depois de configurar o Aspose.Slides, inicialize-o da seguinte maneira:

```python
import aspose.slides as slides

# Crie uma instância da classe Presentation.
with slides.Presentation() as pres:
    # Seu código para manipular apresentações vai aqui.

# Salve a apresentação após fazer alterações.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Guia de Implementação
Com o Aspose.Slides configurado, siga estas etapas para adicionar um gráfico de rosca à sua apresentação slide por slide.

### Criando uma nova apresentação e adicionando um slide
Comece criando uma instância do `Presentation` aula:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Acesse ou crie slides dentro deste contexto.
```

### Adicionando um gráfico de rosca ao primeiro slide
Acesse o primeiro slide e use o `add_chart` método. Especifique o tipo de gráfico como `DOUGHNUT`, juntamente com posição e tamanho:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Configurando dados do gráfico
Limpe os dados existentes e configure configurações como ocultar a legenda:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Adicionando Séries e Categorias
Adicione várias séries e categorias para um gráfico de rosca. Veja como criar 15 séries com propriedades específicas:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Adicione categorias de forma semelhante:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Adicione pontos de dados para cada série.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Personalize a aparência de cada ponto de dados.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Configure as definições de etiqueta para a última série.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Salvando a apresentação
Por fim, salve sua apresentação em um diretório especificado:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Aplicações práticas
Os gráficos de rosca são versáteis e podem ser usados em vários cenários, como:
1. **Alocação Orçamentária**: Exibindo como diferentes departamentos usam seus fundos alocados.
2. **Análise de Participação de Mercado**: Comparar a participação de mercado de produtos ou empresas concorrentes.
3. **Resultados da pesquisa**: Visualização de respostas a perguntas de pesquisas sobre preferências ou níveis de satisfação.

## Considerações de desempenho
Para garantir o desempenho ideal ao usar o Aspose.Slides:
- Minimize o uso de memória descartando os objetos corretamente após o uso.
- Carregue apresentações na memória somente quando necessário e feche-as o mais rápido possível.
- Considere processar slides em lote se estiver trabalhando com um grande número de gráficos.

## Conclusão
Seguindo este guia, você aprendeu a criar gráficos de rosca dinâmicos usando o Aspose.Slides para Python. Essas visualizações podem aprimorar suas apresentações, tornando os dados mais fáceis de entender e envolventes. Continue explorando os recursos da biblioteca para personalizar e otimizar ainda mais seus gráficos.

## Seção de perguntas frequentes
1. **Posso usar o Aspose.Slides sem comprar uma licença?**
   - Sim, você pode começar com uma licença de teste gratuita para fins de avaliação.
2. **Como altero as cores do gráfico no Aspose.Slides?**
   - Use o `fill_format` propriedade para definir a cor desejada para os elementos do seu gráfico.
3. **É possível exportar gráficos como imagens?**
   - Sim, você pode renderizar slides contendo gráficos em formatos de imagem usando os recursos de renderização da biblioteca.
4. **Quais são alguns problemas comuns ao adicionar gráficos?**
   - Certifique-se de que todos os pontos de dados e categorias sejam adicionados corretamente antes de tentar salvar ou exibir seu gráfico.
5. **Posso integrar o Aspose.Slides com outras bibliotecas Python?**
   - Com certeza! Você pode usá-lo em conjunto com bibliotecas como o Pandas para aprimorar seus recursos de manipulação de dados.

## Recursos
- [Documentação do Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Baixe o Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Comprar uma licença](https://purchase.aspose.com/buy)
- [Teste gratuito e licença temporária](https://releases.aspose.com/slides/python-net/)
- [Fórum da Comunidade Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}