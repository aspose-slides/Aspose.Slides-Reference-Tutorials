---
title: Definir modo de layout em slides Java
linktitle: Definir modo de layout em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como definir modos de layout para slides Java usando Aspose.Slides. Personalize o posicionamento e o dimensionamento do gráfico neste guia passo a passo com código-fonte.
weight: 23
url: /pt/java/data-manipulation/set-layout-mode-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introdução à definição do modo de layout em slides Java

Neste tutorial, aprenderemos como definir o modo de layout de um gráfico em slides Java usando Aspose.Slides for Java. O modo de layout determina o posicionamento e o tamanho do gráfico no slide.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java instalada e configurada em seu projeto Java. Você pode baixar a biblioteca em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: crie uma apresentação

Primeiro, precisamos criar uma nova apresentação.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Etapa 2: adicionar um slide e um gráfico

A seguir, adicionaremos um slide e um gráfico a ele. Neste exemplo, criaremos um gráfico de colunas agrupadas.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Etapa 3: definir o layout do gráfico

 Agora, vamos definir o layout do gráfico. Ajustaremos a posição e o tamanho do gráfico no slide usando o`setX`, `setY`, `setWidth`, `setHeight` métodos. Além disso, definiremos o`LayoutTargetType` para determinar o modo de layout.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Neste exemplo, definimos o gráfico para ter seu tipo de destino de layout como “Inner”, o que significa que ele será posicionado e dimensionado em relação à área interna do slide.

## Etapa 4: salve a apresentação

Por fim, vamos salvar a apresentação com as configurações de layout do gráfico.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para definir modo de layout em slides Java

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusão

 Neste tutorial, aprendemos como definir o modo de layout de um gráfico em slides Java usando Aspose.Slides for Java. Você pode personalizar a posição e o tamanho do gráfico de acordo com suas necessidades específicas, ajustando os valores na caixa`setX`, `setY`, `setWidth`, `setHeight` , e`setLayoutTargetType`métodos. Isso lhe dá controle sobre o posicionamento dos gráficos nos slides.

## Perguntas frequentes

### Como altero o modo de layout de um gráfico em Aspose.Slides for Java?

 Para alterar o modo de layout de um gráfico em Aspose.Slides for Java, você pode usar o`setLayoutTargetType` método na área de plotagem do gráfico. Você pode configurá-lo para`LayoutTargetType.Inner` ou`LayoutTargetType.Outer` dependendo do layout desejado.

### Posso personalizar a posição e o tamanho do gráfico no slide?

 Sim, você pode personalizar a posição e o tamanho do gráfico no slide usando o botão`setX`, `setY`, `setWidth` , e`setHeight` métodos na área de plotagem do gráfico. Ajuste esses valores para posicionar e dimensionar o gráfico de acordo com suas necessidades.

### Onde posso encontrar mais informações sobre Aspose.Slides para Java?

 Você pode encontrar mais informações sobre Aspose.Slides para Java no[documentação](https://reference.aspose.com/slides/java/). Inclui referências detalhadas de API e exemplos para ajudá-lo a trabalhar com slides e gráficos de maneira eficaz em Java.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
