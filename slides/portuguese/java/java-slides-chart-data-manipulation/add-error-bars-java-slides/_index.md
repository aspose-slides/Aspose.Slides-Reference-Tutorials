---
"description": "Aprenda a adicionar barras de erro a gráficos do PowerPoint em Java usando o Aspose.Slides. Guia passo a passo com código-fonte para personalizar barras de erro."
"linktitle": "Adicionar barras de erro em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Adicionar barras de erro em slides Java"
"url": "/pt/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar barras de erro em slides Java


## Introdução à adição de barras de erro em slides Java usando Aspose.Slides

Neste tutorial, demonstraremos como adicionar barras de erro a um gráfico em um slide do PowerPoint usando o Aspose.Slides para Java. As barras de erro fornecem informações valiosas sobre a variabilidade ou incerteza dos pontos de dados em um gráfico. Criaremos um gráfico de bolhas e adicionaremos barras de erro a ele. Vamos começar!

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada em seu projeto Java. Você pode baixar a biblioteca em [Site Aspose](https://downloads.aspose.com/slides/java).

## Etapa 1: Crie uma apresentação vazia

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Criando uma apresentação vazia
Presentation presentation = new Presentation();
```

Nesta etapa, criamos uma apresentação vazia onde adicionaremos nosso gráfico com barras de erro.

## Etapa 2: Crie um gráfico de bolhas

```java
// Criando um gráfico de bolhas
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Aqui, criamos um gráfico de bolhas e especificamos sua posição e dimensões no slide.

## Etapa 3: Adicionar barras de erro e definir o formato

```java
// Adicionando barras de erro e definindo seu formato
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

Nesta etapa, adicionamos barras de erro ao gráfico e definimos seu formato. Você pode personalizar as barras de erro alterando valores, tipos e outras propriedades.

- `errBarX` representa barras de erro ao longo do eixo X.
- `errBarY` representa barras de erro ao longo do eixo Y.
- Tornamos visíveis as barras de erro X e Y.
- `setValueType` especifica o tipo de valor para barras de erro (por exemplo, Fixo ou Porcentagem).
- `setValue` define o valor para barras de erro.
- `setType` define o tipo de barras de erro (por exemplo, mais ou menos).
- Definimos a largura das linhas da barra de erro usando `getFormat().getLine().setWidth(2)`.
- `setEndCap` especifica se as tampas finais devem ser incluídas nas barras de erro.

## Etapa 4: Salve a apresentação

```java
// Salvando a apresentação
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Por fim, salvamos a apresentação com as barras de erro adicionadas em um local especificado.

Pronto! Você adicionou barras de erro com sucesso a um gráfico em um slide do PowerPoint usando o Aspose.Slides para Java.

## Código-fonte completo para adicionar barras de erro em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Criando uma apresentação vazia
Presentation presentation = new Presentation();
try
{
	// Criando um gráfico de bolhas
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Adicionando barras de erro e definindo seu formato
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Salvando a apresentação
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusão

Neste tutorial, exploramos como aprimorar suas apresentações do PowerPoint adicionando barras de erro aos gráficos usando o Aspose.Slides para Java. As barras de erro fornecem insights valiosos sobre a variabilidade e as incertezas dos dados, tornando suas apresentações mais informativas e visualmente atraentes.

## Perguntas frequentes

### Como posso personalizar ainda mais a aparência das barras de erro?

Você pode personalizar as barras de erro modificando suas propriedades, como estilo de linha, cor e largura, conforme demonstrado na Etapa 3.

### Posso adicionar barras de erro a diferentes tipos de gráficos?

Sim, você pode adicionar barras de erro a vários tipos de gráficos suportados pelo Aspose.Slides para Java. Basta criar o tipo de gráfico desejado e seguir os mesmos passos de personalização da barra de erro.

### Como posso ajustar a posição e o tamanho do gráfico no slide?

Você pode controlar a posição e as dimensões do gráfico ajustando os parâmetros no `addChart` método, conforme mostrado na Etapa 2.

### Onde posso encontrar mais informações sobre o Aspose.Slides para Java?

Você pode consultar o [Documentação do Aspose.Slides para Java](https://reference.aspose.com/slides/java/) para obter informações detalhadas sobre como usar a biblioteca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}