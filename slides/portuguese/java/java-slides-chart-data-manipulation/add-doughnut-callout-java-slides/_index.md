---
"description": "Aprenda a adicionar chamadas de donut em slides Java usando o Aspose.Slides para Java. Guia passo a passo com código-fonte para apresentações aprimoradas."
"linktitle": "Adicionar chamada de rosca em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Adicionar chamada de rosca em slides Java"
"url": "/pt/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar chamada de rosca em slides Java


## Introdução à adição de uma chamada de rosca em slides Java usando Aspose.Slides para Java

Neste tutorial, mostraremos o processo de adição de uma chamada de rosca a um slide em Java usando o Aspose.Slides para Java. Uma chamada de rosca é um elemento de gráfico que pode ser usado para destacar pontos de dados específicos em um gráfico de rosca. Forneceremos instruções passo a passo e o código-fonte completo para sua conveniência.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Ambiente de desenvolvimento Java
2. Biblioteca Aspose.Slides para Java
3. Ambiente de Desenvolvimento Integrado (IDE) como Eclipse ou IntelliJ IDEA
4. Uma apresentação do PowerPoint onde você deseja adicionar o Doughnut Callout

## Etapa 1: configure seu projeto Java

1. Crie um novo projeto Java no IDE escolhido.
2. Adicione a biblioteca Aspose.Slides para Java ao seu projeto como uma dependência.

## Etapa 2: Inicializar a apresentação

Para começar, você precisa inicializar uma apresentação do PowerPoint e criar um slide onde deseja adicionar o texto explicativo do Donut. Aqui está o código para fazer isso:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Certifique-se de substituir `"Your Document Directory"` com o caminho real para o arquivo de apresentação do PowerPoint.

## Etapa 3: Crie um gráfico de rosca

Em seguida, você criará um gráfico de rosca no slide. Você pode personalizar a posição e o tamanho do gráfico conforme suas necessidades. Aqui está o código para adicionar um gráfico de rosca:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Etapa 4: personalize o gráfico de rosca

Agora, é hora de personalizar o gráfico de Rosquinha. Definiremos várias propriedades, como remover a legenda, configurar o tamanho do furo e ajustar o ângulo da primeira fatia. Aqui está o código:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Este trecho de código define as propriedades do gráfico de Rosquinha. Você pode ajustar os valores para atender às suas necessidades específicas.

## Etapa 5: Adicionar dados ao gráfico de rosca

Agora, vamos adicionar dados ao gráfico de Rosquinha. Também personalizaremos a aparência dos pontos de dados. Aqui está o código para fazer isso:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Personalize a aparência do ponto de dados aqui
        i++;
    }
    categoryIndex++;
}
```

Neste código, estamos adicionando categorias e pontos de dados ao gráfico de Rosquinha. Você pode personalizar ainda mais a aparência dos pontos de dados conforme necessário.

## Etapa 6: Salve a apresentação

Por fim, não se esqueça de salvar sua apresentação após adicionar o Doughnut Callout. Aqui está o código para salvar a apresentação:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Certifique-se de substituir `"chart.pptx"` com o nome de arquivo desejado.

Parabéns! Você adicionou com sucesso um Callout de Rosquinha a um slide Java usando o Aspose.Slides para Java. Agora você pode executar seu aplicativo Java para gerar a apresentação do PowerPoint com o gráfico de Rosquinha e o Callout.

## Código-fonte completo para adicionar chamada de rosca em slides Java

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
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(verdadeiro);
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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, abordamos o processo de adicionar um gráfico de rosca a um slide Java usando o Aspose.Slides para Java. Você aprendeu a criar um gráfico de rosca, personalizar sua aparência e adicionar pontos de dados. Sinta-se à vontade para aprimorar ainda mais suas apresentações com esta poderosa biblioteca e explorar mais opções de gráficos.

## Perguntas frequentes

### Como posso alterar a aparência do texto explicativo do donut?

Você pode personalizar a aparência do Callout de Rosca modificando as propriedades dos pontos de dados no gráfico. No código fornecido, você pode ver como definir a cor de preenchimento, a cor da linha, o estilo da fonte e outros atributos dos pontos de dados.

### Posso adicionar mais pontos de dados ao gráfico de rosca?

Sim, você pode adicionar quantos pontos de dados forem necessários ao gráfico de rosca. Basta estender os loops no código onde categorias e pontos de dados são adicionados e fornecer os dados e a formatação apropriados.

### Como posso ajustar a posição e o tamanho do gráfico de rosca no slide?

Você pode alterar a posição e o tamanho do gráfico de rosca modificando os parâmetros no `addChart` método. Os quatro números nesse método correspondem às coordenadas X e Y do canto superior esquerdo do gráfico e à sua largura e altura, respectivamente.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}