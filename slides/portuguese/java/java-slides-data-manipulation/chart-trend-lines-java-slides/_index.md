---
title: Gráfico de linhas de tendência em slides Java
linktitle: Gráfico de linhas de tendência em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como adicionar várias linhas de tendência ao Java Slides usando Aspose.Slides for Java. Guia passo a passo com exemplos de código para visualização de dados eficaz.
type: docs
weight: 15
url: /pt/java/data-manipulation/chart-trend-lines-java-slides/
---

## Introdução às linhas de tendência do gráfico em slides Java: um guia passo a passo

Neste guia abrangente, exploraremos como criar linhas de tendência de gráfico em Java Slides usando Aspose.Slides for Java. As linhas de tendência do gráfico podem ser uma adição valiosa às suas apresentações, ajudando a visualizar e analisar as tendências dos dados de forma eficaz. Orientaremos você durante o processo com explicações claras e exemplos de código.

## Pré-requisitos

Antes de nos aprofundarmos na criação de linhas de tendência do gráfico, certifique-se de ter os seguintes pré-requisitos em vigor:

- Ambiente de Desenvolvimento Java
- Biblioteca Aspose.Slides para Java
- Um editor de código de sua escolha

## Etapa 1: primeiros passos

Vamos começar configurando o ambiente necessário e criando uma nova apresentação:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie um diretório se ainda não estiver presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Criando apresentação vazia
Presentation pres = new Presentation();
```

Inicializamos nossa apresentação e agora estamos prontos para adicionar um gráfico de colunas agrupadas:

```java
// Criando um gráfico de colunas agrupadas
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Etapa 2: Adicionar linha de tendência exponencial

Vamos começar adicionando uma linha de tendência exponencial à nossa série de gráficos:

```java
// Adicionando linha de tendência exponencial para a série de gráficos 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Etapa 3: adicionar linha de tendência linear

seguir, adicionaremos uma linha de tendência linear à nossa série de gráficos:

```java
// Adicionando linha de tendência linear para a série de gráficos 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Etapa 4: Adicionar linha de tendência logarítmica

Agora, vamos adicionar uma linha de tendência logarítmica a uma série de gráficos diferente:

```java
// Adicionando linha de tendência logarítmica para a série de gráficos 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Etapa 5: Adicionar linha de tendência de média móvel

Também podemos adicionar uma linha de tendência de média móvel:

```java
// Adicionando linha de tendência de média móvel para a série de gráficos 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Etapa 6: Adicionar linha de tendência polinomial

Adicionando uma linha de tendência polinomial:

```java
// Adicionando linha de tendência polinomial para a série de gráficos 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Passo 7: Adicionando Linha de Tendência de Energia

Finalmente, vamos adicionar uma linha de tendência de potência:

```java
// Adicionando linha de tendência de potência para a série de gráficos 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Etapa 8: salvando a apresentação

Agora que adicionamos várias linhas de tendência ao nosso gráfico, vamos salvar a apresentação:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Parabéns! Você criou com sucesso uma apresentação com diferentes tipos de linhas de tendência em Java Slides usando Aspose.Slides for Java.

## Código-fonte completo para linhas de tendência de gráfico em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie um diretório se ainda não estiver presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Criando apresentação vazia
Presentation pres = new Presentation();
// Criando um gráfico de colunas agrupadas
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Adicionando linha de tendência potencial para a série de gráficos 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Adicionando linha de tendência linear para a série de gráficos 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Adicionando linha de tendência logarítmica para a série de gráficos 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Adicionando linha de tendência MovingAverage para a série de gráficos 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Adicionando linha de tendência polinomial para a série de gráficos 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Adicionando linha de tendência Power para a série de gráficos 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Salvando apresentação
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, aprendemos como adicionar diferentes tipos de linhas de tendência a gráficos em Java Slides usando a biblioteca Aspose.Slides for Java. Esteja você trabalhando na análise de dados ou criando apresentações informativas, a capacidade de visualizar tendências pode ser uma ferramenta poderosa.

## Perguntas frequentes

### Como altero a cor de uma linha de tendência em Aspose.Slides for Java?

 Para alterar a cor de uma linha de tendência, você pode usar o`getSolidFillColor().setColor(Color)` método, conforme mostrado no exemplo para adicionar uma linha de tendência linear.

### Posso adicionar múltiplas linhas de tendência a uma única série de gráficos?

Sim, você pode adicionar várias linhas de tendência a uma única série de gráficos. Basta ligar para o`getTrendLines().add()` método para cada linha de tendência que você deseja adicionar.

### Como faço para remover uma linha de tendência de um gráfico em Aspose.Slides for Java?

 Para remover uma linha de tendência de um gráfico, você pode usar o`removeAt(int index)` método, especificando o índice da linha de tendência que você deseja remover.

### É possível personalizar a exibição da equação da linha de tendência?

 Sim, você pode personalizar a exibição da equação da linha de tendência usando o`setDisplayEquation(boolean)` método, conforme demonstrado no exemplo.

### Como posso acessar mais recursos e exemplos para Aspose.Slides for Java?

 Você pode acessar recursos adicionais, documentação e exemplos para Aspose.Slides for Java na página[Aspor site](https://reference.aspose.com/slides/java/).