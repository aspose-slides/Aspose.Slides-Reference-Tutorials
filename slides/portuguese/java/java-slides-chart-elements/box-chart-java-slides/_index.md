---
title: Gráfico de caixa em slides Java
linktitle: Gráfico de caixa em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar Box Charts em apresentações Java com Aspose.Slides. Guia passo a passo e código-fonte incluídos para visualização eficaz dos dados.
weight: 10
url: /pt/java/chart-elements/box-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introdução ao Box Chart em Aspose.Slides para Java

Neste tutorial, orientaremos você no processo de criação de um Box Chart usando Aspose.Slides para Java. Os gráficos de caixa são úteis para visualizar dados estatísticos com vários quartis e valores discrepantes. Forneceremos instruções passo a passo junto com o código-fonte para ajudá-lo a começar.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Biblioteca Aspose.Slides para Java instalada e configurada.
- Um ambiente de desenvolvimento Java configurado.

## Etapa 1: inicializar a apresentação

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Nesta etapa, inicializamos um objeto de apresentação usando o caminho para um arquivo PowerPoint existente ("test.pptx" neste exemplo).

## Etapa 2: crie o gráfico de caixa

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Nesta etapa, criamos um formato Box Chart no primeiro slide da apresentação. Também eliminamos quaisquer categorias e séries existentes do gráfico.

## Etapa 3: definir categorias

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 Nesta etapa definimos as categorias do Box Chart. Nós usamos o`IChartDataWorkbook` para adicionar categorias e rotulá-las de acordo.

## Etapa 4: crie a série

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Aqui, criamos uma série BoxAndWhisker para o gráfico e configuramos várias opções como método quartil, linha média, marcadores médios, pontos internos e pontos discrepantes.

## Etapa 5: adicionar pontos de dados

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Nesta etapa, adicionamos pontos de dados à série BoxAndWhisker. Esses pontos de dados representam os dados estatísticos do gráfico.

## Etapa 6: salve a apresentação

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Por fim, salvamos a apresentação com o Box Chart em um novo arquivo PowerPoint chamado “BoxAndWhisker.pptx”.

Parabéns! Você criou com sucesso um Box Chart usando Aspose.Slides para Java. Você pode personalizar ainda mais o gráfico ajustando várias propriedades e adicionando mais pontos de dados conforme necessário.

## Código-fonte completo para gráfico de caixa em slides Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, aprendemos como criar um Box Chart usando Aspose.Slides para Java. Os Box Charts são ferramentas valiosas para visualizar dados estatísticos, incluindo quartis e valores discrepantes. Fornecemos um guia passo a passo junto com o código-fonte para ajudá-lo a começar a criar gráficos de caixa em seus aplicativos Java.

## Perguntas frequentes

### Como posso alterar a aparência do Box Chart?

Você pode personalizar a aparência do Box Chart modificando propriedades como estilos de linha, cores e fontes. Consulte a documentação do Aspose.Slides para Java para obter detalhes sobre a personalização do gráfico.

### Posso adicionar séries de dados adicionais ao Box Chart?

 Sim, você pode adicionar várias séries de dados ao Box Chart criando`IChartSeries` objetos e adicionar pontos de dados a eles.

### O que significa QuartileMethodType.Exclusive?

 O`QuartileMethodType.Exclusive` configuração especifica que os cálculos do quartil devem ser feitos usando o método exclusivo. Você pode escolher diferentes métodos de cálculo de quartil dependendo de seus dados e requisitos.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
