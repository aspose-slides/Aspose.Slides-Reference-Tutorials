---
"description": "Aprenda a definir fórmulas de células de dados de gráficos em apresentações do PowerPoint em Java usando o Aspose.Slides para Java. Crie gráficos dinâmicos com fórmulas."
"linktitle": "Fórmulas de células de dados de gráfico em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Fórmulas de células de dados de gráfico em slides Java"
"url": "/pt/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Fórmulas de células de dados de gráfico em slides Java


## Introdução às fórmulas de células de dados de gráfico no Aspose.Slides para Java

Neste tutorial, exploraremos como trabalhar com fórmulas de células de dados de gráficos usando o Aspose.Slides para Java. Com o Aspose.Slides, você pode criar e manipular gráficos em apresentações do PowerPoint, incluindo a definição de fórmulas para células de dados.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada. Você pode baixá-la em [aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: Crie uma apresentação do PowerPoint

Primeiro, vamos criar uma nova apresentação do PowerPoint e adicionar um gráfico a ela.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Adicione um gráfico ao primeiro slide
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Obtenha a pasta de trabalho para dados do gráfico
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Continue com as operações de célula de dados
    // ...
    
    // Salvar a apresentação
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Etapa 2: definir fórmulas para células de dados

Agora, vamos definir fórmulas para células de dados específicas no gráfico. Neste exemplo, definiremos fórmulas para duas células diferentes.

### Célula 1: Usando a Notação A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

No código acima, definimos uma fórmula para a célula B2 usando a notação A1. A fórmula calcula a soma das células F2 a H5 e adiciona 1 ao resultado.

### Célula 2: Usando a notação R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Aqui, definimos uma fórmula para a célula C2 usando a notação R1C1. A fórmula calcula o valor máximo dentro do intervalo R2C6 a R5C8 e, em seguida, o divide por 3.

## Etapa 3: Calcular Fórmulas

Depois de definir as fórmulas, é essencial calculá-las usando o seguinte código:

```java
workbook.calculateFormulas();
```

Esta etapa garante que o gráfico reflita os valores atualizados com base nas fórmulas.

## Etapa 4: Salve a apresentação

Por fim, salve a apresentação modificada em um arquivo.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Código-fonte completo para fórmulas de células de dados de gráfico em slides Java

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusão

Neste tutorial, exploramos como trabalhar com fórmulas de células de dados de gráfico no Aspose.Slides para Java. Abordamos a criação de uma apresentação do PowerPoint, a adição de um gráfico, a configuração de fórmulas para células de dados, o cálculo das fórmulas e o salvamento da apresentação. Agora você pode aproveitar esses recursos para criar gráficos dinâmicos e baseados em dados em suas apresentações.

## Perguntas frequentes

### Como adiciono um gráfico a um slide específico?

Para adicionar um gráfico a um slide específico, você pode usar o `getSlides().get_Item(slideIndex)` método para acessar o slide desejado e, em seguida, usar o `addChart` método para adicionar o gráfico.

### Posso usar diferentes tipos de fórmulas em células de dados?

Sim, você pode usar vários tipos de fórmulas, incluindo operações matemáticas, funções e referências a outras células, em fórmulas de células de dados.

### Como altero o tipo de gráfico?

Você pode alterar o tipo de gráfico usando o `setChartType` método sobre o `IChart` objeto e especificando o desejado `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}