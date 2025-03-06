---
title: Ocultar informações do gráfico em slides Java
linktitle: Ocultar informações do gráfico em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como ocultar elementos do gráfico em Java Slides com Aspose.Slides for Java. Personalize apresentações para maior clareza e estética com orientação passo a passo e código-fonte.
weight: 13
url: /pt/java/customization-and-formatting/hide-information-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introdução para ocultar informações do gráfico em slides Java

Neste tutorial, exploraremos como ocultar vários elementos de um gráfico em Java Slides usando a API Aspose.Slides for Java. Você pode usar este código para personalizar seus gráficos conforme necessário para suas apresentações.

## Etapa 1: Configurando o Ambiente

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java adicionada ao seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 2: crie uma nova apresentação

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 3: adicionar um gráfico ao slide

Adicionaremos um gráfico de linhas com marcadores a um slide e depois ocultaremos vários elementos do gráfico.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Etapa 4: ocultar o título do gráfico

Você pode ocultar o título do gráfico da seguinte maneira:

```java
chart.setTitle(false);
```

## Etapa 5: ocultar o eixo de valores

Para ocultar o eixo de valores (eixo vertical), use o seguinte código:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Etapa 6: ocultar o eixo da categoria

Para ocultar o eixo da categoria (eixo horizontal), use este código:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Etapa 7: ocultar a legenda

Você pode ocultar a legenda do gráfico assim:

```java
chart.setLegend(false);
```

## Etapa 8: ocultar linhas de grade principais

Para ocultar as principais linhas de grade do eixo horizontal, você pode usar o seguinte código:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Etapa 9: remover séries

Se quiser remover todas as séries do gráfico, você pode usar um loop como este:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Etapa 10: personalizar a série de gráficos

Você pode personalizar a série de gráficos conforme necessário. Neste exemplo, alteramos o estilo do marcador, a posição do rótulo de dados, o tamanho do marcador, a cor da linha e o estilo do traço:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Etapa 11: salve a apresentação

Por fim, salve a apresentação em um arquivo:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

É isso! Você ocultou com sucesso vários elementos de um gráfico em Java Slides usando Aspose.Slides for Java. Você pode personalizar ainda mais seus gráficos e apresentações conforme necessário para seus requisitos específicos.

## Código-fonte completo para ocultar informações do gráfico em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Ocultando o título do gráfico
	chart.setTitle(false);
	///Eixo de valores ocultos
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Visibilidade do eixo de categoria
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Escondendo a lenda
	chart.setLegend(false);
	//Escondendo MajorGridLines
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Configurando a cor da linha da série
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Conclusão

Neste guia passo a passo, exploramos como ocultar vários elementos de um gráfico em Java Slides usando a API Aspose.Slides for Java. Isso pode ser extremamente útil quando você precisa personalizar seus gráficos para apresentações e torná-los mais atraentes visualmente ou adaptados às suas necessidades específicas.

## Perguntas frequentes

### Como posso personalizar ainda mais a aparência dos elementos do gráfico?

Você pode personalizar várias propriedades dos elementos do gráfico, como cor da linha, cor de preenchimento, estilo do marcador e muito mais, acessando as propriedades correspondentes da série do gráfico, marcadores, rótulos e formato.

### Posso ocultar pontos de dados específicos no gráfico?

Sim, você pode ocultar pontos de dados específicos manipulando os dados na série do gráfico. Você pode remover pontos de dados ou definir seus valores como nulos para ocultá-los.

### Como posso adicionar séries adicionais ao gráfico?

 Você pode adicionar mais séries ao gráfico usando o`IChartData.getSeries().add` método e especificando os pontos de dados para a nova série.

### É possível alterar o tipo de gráfico dinamicamente?

Sim, você pode alterar o tipo de gráfico dinamicamente criando um novo gráfico do tipo desejado e copiando os dados do gráfico antigo para o novo.

### Como posso alterar o título do gráfico e os rótulos dos eixos de forma programática?

Você pode definir o título e os rótulos do gráfico e dos eixos acessando suas respectivas propriedades e definindo o texto e a formatação desejados.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
