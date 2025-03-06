---
title: Adicione cor aos pontos de dados em slides Java
linktitle: Adicione cor aos pontos de dados em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como adicionar cor a pontos de dados em slides Java usando Aspose.Slides for Java.
type: docs
weight: 10
url: /pt/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## Introdução para adicionar cor a pontos de dados em slides Java

Neste tutorial, demonstraremos como adicionar cor a pontos de dados em slides Java usando Aspose.Slides for Java. Este guia passo a passo inclui exemplos de código-fonte para ajudá-lo a realizar essa tarefa.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

- Ambiente de Desenvolvimento Java
- Biblioteca Aspose.Slides para Java

## Etapa 1: crie uma nova apresentação

Primeiro, criaremos uma nova apresentação usando Aspose.Slides for Java. Esta apresentação servirá como contêiner para nosso gráfico.

```java
Presentation pres = new Presentation();
```

## Etapa 2: adicionar um gráfico Sunburst

Agora, vamos adicionar um gráfico Sunburst à apresentação. Especificamos o tipo, posição e tamanho do gráfico.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Etapa 3: acessar pontos de dados

 Para modificar pontos de dados no gráfico, precisamos acessar o`IChartDataPointCollection` objeto.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Etapa 4: personalizar pontos de dados

Nesta etapa, personalizaremos pontos de dados específicos. Aqui, estamos alterando a cor dos pontos de dados e definindo as configurações do rótulo.

```java
// Personalizar o ponto de dados 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Personalizar o ponto de dados 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Etapa 5: salve a apresentação

Por fim, salve a apresentação com o gráfico customizado.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

É isso! Você adicionou cores com sucesso a pontos de dados específicos em um slide Java usando Aspose.Slides for Java.

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

Neste tutorial, você aprendeu como adicionar cor a pontos de dados em slides Java usando Aspose.Slides for Java. Você pode personalizar ainda mais seus gráficos e apresentações com base em seus requisitos específicos.

## Perguntas frequentes

### Como posso alterar a cor de outros pontos de dados?

Para alterar a cor de outros pontos de dados, você pode seguir uma abordagem semelhante mostrada na Etapa 4. Acesse o ponto de dados que deseja personalizar e modifique suas configurações de cor e rótulo.

### Posso personalizar outros aspectos do gráfico?

 Sim, você pode personalizar vários aspectos do gráfico, incluindo fontes, rótulos, títulos e muito mais. Consulte o[Documentação Aspose.Slides para Java](https://reference.aspose.com/slides/java/) para opções de personalização detalhadas.

### Onde posso encontrar mais exemplos e documentação?

 Você pode encontrar mais exemplos e documentação detalhada sobre como usar Aspose.Slides for Java no site[Documentação do Aspose.Slides](https://reference.aspose.com/slides/java/) local na rede Internet.