---
title: Configurando texto explicativo para rótulo de dados em slides Java
linktitle: Configurando texto explicativo para rótulo de dados em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como configurar chamadas para rótulos de dados em Aspose.Slides para Java. Guia passo a passo com código-fonte.
weight: 25
url: /pt/java/data-manipulation/setting-callout-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introdução à configuração de chamada para rótulo de dados em Aspose.Slides para Java

Neste tutorial, demonstraremos como configurar chamadas para rótulos de dados em um gráfico usando Aspose.Slides para Java. As frases de destaque podem ser úteis para destacar pontos de dados específicos em seu gráfico. Percorreremos o código passo a passo e forneceremos o código-fonte necessário.

## Pré-requisitos

- Você deve ter o Aspose.Slides para Java instalado.
- Crie um projeto Java e adicione a biblioteca Aspose.Slides ao seu projeto.

## Etapa 1: crie uma apresentação e adicione um gráfico

 Primeiro, precisamos criar uma apresentação e adicionar um gráfico a um slide. Certifique-se de substituir`"Your Document Directory"` com o caminho real para o diretório do seu documento.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Etapa 2: configurar o gráfico

A seguir, configuraremos o gráfico definindo propriedades como legenda, série e categorias.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configurar séries e categorias (você pode ajustar o número de séries e categorias)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Adicione pontos de dados aqui
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Etapa 3: personalizar rótulos de dados

Agora, personalizaremos os rótulos de dados, incluindo a configuração de textos explicativos para a última série.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Personalize a formatação do ponto de dados (preenchimento, linha, etc.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //Personalize a formatação da etiqueta (fonte, preenchimento, etc.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Ativar frases de destaque
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Etapa 4: salve a apresentação

Por fim, salve a apresentação com o gráfico configurado.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Agora, você configurou com êxito chamadas para rótulos de dados em um gráfico usando Aspose.Slides para Java. Personalize o código de acordo com seu gráfico específico e requisitos de dados.

## Código-fonte completo para definir chamada para rótulo de dados em slides Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, exploramos como configurar chamadas para rótulos de dados em um gráfico usando Aspose.Slides para Java. As frases de destaque são ferramentas valiosas para enfatizar pontos de dados específicos em seus gráficos e apresentações. Fornecemos um guia passo a passo junto com o código-fonte para ajudá-lo a obter essa personalização.

## Perguntas frequentes

### Como posso personalizar a aparência dos rótulos de dados?

Para personalizar a aparência dos rótulos de dados, você pode modificar propriedades como fonte, preenchimento e estilos de linha. Por exemplo:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Como posso ativar ou desativar chamadas para rótulos de dados?

 Para ativar ou desativar chamadas para rótulos de dados, use o`setShowLabelAsDataCallout` método. Defina-o para`true` para ativar chamadas e`false`para desativá-los.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Ativar frases de destaque
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Desativar frases de destaque
```

### Posso personalizar as linhas de chamada para rótulos de dados?

Sim, você pode personalizar as linhas líderes para rótulos de dados usando propriedades como estilo de linha, cor e largura. Por exemplo:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Habilitar linhas líderes
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Estas são algumas opções comuns de personalização para rótulos de dados e textos explicativos em Aspose.Slides para Java. Você pode adaptar ainda mais a aparência às suas necessidades específicas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
