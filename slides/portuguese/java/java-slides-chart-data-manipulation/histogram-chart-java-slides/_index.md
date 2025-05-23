---
"description": "Aprenda a criar gráficos de histograma em apresentações do PowerPoint usando o Aspose.Slides para Java. Guia passo a passo com código-fonte para visualização de dados."
"linktitle": "Gráfico de histograma em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Gráfico de histograma em slides Java"
"url": "/pt/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico de histograma em slides Java


## Introdução ao gráfico de histograma em slides Java usando Aspose.Slides

Neste tutorial, guiaremos você pelo processo de criação de um gráfico de histograma em uma apresentação do PowerPoint usando a API Aspose.Slides para Java. Um gráfico de histograma é usado para representar a distribuição de dados em um intervalo contínuo.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada. Você pode baixá-la do site [Site Aspose](https://releases.aspose.com/slides/java/).

## Etapa 1: Inicialize seu projeto

Crie um projeto Java e inclua a biblioteca Aspose.Slides nas dependências do seu projeto.

## Etapa 2: Importar bibliotecas necessárias

```java
import com.aspose.slides.*;
```

## Etapa 3: Carregar uma apresentação existente

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Certifique-se de substituir `"Your Document Directory"` com o caminho real para o seu documento do PowerPoint.

## Etapa 4: Crie um gráfico de histograma

Agora, vamos criar um gráfico de histograma em um slide da apresentação.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Adicionar pontos de dados à série
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Defina o tipo de agregação do eixo horizontal como Automático
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Salvar a apresentação
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Neste código, primeiro limpamos todas as categorias e séries existentes do gráfico. Em seguida, adicionamos pontos de dados à série usando o `getDataPoints().addDataPointForHistogramSeries` método. Por fim, definimos o tipo de agregação do eixo horizontal como Automático e salvamos a apresentação.

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

Neste tutorial, exploramos como criar um gráfico de histograma em uma apresentação do PowerPoint usando a API Aspose.Slides para Java. Gráficos de histograma são ferramentas valiosas para visualizar a distribuição de dados em um intervalo contínuo e podem ser um complemento poderoso para suas apresentações, especialmente quando se trata de conteúdo estatístico ou analítico.

## Perguntas frequentes

### Como instalo o Aspose.Slides para Java?

Você pode baixar a biblioteca Aspose.Slides para Java em [aqui](https://releases.aspose.com/slides/java/). Siga as instruções de instalação fornecidas no site.

### Para que serve um gráfico de histograma?

Um gráfico de histograma é usado para visualizar a distribuição de dados em um intervalo contínuo. É comumente usado em estatística para representar distribuições de frequência.

### Posso personalizar a aparência do gráfico de histograma?

Sim, você pode personalizar a aparência do gráfico, incluindo suas cores, rótulos e eixos, usando a API Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}