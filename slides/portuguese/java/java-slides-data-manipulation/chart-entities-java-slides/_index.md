---
"description": "Aprenda a criar e personalizar gráficos Java Slides com o Aspose.Slides. Aprimore suas apresentações com entidades gráficas poderosas."
"linktitle": "Entidades de Gráfico em Slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Entidades de Gráfico em Slides Java"
"url": "/pt/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Entidades de Gráfico em Slides Java


## Introdução às Entidades de Gráfico em Slides Java

Gráficos são ferramentas poderosas para visualizar dados em apresentações. Seja para criar relatórios empresariais, apresentações acadêmicas ou qualquer outro tipo de conteúdo, os gráficos ajudam a transmitir informações de forma eficaz. O Aspose.Slides para Java oferece recursos robustos para trabalhar com gráficos, tornando-se uma opção ideal para desenvolvedores Java.

## Pré-requisitos

Antes de mergulharmos no mundo das entidades gráficas, certifique-se de ter os seguintes pré-requisitos em vigor:

- Java Development Kit (JDK) instalado
- Biblioteca Aspose.Slides para Java baixada e adicionada ao seu projeto
- Conhecimento básico de programação Java

Agora, vamos começar a criar e personalizar gráficos usando o Aspose.Slides para Java.

## Etapa 1: Criando uma apresentação

O primeiro passo é criar uma nova apresentação onde você adicionará seu gráfico. Aqui está um trecho de código para criar uma apresentação:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: Adicionar um gráfico

Depois de preparar sua apresentação, é hora de adicionar um gráfico. Neste exemplo, adicionaremos um gráfico de linhas simples com marcadores. Veja como fazer isso:

```java
// Acessando o primeiro slide
ISlide slide = pres.getSlides().get_Item(0);

// Adicionando o gráfico de amostra
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Etapa 3: Personalizando o título do gráfico

Um gráfico bem definido deve ter um título. Vamos definir um título para o nosso gráfico:

```java
// Título do gráfico de configuração
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Etapa 4: Formatando linhas de grade

Você pode formatar as linhas de grade principais e secundárias do seu gráfico. Vamos definir a formatação para as linhas de grade do eixo vertical:

```java
// Definindo o formato das linhas de grade principais para o eixo de valor
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Definindo o formato das linhas de grade secundárias para o eixo de valor
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Etapa 5: Personalizando o Eixo de Valor

Você tem controle sobre o formato numérico e os valores máximo e mínimo do eixo de valores. Veja como personalizá-lo:

```java
// Definindo o formato do número do eixo de valor
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Definindo valores máximos e mínimos do gráfico
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Etapa 6: Adicionando o título do eixo de valor

Para tornar seu gráfico mais informativo, você pode adicionar um título ao eixo de valor:

```java
// Definindo o título do eixo de valor
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Etapa 7: Formatando o Eixo da Categoria

O eixo de categorias, que normalmente representa categorias de dados, também pode ser personalizado:

```java
// Definindo o formato das linhas de grade principais para o eixo de categoria
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Definindo o formato das linhas de grade secundárias para o eixo de categoria
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Etapa 8: Adicionando legendas

As legendas ajudam a explicar as séries de dados no seu gráfico. Vamos personalizar as legendas:

```java
// Definindo propriedades de texto de legendas
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Definir legendas de gráficos de exibição sem sobreposição de gráficos
chart.getLegend().setOverlay(true);
```

## Etapa 9: Salvando a apresentação

Por fim, salve sua apresentação com o gráfico:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para entidades de gráfico em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie um diretório se ele ainda não estiver presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instanciando apresentação // Instanciando apresentação
Presentation pres = new Presentation();
try
{
	// Acessando o primeiro slide
	ISlide slide = pres.getSlides().get_Item(0);
	// Adicionando o gráfico de amostra
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Título do gráfico de configuração
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Definindo o formato das linhas de grade principais para o eixo de valor
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Definindo o formato das linhas de grade secundárias para o eixo de valor
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Definindo o formato do número do eixo de valor
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Definindo valores máximos e mínimos do gráfico
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Definindo propriedades de texto do eixo de valor
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Definindo o título do eixo de valor
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Configuração do formato da linha do eixo de valor: agora obsoleto
	// gráfico.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Definindo o formato das linhas de grade principais para o eixo de categoria
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Definindo o formato das linhas de grade secundárias para o eixo de categoria
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Definindo propriedades de texto do eixo de categoria
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Título da categoria de configuração
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Definindo a posição do rótulo do eixo da categoria
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Definindo o ângulo de rotação do rótulo do eixo da categoria
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Definindo propriedades de texto de legendas
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Definir legendas de gráficos de exibição sem sobreposição de gráficos
	chart.getLegend().setOverlay(true);
	// Traçando a primeira série no eixo de valor secundário
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = verdadeiro;
	// Definindo a cor da parede de fundo do gráfico
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Definindo a cor da área de plotagem
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

Neste artigo, exploramos o mundo das entidades gráficas no Java Slides usando o Aspose.Slides para Java. Você aprendeu a criar, personalizar e manipular gráficos para aprimorar suas apresentações. Os gráficos não apenas tornam seus dados visualmente atraentes, mas também ajudam seu público a entender informações complexas com mais facilidade.

## Perguntas frequentes

### Como altero o tipo de gráfico?

Para alterar o tipo de gráfico, use o `chart.setType()` método e especifique o tipo de gráfico desejado.

### Posso adicionar várias séries de dados a um gráfico?

Sim, você pode adicionar várias séries de dados a um gráfico usando o `chart.getChartData().getSeries().addSeries()` método.

### Como posso personalizar as cores do gráfico?

Você pode personalizar as cores do gráfico definindo o formato de preenchimento para vários elementos do gráfico, como linhas de grade, título e legendas.

### Posso criar gráficos 3D?

Sim, o Aspose.Slides para Java suporta a criação de gráficos 3D. Você pode definir o `ChartType` para um tipo de gráfico 3D para criar um.

### O Aspose.Slides para Java é compatível com as versões mais recentes do Java?

Sim, o Aspose.Slides para Java é atualizado regularmente para oferecer suporte às versões mais recentes do Java e fornece compatibilidade com uma ampla variedade de ambientes Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}