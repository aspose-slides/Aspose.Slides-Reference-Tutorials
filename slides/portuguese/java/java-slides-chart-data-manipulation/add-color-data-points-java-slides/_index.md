---
"description": "Aprenda como adicionar cor a pontos de dados em slides Java usando o Aspose.Slides para Java."
"linktitle": "Adicionar cor aos pontos de dados em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Adicionar cor aos pontos de dados em slides Java"
"url": "/pt/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar cor aos pontos de dados em slides Java


## Introdução à adição de cores a pontos de dados em slides Java

Neste tutorial, demonstraremos como adicionar cor a pontos de dados em slides Java usando o Aspose.Slides para Java. Este guia passo a passo inclui exemplos de código-fonte para ajudar você a realizar essa tarefa.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

- Ambiente de desenvolvimento Java
- Biblioteca Aspose.Slides para Java

## Etapa 1: Crie uma nova apresentação

Primeiro, criaremos uma nova apresentação usando o Aspose.Slides para Java. Essa apresentação servirá como contêiner para o nosso gráfico.

```java
Presentation pres = new Presentation();
```

## Etapa 2: adicione um gráfico Sunburst

Agora, vamos adicionar um gráfico Sunburst à apresentação. Especificamos o tipo, a posição e o tamanho do gráfico.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Etapa 3: Acessar pontos de dados

Para modificar os pontos de dados no gráfico, precisamos acessar o `IChartDataPointCollection` objeto.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Etapa 4: personalizar pontos de dados

Nesta etapa, personalizaremos pontos de dados específicos. Aqui, alteraremos a cor dos pontos de dados e definiremos as configurações de rótulo.

```java
// Personalizar ponto de dados 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Personalizar ponto de dados 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Etapa 5: Salve a apresentação

Por fim, salve a apresentação com o gráfico personalizado.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Pronto! Você adicionou cor com sucesso a pontos de dados específicos em um slide Java usando o Aspose.Slides para Java.

## Código-fonte completo para adicionar cor a pontos de dados em slides Java

```java
Presentation pres = new Presentation();
try
{
	// O caminho para o diretório de documentos.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//PENDÊNCIA
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, você aprendeu a adicionar cor a pontos de dados em slides Java usando o Aspose.Slides para Java. Você pode personalizar ainda mais seus gráficos e apresentações de acordo com suas necessidades específicas.

## Perguntas frequentes

### Como posso alterar a cor de outros pontos de dados?

Para alterar a cor de outros pontos de dados, você pode seguir uma abordagem semelhante à mostrada na Etapa 4. Acesse o ponto de dados que deseja personalizar e modifique suas configurações de cor e rótulo.

### Posso personalizar outros aspectos do gráfico?

Sim, você pode personalizar vários aspectos do gráfico, incluindo fontes, rótulos, títulos e muito mais. Consulte a [Documentação do Aspose.Slides para Java](https://reference.aspose.com/slides/java/) para opções detalhadas de personalização.

### Onde posso encontrar mais exemplos e documentação?

Você pode encontrar mais exemplos e documentação detalhada sobre o uso do Aspose.Slides para Java no [Documentação do Aspose.Slides](https://reference.aspose.com/slides/java/) site.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}