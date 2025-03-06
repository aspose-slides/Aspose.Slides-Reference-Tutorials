---
title: Gerenciar gráficos de propriedades em slides Java
linktitle: Gerenciar gráficos de propriedades em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda a criar gráficos impressionantes e gerenciar propriedades em slides Java com Aspose.Slides. Guia passo a passo com código-fonte para apresentações poderosas.
weight: 13
url: /pt/java/data-manipulation/manage-properties-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introdução ao gerenciamento de propriedades e gráficos em slides Java usando Aspose.Slides

Neste tutorial, exploraremos como gerenciar propriedades e criar gráficos em slides Java usando Aspose.Slides. Aspose.Slides é uma API Java poderosa para trabalhar com apresentações em PowerPoint. Percorreremos o processo passo a passo, incluindo exemplos de código-fonte.

## Pré-requisitos

Antes de começarmos, certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada em seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Adicionando um gráfico a um slide

Para adicionar um gráfico a um slide, siga estas etapas:

1. Importe as classes necessárias e crie uma instância da classe Presentation.

```java
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
```

2. Acesse o slide onde deseja adicionar o gráfico. Neste exemplo, acessamos o primeiro slide.

```java
// Acesse o primeiro slide
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Adicione um gráfico com dados padrão. Neste caso, estamos adicionando um gráfico StackedColumn3D.

```java
// Adicionar gráfico com dados padrão
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Configurando dados do gráfico

Para definir os dados do gráfico, precisamos criar uma pasta de trabalho de dados do gráfico e adicionar séries e categorias. Siga esses passos:

4. Defina o índice da planilha de dados do gráfico.

```java
// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;
```

5. Obtenha a pasta de trabalho de dados do gráfico.

```java
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Adicione séries ao gráfico. Neste exemplo, adicionamos duas séries denominadas “Série 1” e “Série 2”.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Adicione categorias ao gráfico. Aqui, adicionamos três categorias.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Configurando propriedades de rotação 3D

Agora, vamos definir as propriedades de rotação 3D do gráfico:

8. Defina os eixos de ângulo reto.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Defina os ângulos de rotação para os eixos X e Y. Neste exemplo, giramos X 40 graus e Y 270 graus.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Defina a porcentagem de profundidade para 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Preenchendo dados de série

11. Pegue a segunda série de gráficos e preencha-a com pontos de dados.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Preencher dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Ajustando a sobreposição

12. Defina o valor de sobreposição para séries. Por exemplo, você pode definir como 100 para não haver sobreposição.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Salvando a apresentação

Por fim, salve a apresentação em disco.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

É isso! Você criou com sucesso um gráfico de colunas empilhadas 3D com propriedades personalizadas usando Aspose.Slides em Java.

## Código-fonte completo para gerenciar gráficos de propriedades em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
// Acesse o primeiro slide
ISlide slide = presentation.getSlides().get_Item(0);
// Adicionar gráfico com dados padrão
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Adicionar série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Adicionar categorias
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Definir propriedades de Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Veja a segunda série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Definir valor de sobreposição
series.getParentSeriesGroup().setOverlap((byte) 100);
// Gravar apresentação em disco
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, mergulhamos no mundo do gerenciamento de propriedades e da criação de gráficos em slides Java usando Aspose.Slides. Aspose.Slides é uma API Java robusta que permite aos desenvolvedores trabalhar com apresentações do PowerPoint de forma eficiente. Abordamos as etapas essenciais e fornecemos exemplos de código-fonte para orientá-lo durante o processo.

## Perguntas frequentes

### Como posso alterar o tipo de gráfico?

 Você pode alterar o tipo de gráfico modificando o`ChartType` parâmetro ao adicionar o gráfico. Consulte a documentação do Aspose.Slides para os tipos de gráficos disponíveis.

### Posso personalizar as cores do gráfico?

Sim, você pode personalizar as cores do gráfico definindo as propriedades de preenchimento de categorias ou pontos de dados de série.

### Como adiciono mais pontos de dados a uma série?

 Você pode adicionar mais pontos de dados a uma série usando o`series.getDataPoints().addDataPointForBarSeries()` método e especificando a célula que contém o valor dos dados.

### Como posso definir um ângulo de rotação diferente?

 Para definir um ângulo de rotação diferente para os eixos X e Y, use`chart.getRotation3D().setRotationX()` e`chart.getRotation3D().setRotationY()` com os valores de ângulo desejados.

### Que outras propriedades 3D posso personalizar?

Você pode explorar outras propriedades 3D do gráfico, como profundidade, perspectiva e iluminação, consultando a documentação do Aspose.Slides.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
