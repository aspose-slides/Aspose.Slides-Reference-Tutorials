---
title: Legenda do tamanho da fonte em slides Java
linktitle: Legenda do tamanho da fonte em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprimore as apresentações do PowerPoint com Aspose.Slides para Java. Aprenda como personalizar os tamanhos das fontes das legendas e muito mais em nosso guia passo a passo.
weight: 13
url: /pt/java/chart-elements/font-size-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introdução à legenda do tamanho da fonte em slides Java

Neste tutorial, você aprenderá como personalizar o tamanho da fonte da legenda em um slide do PowerPoint usando Aspose.Slides for Java. Forneceremos instruções passo a passo e código-fonte para realizar esta tarefa.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java instalada e configurada em seu projeto Java. Você pode baixar a biblioteca em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: inicializar a apresentação

Primeiro, importe as classes necessárias e inicialize sua apresentação em PowerPoint.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Substituir`"Your Document Directory"` com o caminho real para o seu arquivo PowerPoint.

## Etapa 2: adicionar um gráfico

A seguir, adicionaremos um gráfico ao slide e definiremos o tamanho da fonte da legenda.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 Neste código, criamos um gráfico de colunas agrupadas no primeiro slide e definimos o tamanho da fonte do texto da legenda para 20 pontos. Você pode ajustar o`setFontHeight`valor para alterar o tamanho da fonte conforme necessário.

## Etapa 3: personalizar os valores do eixo

Agora, vamos personalizar os valores do eixo vertical do gráfico.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Aqui, definimos os valores mínimo e máximo para o eixo vertical. Você pode modificar os valores de acordo com seus requisitos de dados.

## Etapa 4: salve a apresentação

Finalmente, salve a apresentação modificada em um novo arquivo.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Este código salva a apresentação modificada como “output.pptx” no diretório especificado.

## Código-fonte completo para legenda do tamanho da fonte em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Você personalizou com sucesso o tamanho da fonte da legenda em um slide Java PowerPoint usando Aspose.Slides for Java. Você pode explorar ainda mais os recursos do Aspose.Slides para criar apresentações interativas e visualmente atraentes.

## Perguntas frequentes

### Como altero o tamanho da fonte do texto da legenda em um gráfico?

Para alterar o tamanho da fonte do texto da legenda em um gráfico, você pode usar o seguinte código:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 Neste código, criamos um gráfico e definimos o tamanho da fonte do texto da legenda em 20 pontos. Você pode ajustar o`setFontHeight` valor para alterar o tamanho da fonte.

### Posso personalizar outras propriedades da legenda em um gráfico?

Sim, você pode personalizar várias propriedades da legenda em um gráfico usando Aspose.Slides. Algumas das propriedades comuns que você pode personalizar incluem formatação de texto, posição, visibilidade e muito mais. Por exemplo, para alterar a posição da legenda, você pode usar:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Este código define a legenda para aparecer na parte inferior do gráfico. Explore a documentação do Aspose.Slides para obter mais opções de personalização.

### Como defino valores mínimos e máximos para o eixo vertical em um gráfico?

Para definir valores mínimos e máximos para o eixo vertical em um gráfico, você pode usar o seguinte código:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Aqui, desativamos a escala automática do eixo e especificamos os valores mínimo e máximo para o eixo vertical. Ajuste os valores conforme necessário para os dados do seu gráfico.

### Onde posso encontrar mais informações e documentação sobre Aspose.Slides?

 Você pode encontrar documentação abrangente e referências de API para Aspose.Slides for Java no site de documentação do Aspose. Visita[aqui](https://reference.aspose.com/slides/java/) para obter informações detalhadas sobre como usar a biblioteca.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
