---
title: Gráfico existente em slides Java
linktitle: Gráfico existente em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprimore suas apresentações em PowerPoint com Aspose.Slides para Java. Aprenda a modificar gráficos existentes de forma programática. Guia passo a passo com código-fonte para personalização de gráficos.
weight: 12
url: /pt/java/chart-elements/existing-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introdução ao gráfico existente em slides Java usando Aspose.Slides para Java

Neste tutorial, demonstraremos como modificar um gráfico existente em uma apresentação do PowerPoint usando Aspose.Slides para Java. Seguiremos as etapas para alterar os dados do gráfico, nomes de categorias, nomes de séries e adicionar uma nova série ao gráfico. Certifique-se de ter Aspose.Slides for Java configurado em seu projeto.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Biblioteca Aspose.Slides para Java incluída em seu projeto.
2. Uma apresentação existente do PowerPoint com um gráfico que você deseja modificar.
3. Ambiente de desenvolvimento Java configurado.

## Etapa 1: carregar a apresentação

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Instancie a classe Presentation que representa o arquivo PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Etapa 2: acesse o slide e o gráfico

```java
// Acesse o primeiro slide
ISlide sld = pres.getSlides().get_Item(0);

// Acesse o gráfico no slide
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Etapa 3: alterar os dados do gráfico e os nomes das categorias

```java
// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;

// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Alterar nomes de categorias de gráfico
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Etapa 4: atualizar a primeira série de gráficos

```java
// Veja a primeira série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Atualizar nome da série
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Atualizar dados da série
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Etapa 5: atualizar a segunda série de gráficos

```java
// Veja a segunda série de gráficos
series = chart.getChartData().getSeries().get_Item(1);

// Atualizar nome da série
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Atualizar dados da série
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Etapa 6: adicionar uma nova série ao gráfico

```java
// Adicionando uma nova série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Veja a terceira série de gráficos
series = chart.getChartData().getSeries().get_Item(2);

// Preencher dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Etapa 7: alterar o tipo de gráfico

```java
//Altere o tipo de gráfico para Cilindro Clusterizado
chart.setType(ChartType.ClusteredCylinder);
```

## Etapa 8: salve a apresentação modificada

```java
// Salve a apresentação com o gráfico modificado
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Parabéns! Você modificou com sucesso um gráfico existente em uma apresentação do PowerPoint usando Aspose.Slides para Java. Agora você pode usar esse código para personalizar gráficos em suas apresentações do PowerPoint de forma programática.

## Código-fonte completo para gráfico existente em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Instanciar classe de apresentação que representa arquivo PPTX // Instanciar classe de apresentação que representa arquivo PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Acesse o primeiro slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Adicionar gráfico com dados padrão
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Alterando o nome da categoria do gráfico
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Veja a primeira série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Agora atualizando os dados da série
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Modificando o nome da série
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Veja a segunda série de gráficos
series = chart.getChartData().getSeries().get_Item(1);
// Agora atualizando os dados da série
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Modificando o nome da série
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Agora, adicionando uma nova série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Faça a terceira série de gráficos
series = chart.getChartData().getSeries().get_Item(2);
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Salvar apresentação com gráfico
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Conclusão

Neste tutorial abrangente, aprendemos como modificar um gráfico existente em uma apresentação do PowerPoint usando Aspose.Slides para Java. Seguindo o guia passo a passo e utilizando exemplos de código-fonte, você pode personalizar e atualizar facilmente os gráficos para atender aos seus requisitos específicos. Aqui está uma recapitulação do que cobrimos:

## Perguntas frequentes

### Como posso alterar o tipo de gráfico?

 Você pode alterar o tipo de gráfico usando o`chart.setType(ChartType.ChartTypeHere)` método. Substituir`ChartTypeHere` com o tipo de gráfico desejado, como`ChartType.ClusteredCylinder` em nosso exemplo.

### Posso adicionar mais pontos de dados a uma série?

 Sim, você pode adicionar mais pontos de dados a uma série usando o`series.getDataPoints().addDataPointForBarSeries(cell)` método. Certifique-se de fornecer os dados da célula apropriados.

### Como atualizo os nomes das categorias?

 Você pode atualizar nomes de categorias usando`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` para definir os novos nomes de categoria.

### Como modifico os nomes das séries?

 Para modificar nomes de séries, use`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` para definir os novos nomes das séries.

### Existe uma maneira de remover uma série do gráfico?

 Sim, você pode remover uma série do gráfico usando o`chart.getChartData().getSeries().removeAt(index)` método, onde`index`é o índice da série que você deseja remover.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
