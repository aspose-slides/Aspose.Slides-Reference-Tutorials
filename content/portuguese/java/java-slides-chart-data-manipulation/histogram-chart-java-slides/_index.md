---
title: Gráfico de histograma em slides Java
linktitle: Gráfico de histograma em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar gráficos de histograma em apresentações do PowerPoint usando Aspose.Slides para Java. Guia passo a passo com código-fonte para visualização de dados.
type: docs
weight: 19
url: /pt/java/chart-data-manipulation/histogram-chart-java-slides/
---

## Introdução ao gráfico de histograma em slides Java usando Aspose.Slides

Neste tutorial, iremos guiá-lo através do processo de criação de um gráfico de histograma em uma apresentação do PowerPoint usando a API Aspose.Slides for Java. Um gráfico de histograma é usado para representar a distribuição de dados em um intervalo contínuo.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java instalada. Você pode baixá-lo no[Aspor site](https://releases.aspose.com/slides/java/).

## Etapa 1: inicialize seu projeto

Crie um projeto Java e inclua a biblioteca Aspose.Slides nas dependências do seu projeto.

## Etapa 2: importar as bibliotecas necessárias

```java
import com.aspose.slides.*;
```

## Etapa 3: carregar uma apresentação existente

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Certifique-se de substituir`"Your Document Directory"` com o caminho real para o seu documento PowerPoint.

## Etapa 4: crie um gráfico de histograma

Agora, vamos criar um gráfico de histograma em um slide da apresentação.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Adicione pontos de dados à série
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Defina o tipo de agregação do eixo horizontal como Automático
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Salve a apresentação
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Neste código, primeiro limpamos todas as categorias e séries existentes no gráfico. Em seguida, adicionamos pontos de dados à série usando o`getDataPoints().addDataPointForHistogramSeries` método. Por fim, definimos o tipo de agregação do eixo horizontal como Automático e salvamos a apresentação.

## Código-fonte completo para gráfico de histograma em slides Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, exploramos como criar um gráfico de histograma em uma apresentação do PowerPoint usando a API Aspose.Slides for Java. Os gráficos de histograma são ferramentas valiosas para visualizar a distribuição de dados em um intervalo contínuo e podem ser uma adição poderosa às suas apresentações, especialmente quando se trata de conteúdo estatístico ou analítico.

## Perguntas frequentes

### Como faço para instalar o Aspose.Slides para Java?

 Você pode baixar a biblioteca Aspose.Slides para Java em[aqui](https://releases.aspose.com/slides/java/). Siga as instruções de instalação fornecidas em seu site.

### Para que é usado um gráfico de histograma?

Um gráfico de histograma é usado para visualizar a distribuição de dados em um intervalo contínuo. É comumente usado em estatísticas para representar distribuições de frequência.

### Posso personalizar a aparência do gráfico de histograma?

Sim, você pode personalizar a aparência do gráfico, incluindo cores, rótulos e eixos, usando a API Aspose.Slides.