---
title: Criação de gráfico de radar em slides Java
linktitle: Criação de gráfico de radar em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar gráficos de radar em apresentações Java PowerPoint usando Aspose.Slides for Java API.
type: docs
weight: 10
url: /pt/java/chart-creation/radar-chart-creating-java-slides/
---

## Introdução à criação de um gráfico de radar em slides Java

Neste tutorial, iremos guiá-lo através do processo de criação de um gráfico de radar usando a API Aspose.Slides for Java. Os gráficos de radar são úteis para visualizar dados em um padrão circular, facilitando a comparação de várias séries de dados. Forneceremos instruções passo a passo junto com o código-fonte Java.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java integrada ao seu projeto. Você pode baixar a biblioteca em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: configurando a apresentação

Vamos começar configurando uma nova apresentação do PowerPoint e adicionando um slide a ela.

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Etapa 2: adicionar um gráfico de radar

A seguir, adicionaremos um gráfico de radar ao slide. Especificaremos a posição e as dimensões do gráfico.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Etapa 3: definir dados do gráfico

Agora definiremos os dados do gráfico. Isso envolve a criação de uma pasta de trabalho de dados, adição de categorias e adição de séries.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Definir título do gráfico
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Excluir séries e categorias geradas padrão
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Adicionando novas categorias
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Adicionando nova série
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Etapa 4: preencher os dados da série

Agora, preencheremos os dados da série para nosso gráfico de radar.

```java
// Preencher dados de série para a Série 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Definir cor da série
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Preencher dados de série para a Série 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Definir cor da série
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Etapa 5: Personalizando Eixos e Legendas

Vamos personalizar os eixos e as legendas do nosso gráfico de radar.

```java
// Definir posição da legenda
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Configurando propriedades de texto do eixo de categoria
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Configurando propriedades de texto de legendas
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Configurando propriedades de texto do eixo de valores
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Configurando o formato do número do eixo de valor
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Configurando o valor unitário principal do gráfico
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Etapa 6: salvando a apresentação

Por fim, salve a apresentação gerada com o gráfico de radar

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

É isso! Você criou com sucesso um gráfico de radar em uma apresentação do PowerPoint usando Aspose.Slides para Java. Agora você pode personalizar ainda mais este exemplo para atender às suas necessidades específicas.

## Código-fonte completo para criação de gráfico de radar em slides Java

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Acesse o primeiro slide
	ISlide sld = pres.getSlides().get_Item(0);
	// Adicionar gráfico de radar
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Configurando o índice da planilha de dados do gráfico
	int defaultWorksheetIndex = 0;
	// Obtendo a planilha de dados do gráfico
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Definir título do gráfico
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Excluir séries e categorias geradas padrão
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Adicionando novas categorias
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Adicionando nova série
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Agora preenchendo dados de série
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Definir cor da série
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Agora preenchendo outra série de dados
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Definir cor da série
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Definir posição da legenda
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Configurando propriedades de texto do eixo de categoria
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Configurando propriedades de texto de legendas
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Configurando propriedades de texto do eixo de valores
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Configurando o formato do número do eixo de valor
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Configurando o valor unitário principal do gráfico
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Salvar apresentação gerada
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, você aprendeu como criar um gráfico de radar em uma apresentação do PowerPoint usando Aspose.Slides para Java. Você pode aplicar esses conceitos para visualizar e apresentar seus dados de maneira eficaz em seus aplicativos Java.

## Perguntas frequentes

### Como posso alterar o título do gráfico?

Para alterar o título do gráfico, modifique a seguinte linha:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Posso adicionar mais séries de dados ao gráfico de radar?

Sim, você pode adicionar mais séries de dados seguindo as etapas da "Etapa 3" e da "Etapa 4" para cada série adicional que desejar incluir.

### Como posso personalizar as cores do gráfico?

 Você pode personalizar as cores da série modificando as linhas que definem as`SolidFillColor` propriedade para cada série. Por exemplo:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Como posso alterar os rótulos e a formatação dos eixos?

Consulte a "Etapa 5" para personalizar os rótulos e a formatação dos eixos, incluindo tamanho e cor da fonte.

### Como faço para salvar o gráfico em um formato de arquivo diferente?

 Você pode alterar o formato de saída modificando a extensão do arquivo no`outPath` variável e usando o apropriado`SaveFormat` . Por exemplo, para salvar como PDF, use`SaveFormat.Pdf`.