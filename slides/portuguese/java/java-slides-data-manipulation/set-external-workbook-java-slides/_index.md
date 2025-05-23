---
"description": "Aprenda a definir pastas de trabalho externas no Java Slides usando o Aspose.Slides para Java. Crie apresentações dinâmicas com integração de dados do Excel."
"linktitle": "Definir pasta de trabalho externa em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Definir pasta de trabalho externa em slides Java"
"url": "/pt/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Definir pasta de trabalho externa em slides Java


## Introdução ao Set External Workbook em Slides Java

Neste tutorial, exploraremos como definir uma pasta de trabalho externa no Java Slides usando o Aspose.Slides. Você aprenderá a criar uma apresentação do PowerPoint com um gráfico que faz referência a dados de uma pasta de trabalho externa do Excel. Ao final deste guia, você terá uma compreensão clara de como integrar dados externos às suas apresentações do Java Slides.

## Pré-requisitos

Antes de começarmos a implementação, certifique-se de ter os seguintes pré-requisitos:

- Java Development Kit (JDK) instalado no seu sistema.
- Biblioteca Aspose.Slides para Java adicionada ao seu projeto.
- Uma pasta de trabalho do Excel com os dados que você deseja referenciar na sua apresentação.

## Etapa 1: Crie uma nova apresentação

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Começamos criando uma nova apresentação do PowerPoint usando o Aspose.Slides.

## Etapa 2: Adicionar um gráfico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Em seguida, inserimos um gráfico de pizza na apresentação. Você pode personalizar o tipo e a posição do gráfico conforme necessário.

## Etapa 3: Acessar a pasta de trabalho externa

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Para acessar a pasta de trabalho externa, usamos o `setExternalWorkbook` método e forneça o caminho para a pasta de trabalho do Excel que contém os dados.

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

Vinculamos o gráfico aos dados da pasta de trabalho externa especificando as referências de célula para séries e categorias.

## Etapa 5: Salve a apresentação

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Por fim, salvamos a apresentação com a referência da pasta de trabalho externa como um arquivo do PowerPoint.

## Código-fonte completo para a pasta de trabalho externa definida em slides Java

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

Neste tutorial, aprendemos como definir uma pasta de trabalho externa no Java Slides usando o Aspose.Slides. Agora você pode criar apresentações que referenciam dinamicamente dados de pastas de trabalho do Excel, aumentando a flexibilidade e a interatividade dos seus slides.

## Perguntas frequentes

### Como instalo o Aspose.Slides para Java?

O Aspose.Slides para Java pode ser instalado adicionando a biblioteca ao seu projeto Java. Você pode baixar a biblioteca do site do Aspose e seguir as instruções de instalação fornecidas na documentação.

### Posso usar diferentes tipos de gráficos com pastas de trabalho externas?

Sim, você pode usar vários tipos de gráficos suportados pelo Aspose.Slides e vinculá-los a dados de pastas de trabalho externas. O processo pode variar um pouco dependendo do tipo de gráfico escolhido.

### E se a estrutura de dados da minha pasta de trabalho externa mudar?

Se a estrutura dos dados da sua pasta de trabalho externa mudar, talvez seja necessário atualizar as referências de célula no seu código Java para garantir que os dados do gráfico permaneçam precisos.

### O Aspose.Slides é compatível com as versões mais recentes do Java?

O Aspose.Slides para Java é atualizado regularmente para garantir a compatibilidade com as versões mais recentes do Java. Certifique-se de verificar se há atualizações e usar a versão mais recente da biblioteca para obter desempenho e compatibilidade ideais.

### Posso adicionar vários gráficos referenciando a mesma pasta de trabalho externa?

Sim, você pode adicionar vários gráficos à sua apresentação, todos referenciando a mesma pasta de trabalho externa. Basta repetir os passos descritos neste tutorial para cada gráfico que desejar criar.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}