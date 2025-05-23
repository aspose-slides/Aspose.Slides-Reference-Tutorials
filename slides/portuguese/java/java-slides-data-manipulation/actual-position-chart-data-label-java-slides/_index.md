---
"description": "Aprenda a obter a posição real dos rótulos de dados do gráfico em Java Slides usando o Aspose.Slides para Java. Guia passo a passo com código-fonte."
"linktitle": "Obtenha a posição real do rótulo de dados do gráfico em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Obtenha a posição real do rótulo de dados do gráfico em slides Java"
"url": "/pt/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Obtenha a posição real do rótulo de dados do gráfico em slides Java


## Introdução à obtenção da posição real do rótulo de dados do gráfico em slides Java

Neste tutorial, você aprenderá a recuperar a posição real dos rótulos de dados do gráfico usando o Aspose.Slides para Java. Criaremos um programa Java que gera uma apresentação do PowerPoint com um gráfico, personaliza os rótulos de dados e, em seguida, adiciona formas que representam as posições desses rótulos.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java configurada no seu projeto Java.

## Etapa 1: Crie uma apresentação do PowerPoint

Primeiro, vamos criar uma nova apresentação do PowerPoint e adicionar um gráfico a ela. Personalizaremos os rótulos de dados do gráfico posteriormente neste tutorial.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Etapa 2: personalizar rótulos de dados
Agora, vamos personalizar os rótulos de dados para a série do gráfico. Definiremos a posição deles e exibiremos os valores.

```java
try {
    // ... (código anterior)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (código restante)
} finally {
    if (pres != null) pres.dispose();
}
```

## Etapa 3: Obtenha a posição real dos rótulos de dados
Nesta etapa, iteraremos pelos pontos de dados da série do gráfico e recuperaremos a posição real dos rótulos de dados que têm um valor maior que 4. Em seguida, adicionaremos elipses para representar essas posições.

```java
try {
    // ... (código anterior)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (código restante)
} finally {
    if (pres != null) pres.dispose();
}
```

## Etapa 4: Salve a apresentação
Por fim, salve a apresentação gerada em um arquivo.

```java
try {
    // ... (código anterior)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Código-fonte completo para obter a posição real do rótulo de dados do gráfico em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//PENDÊNCIA
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, você aprendeu a recuperar a posição real dos rótulos de dados do gráfico em Slides Java usando o Aspose.Slides para Java. Agora você pode usar esse conhecimento para aprimorar suas apresentações do PowerPoint com rótulos de dados personalizados e representações visuais de suas posições.

## Perguntas frequentes

### Como posso personalizar rótulos de dados em um gráfico?

Para personalizar rótulos de dados em um gráfico, você pode usar o `setDefaultDataLabelFormat` método na série do gráfico e definir propriedades como posição e visibilidade. Por exemplo:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Como posso adicionar formas para representar posições de rótulos de dados?

Você pode iterar pelos pontos de dados de uma série de gráficos e usar o `getActualX`, `getActualY`, `getActualWidth`, e `getActualHeight` métodos do rótulo de dados para obter sua posição. Em seguida, você pode adicionar formas usando o `addAutoShape` método. Aqui está um exemplo:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Como posso salvar a apresentação gerada?

Você pode salvar a apresentação gerada usando o `save` método. Forneça o caminho do arquivo desejado e o `SaveFormat` como parâmetros. Por exemplo:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}