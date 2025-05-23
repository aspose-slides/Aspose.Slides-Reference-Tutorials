---
"date": "2025-04-22"
"description": "Aprenda a personalizar fontes de gráficos em apresentações do PowerPoint usando o Aspose.Slides com Python. Siga este guia para obter etapas detalhadas e aplicações práticas."
"title": "Como personalizar fontes de gráficos no PowerPoint usando Aspose.Slides para Python"
"url": "/pt/python-net/charts-graphs/customize-chart-fonts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como personalizar fontes de gráficos no PowerPoint usando Aspose.Slides para Python

## Introdução
Deseja aprimorar o apelo visual dos seus gráficos em apresentações do PowerPoint usando Python? Você não está sozinho! Muitos desenvolvedores enfrentam desafios ao tentar personalizar fontes de gráficos programaticamente. Este guia o guiará pela configuração de propriedades de fonte para gráficos no PowerPoint usando **Aspose.Slides para Python**. Ao dominar essas técnicas, você pode criar slides visualmente atraentes e com aparência profissional sem esforço.

Neste tutorial, abordaremos:
- Configurando Aspose.Slides para Python
- Personalizando fontes de gráficos com facilidade
- Aplicações práticas para seus projetos

Vamos começar garantindo que você tenha tudo pronto!

### Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos atendidos:
1. **Ambiente Python**: Certifique-se de ter o Python instalado (versão 3.6 ou superior).
2. **Aspose.Slides para Python**: Você precisará desta biblioteca para manipular arquivos do PowerPoint.
3. **Conhecimento básico**: Familiaridade com programação Python e um conhecimento básico de trabalho com bibliotecas serão úteis.

## Configurando Aspose.Slides para Python
Para começar, você precisará instalar o `aspose.slides` biblioteca usando pip:

```bash
pip install aspose.slides
```

### Etapas de aquisição de licença
- **Teste grátis**: Baixe uma versão de teste gratuita em [Site oficial da Aspose](https://releases.aspose.com/slides/python-net/).
- **Licença Temporária**:Para testes mais abrangentes, adquira uma licença temporária por meio de [página de compra](https://purchase.aspose.com/temporary-license/).
- **Comprar**:Se você achar a ferramenta inestimável para suas necessidades, considere adquirir uma licença completa da [Site de compra Aspose](https://purchase.aspose.com/buy).

Uma vez instalado e licenciado, inicialize o Aspose.Slides em Python:

```python
import aspose.slides as slides

# Inicialize o objeto Presentation com slides.Presentation() como pres:
    # Seu código vai aqui
```

## Guia de Implementação
Nesta seção, exploraremos como definir as propriedades da fonte do gráfico passo a passo.

### Adicionando um gráfico de colunas agrupadas
Primeiro, vamos adicionar um gráfico de colunas agrupadas à nossa apresentação:

```python
# Adicione um gráfico de colunas agrupadas na posição e tamanho especificados.
chart = pres.slides[0].shapes.add_chart(
    slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 500, 400
)
```
**Explicação**: Este snippet adiciona um novo gráfico ao primeiro slide da sua apresentação. O `add_chart` O método requer que você especifique o tipo de gráfico, sua posição e tamanho no slide.

### Definindo propriedades da fonte
Em seguida, vamos definir a altura da fonte do texto em nosso gráfico:

```python
# Defina a altura da fonte do texto no gráfico.
chart.text_format.portion_format.font_height = 20
```
**Explicação**: Esta linha ajusta o tamanho da fonte de todas as partes do texto no seu gráfico. `font_height` A propriedade é especificada em pontos, e você pode ajustar esse valor para atender às suas necessidades de design.

### Exibindo rótulos de dados
Para melhorar a legibilidade, exibiremos valores em rótulos de dados:

```python
# Exibir valores nos rótulos de dados da primeira série.
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```
**Explicação**: Esta configuração garante que cada ponto de dados da primeira série mostre seu valor. Isso é especialmente útil para transmitir informações precisas rapidamente.

### Salvando sua apresentação
Por fim, salve sua apresentação no local desejado:

```python
# Salve a apresentação em um diretório de saída especificado.
pres.save(
    "YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_chart_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}