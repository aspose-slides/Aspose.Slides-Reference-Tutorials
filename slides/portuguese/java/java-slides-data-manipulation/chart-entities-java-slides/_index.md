---
title: Entidades de gráfico em slides Java
linktitle: Entidades de gráfico em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda a criar e personalizar gráficos do Java Slides com Aspose.Slides. Aprimore suas apresentações com entidades gráficas poderosas.
weight: 13
url: /pt/java/data-manipulation/chart-entities-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introdução às entidades gráficas em slides Java

Os gráficos são ferramentas poderosas para visualizar dados em apresentações. Esteja você criando relatórios de negócios, apresentações acadêmicas ou qualquer outra forma de conteúdo, os gráficos ajudam a transmitir informações de maneira eficaz. Aspose.Slides for Java fornece recursos robustos para trabalhar com gráficos, tornando-o uma escolha ideal para desenvolvedores Java.

## Pré-requisitos

Antes de mergulharmos no mundo das entidades gráficas, certifique-se de ter os seguintes pré-requisitos em vigor:

- Kit de desenvolvimento Java (JDK) instalado
- Biblioteca Aspose.Slides para Java baixada e adicionada ao seu projeto
- Conhecimento básico de programação Java

Agora, vamos começar a criar e personalizar gráficos usando Aspose.Slides para Java.

## Etapa 1: Criando uma apresentação

O primeiro passo é criar uma nova apresentação onde você adicionará seu gráfico. Aqui está um trecho de código para criar uma apresentação:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: adicionar um gráfico

Depois de ter sua apresentação pronta, é hora de adicionar um gráfico. Neste exemplo, adicionaremos um gráfico de linhas simples com marcadores. Veja como você pode fazer isso:

```java
// Acessando o primeiro slide
ISlide slide = pres.getSlides().get_Item(0);

// Adicionando o gráfico de amostra
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Etapa 3: Personalização do título do gráfico

Um gráfico bem definido deve ter um título. Vamos definir um título para nosso gráfico:

```java
// Configurando o título do gráfico
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Etapa 4: formatação de linhas de grade

Você pode formatar as linhas de grade principais e secundárias do seu gráfico. Vamos definir alguma formatação para as linhas de grade do eixo vertical:

```java
// Configurando o formato das linhas de grade principais para o eixo de valor
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Configurando o formato das linhas de grade secundárias para o eixo de valor
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Etapa 5: Personalização do Eixo de Valor

Você tem controle sobre o formato numérico e os valores máximo e mínimo do eixo de valores. Veja como personalizá-lo:

```java
// Configurando o formato do número do eixo de valor
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Definir valores máximos e mínimos do gráfico
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Etapa 6: Adicionando título ao eixo de valor

Para tornar seu gráfico mais informativo, você pode adicionar um título ao eixo de valores:

```java
// Definir título do eixo de valor
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Etapa 7: formatação do eixo da categoria

O eixo de categoria, que normalmente representa categorias de dados, também pode ser personalizado:

```java
// Configurando o formato das linhas de grade principais para o eixo de categoria
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Configurando o formato das linhas de grade secundárias para o eixo de categoria
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Etapa 8: adicionar legendas

As legendas ajudam a explicar a série de dados no seu gráfico. Vamos personalizar as legendas:

```java
// Configurando propriedades de texto de legendas
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Definir mostrar legendas do gráfico sem gráfico sobreposto
chart.getLegend().setOverlay(true);
```

## Etapa 9: salvando a apresentação

Por fim, salve sua apresentação com o gráfico:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para entidades gráficas em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie um diretório se ainda não estiver presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instanciando apresentação// Instanciando apresentação
Presentation pres = new Presentation();
try
{
	// Acessando o primeiro slide
	ISlide slide = pres.getSlides().get_Item(0);
	// Adicionando o gráfico de amostra
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Configurando o título do gráfico
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Configurando o formato das linhas de grade principais para o eixo de valor
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Configurando o formato das linhas de grade secundárias para o eixo de valor
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Configurando o formato do número do eixo de valor
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Definir valores máximos e mínimos do gráfico
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Configurando propriedades de texto do eixo de valores
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Definir título do eixo de valor
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Configurando o formato da linha do eixo de valor: agora obsoleto
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Configurando o formato das linhas de grade principais para o eixo de categoria
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Configurando o formato das linhas de grade secundárias para o eixo de categoria
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Configurando propriedades de texto do eixo de categoria
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Configurando o título da categoria
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Definir a posição da etiqueta do eixo da categoria
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Configurando o ângulo de rotação da etiqueta do eixo da categoria
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Configurando propriedades de texto de legendas
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Definir mostrar legendas do gráfico sem gráfico sobreposto
	chart.getLegend().setOverlay(true);
	// Plotando a primeira série no eixo de valor secundário
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Definir a cor da parede posterior do gráfico
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	//Configurando a cor da área de plotagem
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Salvar apresentação
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste artigo, exploramos o mundo das entidades gráficas em Java Slides usando Aspose.Slides for Java. Você aprendeu como criar, personalizar e manipular gráficos para aprimorar suas apresentações. Os gráficos não apenas tornam seus dados visualmente atraentes, mas também ajudam seu público a compreender informações complexas com mais facilidade.

## Perguntas frequentes

### Como altero o tipo de gráfico?

 Para alterar o tipo de gráfico, use o`chart.setType()` método e especifique o tipo de gráfico desejado.

### Posso adicionar várias séries de dados a um gráfico?

 Sim, você pode adicionar várias séries de dados a um gráfico usando o`chart.getChartData().getSeries().addSeries()` método.

### Como posso personalizar as cores do gráfico?

Você pode personalizar as cores do gráfico definindo o formato de preenchimento de vários elementos do gráfico, como linhas de grade, títulos e legendas.

### Posso criar gráficos 3D?

 Sim, Aspose.Slides for Java suporta a criação de gráficos 3D. Você pode definir o`ChartType` para um tipo de gráfico 3D para criar um.

### O Aspose.Slides for Java é compatível com as versões mais recentes do Java?

Sim, o Aspose.Slides for Java é atualizado regularmente para oferecer suporte às versões mais recentes do Java e fornece compatibilidade em uma ampla variedade de ambientes Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
