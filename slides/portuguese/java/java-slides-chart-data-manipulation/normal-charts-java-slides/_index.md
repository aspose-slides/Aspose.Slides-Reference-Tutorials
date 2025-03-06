---
title: Gráficos normais em slides Java
linktitle: Gráficos normais em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Crie gráficos normais em slides Java com Aspose.Slides para Java. Guia passo a passo e código-fonte para criar, personalizar e salvar gráficos em apresentações do PowerPoint.
weight: 21
url: /pt/java/chart-data-manipulation/normal-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gráficos normais em slides Java


## Introdução aos gráficos normais em slides Java

Neste tutorial, percorreremos o processo de criação de gráficos normais em Java Slides usando a API Aspose.Slides for Java. Usaremos instruções passo a passo junto com o código-fonte para demonstrar como criar um gráfico de colunas agrupadas em uma apresentação do PowerPoint.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Aspose.Slides para API Java instalada.
2. Um ambiente de desenvolvimento Java configurado.
3. Conhecimento básico de programação Java.

## Etapa 1: Configurando o Projeto

Certifique-se de ter um diretório para o seu projeto. Vamos chamá-lo de “Seu diretório de documentos”, conforme mencionado no código. Você pode substituir isso pelo caminho real para o diretório do seu projeto.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie um diretório se ainda não estiver presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Etapa 2: Criando uma apresentação

Agora vamos criar uma apresentação em PowerPoint e acessar seu primeiro slide.

```java
// Instancie a classe Presentation que representa o arquivo PPTX
Presentation pres = new Presentation();
// Acesse o primeiro slide
ISlide sld = pres.getSlides().get_Item(0);
```

## Etapa 3: adicionar um gráfico

Adicionaremos um gráfico de colunas agrupadas ao slide e definiremos seu título.

```java
// Adicionar gráfico com dados padrão
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Configurando o título do gráfico
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Etapa 4: definir dados do gráfico

A seguir, definiremos os dados do gráfico definindo séries e categorias.

```java
// Defina a primeira série para Mostrar Valores
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;

// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Excluir séries e categorias geradas padrão
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Adicionando nova série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Adicionando novas categorias
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Etapa 5: preencher dados de séries

Agora, vamos preencher os pontos de dados da série para o gráfico.

```java
// Veja a primeira série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Definir cor de preenchimento para séries
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Veja a segunda série de gráficos
series = chart.getChartData().getSeries().get_Item(1);

// Preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Definir cor de preenchimento para séries
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Etapa 6: Personalização de rótulos

Vamos personalizar os rótulos de dados da série de gráficos.

```java
// O primeiro rótulo mostrará o nome da categoria
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Mostrar valor para o terceiro rótulo com nome da série e separador
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Etapa 7: salvando a apresentação

Por fim, salve a apresentação com o gráfico no diretório do seu projeto.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

É isso! Você criou com sucesso um gráfico de colunas agrupadas em uma apresentação do PowerPoint usando Aspose.Slides para Java. Você pode personalizar ainda mais este gráfico de acordo com suas necessidades.

## Código-fonte completo para gráficos normais em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie um diretório se ainda não estiver presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instancie a classe Presentation que representa o arquivo PPTX
Presentation pres = new Presentation();
// Acesse o primeiro slide
ISlide sld = pres.getSlides().get_Item(0);
// Adicionar gráfico com dados padrão
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Configurando o título do gráfico
// Chart.getChartTitle().getTextFrameForOverriding().setText("Título de exemplo");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Defina a primeira série para Mostrar Valores
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Excluir séries e categorias geradas padrão
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Adicionando nova série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Adicionando novas categorias
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Veja a primeira série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Definir cor de preenchimento para séries
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Veja a segunda série de gráficos
series = chart.getChartData().getSeries().get_Item(1);
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Definir cor de preenchimento para séries
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// O primeiro rótulo mostrará o nome da categoria
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Mostrar valor para o terceiro rótulo
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Salvar apresentação com gráfico
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Conclusão

Neste tutorial, aprendemos como criar gráficos normais em Java Slides usando a API Aspose.Slides for Java. Seguimos um guia passo a passo com código-fonte para criar um gráfico de colunas agrupadas em uma apresentação do PowerPoint.

## Perguntas frequentes

### Como posso alterar o tipo de gráfico?

 Para alterar o tipo de gráfico, modifique o`ChartType`parâmetro ao adicionar o gráfico usando`sld.getShapes().addChart()`. Você pode escolher entre vários tipos de gráficos disponíveis em Aspose.Slides.

### Posso alterar as cores da série do gráfico?

 Sim, você pode alterar as cores da série do gráfico definindo a cor de preenchimento de cada série usando`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Como adiciono mais categorias ou séries ao gráfico?

 Você pode adicionar mais categorias ou séries ao gráfico adicionando novos pontos de dados e rótulos usando o`chart.getChartData().getCategories().add()` e`chart.getChartData().getSeries().add()` métodos.

### Como posso personalizar ainda mais o título do gráfico?

 Você pode personalizar ainda mais o título do gráfico modificando as propriedades de`chart.getChartTitle()` como alinhamento do texto, tamanho da fonte e cor.

### Como faço para salvar o gráfico em um formato de arquivo diferente?

 Para salvar o gráfico em um formato de arquivo diferente, altere o`SaveFormat` parâmetro no`pres.save()` método para o formato desejado (por exemplo, PDF, PNG, JPEG).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
