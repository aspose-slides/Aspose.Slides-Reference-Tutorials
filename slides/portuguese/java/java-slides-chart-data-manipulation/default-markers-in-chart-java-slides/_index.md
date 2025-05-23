---
"description": "Aprenda a criar slides em Java com marcadores padrão em gráficos usando o Aspose.Slides para Java. Guia passo a passo com código-fonte."
"linktitle": "Marcadores padrão no gráfico em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Marcadores padrão no gráfico em slides Java"
"url": "/pt/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Marcadores padrão no gráfico em slides Java


## Introdução aos marcadores padrão em gráficos em slides Java

Neste tutorial, exploraremos como criar um gráfico com marcadores padrão usando o Aspose.Slides para Java. Marcadores padrão são símbolos ou formas adicionados aos pontos de dados em um gráfico para destacá-los. Criaremos um gráfico de linhas com marcadores para visualizar os dados.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada no seu projeto Java.

## Etapa 1: Crie uma apresentação

Primeiro, vamos criar uma apresentação e adicionar um slide a ela. Em seguida, adicionaremos um gráfico ao slide.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Etapa 2: adicione um gráfico de linhas com marcadores

Agora, vamos adicionar um gráfico de linhas com marcadores ao slide. Também limparemos todos os dados padrão do gráfico.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Etapa 3: preencher dados do gráfico

Vamos preencher o gráfico com dados de exemplo. Neste exemplo, criaremos duas séries com pontos de dados e categorias.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Série 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Série 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Preenchendo dados de série
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Etapa 4: personalize o gráfico

Você pode personalizar ainda mais o gráfico, adicionando uma legenda e ajustando sua aparência.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Etapa 5: Salve a apresentação

Por fim, salve a apresentação com o gráfico no local desejado.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Pronto! Você criou um gráfico de linhas com marcadores padrão usando o Aspose.Slides para Java.

## Código-fonte completo para marcadores padrão em gráficos em slides Java

```java
        // O caminho para o diretório de documentos.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Pegue a segunda série de gráficos
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Agora preenchendo dados de série
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusão

Neste tutorial abrangente, você aprendeu a criar slides em Java com marcadores padrão em gráficos usando o Aspose.Slides para Java. Abordamos todo o processo, desde a configuração da apresentação até a personalização da aparência do gráfico e o salvamento do resultado.

## Perguntas frequentes

### Como posso alterar os símbolos dos marcadores?

Você pode personalizar os símbolos dos marcadores definindo o estilo do marcador para cada ponto de dados. Use `IDataPoint.setMarkerStyle()` para alterar o símbolo do marcador.

### Como ajusto as cores do gráfico?

Para modificar as cores do gráfico, você pode usar o `IChartSeriesFormat` e `IShapeFillFormat` interfaces para definir propriedades de preenchimento e linha.

### Posso adicionar rótulos aos pontos de dados?

Sim, você pode adicionar rótulos aos pontos de dados usando o `IDataPoint.getLabel()` método e personalizá-los conforme necessário.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}