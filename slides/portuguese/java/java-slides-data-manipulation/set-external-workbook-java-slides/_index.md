---
title: Definir pasta de trabalho externa em slides Java
linktitle: Definir pasta de trabalho externa em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como definir pastas de trabalho externas em Java Slides usando Aspose.Slides for Java. Crie apresentações dinâmicas com integração de dados do Excel.
weight: 19
url: /pt/java/data-manipulation/set-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introdução à definição de pasta de trabalho externa em slides Java

Neste tutorial, exploraremos como definir uma pasta de trabalho externa em Java Slides usando Aspose.Slides. Você aprenderá como criar uma apresentação do PowerPoint com um gráfico que faz referência a dados de uma pasta de trabalho externa do Excel. Ao final deste guia, você terá uma compreensão clara de como integrar dados externos em suas apresentações Java Slides.

## Pré-requisitos

Antes de mergulharmos na implementação, certifique-se de ter os seguintes pré-requisitos:

- Java Development Kit (JDK) instalado em seu sistema.
- Biblioteca Aspose.Slides para Java adicionada ao seu projeto.
- Uma pasta de trabalho do Excel com os dados que você deseja referenciar em sua apresentação.

## Etapa 1: crie uma nova apresentação

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Começamos criando uma nova apresentação em PowerPoint usando Aspose.Slides.

## Etapa 2: adicionar um gráfico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

A seguir, inserimos um gráfico de pizza na apresentação. Você pode personalizar o tipo e a posição do gráfico conforme necessário.

## Etapa 3: acessar a pasta de trabalho externa

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Para acessar a pasta de trabalho externa, usamos o`setExternalWorkbook` método e forneça o caminho para a pasta de trabalho do Excel que contém os dados.

## Etapa 4: vincular dados do gráfico

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Vinculamos o gráfico aos dados da pasta de trabalho externa especificando as referências de células para séries e categorias.

## Etapa 5: salve a apresentação

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Finalmente, salvamos a apresentação com a referência externa da pasta de trabalho como um arquivo PowerPoint.

## Código-fonte completo para definir pasta de trabalho externa em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, aprendemos como definir uma pasta de trabalho externa em Java Slides usando Aspose.Slides. Agora você pode criar apresentações que fazem referência dinâmica a dados de pastas de trabalho do Excel, aumentando a flexibilidade e a interatividade dos seus slides.

## Perguntas frequentes

### Como faço para instalar o Aspose.Slides para Java?

Aspose.Slides for Java pode ser instalado adicionando a biblioteca ao seu projeto Java. Você pode baixar a biblioteca do site Aspose e seguir as instruções de instalação fornecidas na documentação.

### Posso usar diferentes tipos de gráficos com pastas de trabalho externas?

Sim, você pode usar vários tipos de gráficos suportados pelo Aspose.Slides e vinculá-los a dados de pastas de trabalho externas. O processo pode variar um pouco dependendo do tipo de gráfico escolhido.

### E se a estrutura de dados da minha pasta de trabalho externa mudar?

Se a estrutura dos dados da sua pasta de trabalho externa for alterada, talvez seja necessário atualizar as referências de células no seu código Java para garantir que os dados do gráfico permaneçam precisos.

### O Aspose.Slides é compatível com as versões mais recentes do Java?

Aspose.Slides for Java é atualizado regularmente para garantir compatibilidade com as versões mais recentes do Java. Certifique-se de verificar se há atualizações e de usar a versão mais recente da biblioteca para obter desempenho e compatibilidade ideais.

### Posso adicionar vários gráficos referenciando a mesma pasta de trabalho externa?

Sim, você pode adicionar vários gráficos à sua apresentação, todos fazendo referência à mesma pasta de trabalho externa. Basta repetir as etapas descritas neste tutorial para cada gráfico que deseja criar.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
