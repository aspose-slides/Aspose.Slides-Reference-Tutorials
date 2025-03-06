---
title: Gráfico de mapa em slides Java
linktitle: Gráfico de mapa em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Crie gráficos de mapas impressionantes em apresentações do PowerPoint com Aspose.Slides para Java. Guia passo a passo e código-fonte para desenvolvedores Java.
weight: 15
url: /pt/java/chart-elements/map-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico de mapa em slides Java


## Introdução ao mapa gráfico em slides Java usando Aspose.Slides para Java

Neste tutorial, iremos guiá-lo através do processo de criação de um mapa gráfico em uma apresentação do PowerPoint usando Aspose.Slides para Java. Os gráficos de mapas são uma ótima maneira de visualizar dados geográficos em suas apresentações.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java integrada ao seu projeto Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: configure seu projeto

Certifique-se de ter configurado seu projeto Java e adicionado a biblioteca Aspose.Slides para Java ao caminho de classe do seu projeto.

## Etapa 2: crie uma apresentação em PowerPoint

Primeiro, vamos criar uma nova apresentação em PowerPoint.

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## Etapa 3: adicionar um mapa gráfico

Agora, adicionaremos um mapa gráfico à apresentação.

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## Etapa 4: adicionar dados ao mapa gráfico

Vamos adicionar alguns dados ao mapa gráfico. Criaremos uma série e adicionaremos pontos de dados a ela.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## Etapa 5: adicionar categorias

Precisamos adicionar categorias ao mapa, representando diferentes regiões geográficas.

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## Etapa 6: personalizar pontos de dados

Você pode personalizar pontos de dados individuais. Neste exemplo, alteramos a cor e o valor de um ponto de dados específico.

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Etapa 7: salve a apresentação

Por fim, salve a apresentação com o mapa gráfico.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

É isso! Você criou um mapa gráfico em uma apresentação do PowerPoint usando Aspose.Slides para Java. Você pode personalizar ainda mais o gráfico e explorar outros recursos oferecidos pelo Aspose.Slides para aprimorar suas apresentações.

## Código-fonte completo para mapa gráfico em slides Java

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//criar gráfico vazio
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//Adicione séries e alguns pontos de dados
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//adicionar categorias
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//alterar o valor do ponto de dados
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//definir a aparência do ponto de dados
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Conclusão

Neste tutorial, percorremos o processo de criação de um mapa gráfico em uma apresentação do PowerPoint usando Aspose.Slides para Java. Os gráficos de mapas são uma forma eficaz de visualizar dados geográficos, tornando suas apresentações mais envolventes e informativas. Vamos resumir as principais etapas:

## Perguntas frequentes

### Como posso alterar o tipo de gráfico do mapa?

 Você pode alterar o tipo de gráfico substituindo`ChartType.Map` com o tipo de gráfico desejado ao criar o gráfico na Etapa 3.

### Como posso personalizar a aparência do mapa gráfico?

 Você pode personalizar a aparência do gráfico modificando as propriedades do`dataPoint` objeto na Etapa 6. Você pode alterar cores, valores e muito mais.

### Posso adicionar mais pontos de dados e categorias?

 Sim, você pode adicionar quantos pontos de dados e categorias forem necessários. Basta usar o`series.getDataPoints().addDataPointForMapSeries()` e`chart.getChartData().getCategories().add()` métodos para adicioná-los.

### Como integro Aspose.Slides for Java ao meu projeto?

 Baixe a biblioteca de[aqui](https://releases.aspose.com/slides/java/) e adicione-o ao classpath do seu projeto.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
