---
"description": "Aprenda a adicionar barras de erro personalizadas a gráficos do PowerPoint em Slides Java usando o Aspose.Slides. Guia passo a passo com código-fonte para visualização precisa de dados."
"linktitle": "Adicionar erro personalizado em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Adicionar erro personalizado em slides Java"
"url": "/pt/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar erro personalizado em slides Java


## Introdução à adição de barras de erro personalizadas em slides Java usando Aspose.Slides

Neste tutorial, você aprenderá a adicionar barras de erro personalizadas a um gráfico em uma apresentação do PowerPoint usando o Aspose.Slides para Java. Barras de erro são úteis para exibir variabilidade ou incerteza em pontos de dados em um gráfico.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Biblioteca Aspose.Slides para Java instalada e configurada em seu projeto.
- Um ambiente de desenvolvimento Java configurado.

## Etapa 1: Crie uma apresentação vazia

Primeiro, crie uma apresentação vazia do PowerPoint.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Criando uma apresentação vazia
Presentation presentation = new Presentation();
```

## Etapa 2: adicione um gráfico de bolhas

Em seguida, adicionaremos um gráfico de bolhas à apresentação.

```java
// Criando um gráfico de bolhas
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Etapa 3: adicionar barras de erro personalizadas

Agora, vamos adicionar barras de erro personalizadas à série do gráfico.

```java
// Adicionar barras de erro personalizadas e definir seu formato
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Etapa 4: Definir dados de barras de erro

Nesta etapa, acessaremos os pontos de dados da série do gráfico e definiremos os valores das barras de erro personalizadas para cada ponto.

```java
// Acessando pontos de dados de séries de gráficos e definindo valores de barras de erro para pontos individuais
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Definindo barras de erro para pontos de séries de gráficos
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Etapa 5: Salve a apresentação

Por fim, salve a apresentação com as barras de erro personalizadas.

```java
// Salvando a apresentação
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Pronto! Você adicionou com sucesso barras de erro personalizadas a um gráfico em uma apresentação do PowerPoint usando o Aspose.Slides para Java.

## Código-fonte completo para adicionar erro personalizado em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Criando uma apresentação vazia
Presentation presentation = new Presentation();
try
{
	// Criando um gráfico de bolhas
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Adicionar barras de erro personalizadas e definir seu formato
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Acessando pontos de dados de séries de gráficos e definindo valores de barras de erro para pontos individuais
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Definindo barras de erro para pontos de séries de gráficos
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Salvando a apresentação
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusão

Neste tutorial abrangente, você aprendeu a aprimorar suas apresentações do PowerPoint adicionando barras de erro personalizadas aos gráficos usando o Aspose.Slides para Java. As barras de erro fornecem insights valiosos sobre a variabilidade e a incerteza dos dados, tornando seus gráficos mais informativos e visualmente atraentes.

## Perguntas frequentes

### Como posso personalizar a aparência das barras de erro?

Você pode personalizar a aparência das barras de erro modificando as propriedades das mesmas. `IErrorBarsFormat` objeto, como estilo de linha, cor de linha e largura da barra de erro.

### Posso adicionar barras de erro a outros tipos de gráfico?

Sim, você pode adicionar barras de erro a vários tipos de gráficos suportados pelo Aspose.Slides para Java, incluindo gráficos de barras, gráficos de linhas e gráficos de dispersão.

### Como defino valores diferentes de barra de erro para cada ponto de dados?

Você pode percorrer os pontos de dados e definir valores de barra de erro personalizados para cada ponto, conforme mostrado no código acima.

### É possível ocultar barras de erro para pontos de dados específicos?

Sim, você pode controlar a visibilidade das barras de erro para pontos de dados individuais definindo o `setVisible` propriedade do `IErrorBarsFormat` objeto.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}