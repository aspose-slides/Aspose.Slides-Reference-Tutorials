---
title: Gráfico disperso em slides Java
linktitle: Gráfico disperso em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar gráficos de dispersão em Java usando Aspose.Slides. Guia passo a passo com código fonte Java para visualização de dados em apresentações.
type: docs
weight: 11
url: /pt/java/chart-creation/scattered-chart-java-slides/
---

## Introdução ao gráfico de dispersão em Aspose.Slides para Java

Neste tutorial, iremos guiá-lo através do processo de criação de um gráfico de dispersão usando Aspose.Slides para Java. Os gráficos de dispersão são úteis para visualizar pontos de dados em um plano bidimensional. Forneceremos instruções passo a passo e incluiremos o código-fonte Java para sua conveniência.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

1. [Aspose.Slides para Java](https://products.aspose.com/slides/java) instalado.
2. Um ambiente de desenvolvimento Java configurado.

## Etapa 1: inicializar a apresentação

Primeiro, importe as bibliotecas necessárias e crie uma nova apresentação.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Crie um diretório se ainda não estiver presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Crie uma nova apresentação
Presentation pres = new Presentation();
```

## Etapa 2: adicione um slide e crie o gráfico de dispersão

 Em seguida, adicione um slide e crie o gráfico de dispersão nele. Usaremos o`ScatterWithSmoothLines` tipo de gráfico neste exemplo.

```java
// Obtenha o primeiro slide
ISlide slide = pres.getSlides().get_Item(0);

// Criando o gráfico de dispersão
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Etapa 3: preparar dados do gráfico

Agora, vamos preparar os dados para nosso gráfico de dispersão. Adicionaremos duas séries, cada uma com vários pontos de dados.

```java
// Obtendo o índice da planilha de dados do gráfico padrão
int defaultWorksheetIndex = 0;

// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Excluir série de demonstração
chart.getChartData().getSeries().clear();

// Adicione a primeira série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Veja a primeira série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Adicione pontos de dados à primeira série
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Edite o tipo de série
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Alterar tamanho do marcador
series.getMarker().setSymbol(MarkerStyleType.Star); // Alterar símbolo do marcador

// Veja a segunda série de gráficos
series = chart.getChartData().getSeries().get_Item(1);

// Adicione pontos de dados à segunda série
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Alterar o estilo do marcador para a segunda série
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Etapa 4: salve a apresentação

Por fim, salve a apresentação com o gráfico de dispersão em um arquivo PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

É isso! Você criou com sucesso um gráfico de dispersão usando Aspose.Slides para Java. Agora você pode personalizar ainda mais este exemplo para atender aos seus dados específicos e requisitos de design.

## Código-fonte completo para gráfico disperso em slides Java
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie um diretório se ainda não estiver presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Criando o gráfico padrão
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Obtendo o índice da planilha de dados do gráfico padrão
int defaultWorksheetIndex = 0;
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Excluir série de demonstração
chart.getChartData().getSeries().clear();
// Adicionar nova série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Veja a primeira série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Adicione um novo ponto (1:3) aqui.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Adicionar novo ponto (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Edite o tipo de série
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Alterando o marcador da série do gráfico
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Veja a segunda série de gráficos
series = chart.getChartData().getSeries().get_Item(1);
// Adicione um novo ponto (5:2) ali.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Adicionar novo ponto (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Adicionar novo ponto (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Adicionar novo ponto (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Alterando o marcador da série do gráfico
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, orientamos você no processo de criação de um gráfico de dispersão usando Aspose.Slides para Java. Os gráficos de dispersão são ferramentas poderosas para visualizar pontos de dados em um espaço bidimensional, facilitando a análise e a compreensão de relacionamentos de dados complexos.

## Perguntas frequentes

### Como posso alterar o tipo de gráfico?

 Para alterar o tipo de gráfico, use o`setType`método na série de gráficos e forneça o tipo de gráfico desejado. Por exemplo,`series.setType(ChartType.Line)` mudaria a série para um gráfico de linhas.

### Como posso personalizar o tamanho e o estilo do marcador?

 Você pode alterar o tamanho e o estilo do marcador usando o`getMarker` método na série e, em seguida, defina as propriedades de tamanho e símbolo. Por exemplo:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Sinta-se à vontade para explorar mais opções de personalização na documentação do Aspose.Slides para Java.

 Lembre-se de substituir`"Your Document Directory"` com o caminho real onde você deseja salvar a apresentação.