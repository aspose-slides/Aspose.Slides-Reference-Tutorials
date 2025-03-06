---
title: Propriedades de fonte para legenda individual em slides Java
linktitle: Propriedades de fonte para legenda individual em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprimore as apresentações do PowerPoint com estilos, tamanhos e cores de fonte personalizados para legendas individuais em Java Slides usando Aspose.Slides for Java.
type: docs
weight: 12
url: /pt/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

## Introdução às propriedades de fonte para legenda individual em slides Java

Neste tutorial, exploraremos como definir propriedades de fonte para uma legenda individual em Java Slides usando Aspose.Slides for Java. Ao personalizar as propriedades da fonte, você pode tornar suas legendas mais atraentes visualmente e informativas em suas apresentações do PowerPoint.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java integrada ao seu projeto. Você pode baixá-lo no[Aspose.Slides para documentação Java](https://reference.aspose.com/slides/java/).

## Etapa 1: inicializar a apresentação e adicionar gráfico

Primeiro, vamos começar inicializando uma apresentação do PowerPoint e adicionando um gráfico a ela. Neste exemplo, usaremos um gráfico de colunas agrupadas como ilustração.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // O resto do código vai aqui
} finally {
    if (pres != null) pres.dispose();
}
```

 Substituir`"Your Document Directory"` com o diretório real onde seu documento PowerPoint está localizado.

## Etapa 2: personalizar propriedades de fonte para legenda

Agora, vamos personalizar as propriedades da fonte para uma entrada de legenda individual no gráfico. Neste exemplo, temos como alvo a segunda entrada da legenda (índice 1), mas você pode ajustar o índice de acordo com seus requisitos específicos.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Aqui está o que cada linha de código faz:

- `get_Item(1)` recupera a segunda entrada da legenda (índice 1). Você pode alterar o índice para direcionar uma entrada de legenda diferente.
- `setFontBold(NullableBool.True)` define a fonte para negrito.
- `setFontHeight(20)` define o tamanho da fonte para 20 pontos.
- `setFontItalic(NullableBool.True)` define a fonte para itálico.
- `setFillType(FillType.Solid)` especifica que o texto de entrada da legenda deve ter um preenchimento sólido.
- `getSolidFillColor().setColor(Color.BLUE)` define a cor de preenchimento para azul. Você pode substituir`Color.BLUE` com a cor desejada.

## Etapa 3: salve a apresentação modificada

Por fim, salve a apresentação modificada em um novo arquivo para preservar as alterações.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Substituir`"output.pptx"` com o nome do arquivo de saída de sua preferência.

É isso! Você personalizou com êxito as propriedades da fonte para uma entrada de legenda individual em uma apresentação do Java Slides usando Aspose.Slides for Java.

## Código-fonte completo para propriedades de fonte para legenda individual em slides Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, aprendemos como personalizar as propriedades da fonte para uma legenda individual em Java Slides usando Aspose.Slides for Java. Ao ajustar estilos, tamanhos e cores de fontes, você pode aprimorar o apelo visual e a clareza de suas apresentações em PowerPoint.

## Perguntas frequentes

### Como posso alterar a cor da fonte?

 Para alterar a cor da fonte, use`tf.getPortionFormat().getFontColor().setColor(yourColor)` em vez de alterar a cor de preenchimento. Substituir`yourColor` com a cor de fonte desejada.

### Como modifico outras propriedades da legenda?

Você pode modificar várias outras propriedades da legenda, como posição, tamanho e formato. Consulte a documentação do Aspose.Slides for Java para obter informações detalhadas sobre como trabalhar com legendas.

### Posso aplicar essas alterações a diversas entradas de legenda?

 Sim, você pode percorrer as entradas da legenda e aplicar essas alterações a várias entradas ajustando o índice em`get_Item(index)` e repetindo o código de personalização.

Lembre-se de descartar o objeto de apresentação quando terminar para liberar recursos:

```java
if (pres != null) pres.dispose();
```