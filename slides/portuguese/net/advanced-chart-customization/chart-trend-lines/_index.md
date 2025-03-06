---
title: Explorando linhas de tendência do gráfico em Aspose.Slides para .NET
linktitle: Linhas de tendência do gráfico
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como adicionar várias linhas de tendência aos gráficos usando Aspose.Slides for .NET neste guia passo a passo. Aprimore suas habilidades de visualização de dados com facilidade!
weight: 12
url: /pt/net/advanced-chart-customization/chart-trend-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Explorando linhas de tendência do gráfico em Aspose.Slides para .NET


No mundo da visualização e apresentação de dados, a incorporação de gráficos pode ser uma forma poderosa de transmitir informações de forma eficaz. Aspose.Slides for .NET fornece um conjunto rico de ferramentas para trabalhar com gráficos, incluindo a capacidade de adicionar linhas de tendência aos seus gráficos. Neste tutorial, nos aprofundaremos no processo de adição de linhas de tendência a um gráfico passo a passo usando Aspose.Slides for .NET. 

## Pré-requisitos

Antes de começarmos a trabalhar com Aspose.Slides for .NET, você precisará garantir que possui os seguintes pré-requisitos:

1. Aspose.Slides for .NET: Para acessar a biblioteca e utilizá-la, você deve ter o Aspose.Slides for .NET instalado. Você pode obter a biblioteca no[página de download](https://releases.aspose.com/slides/net/).

2. Ambiente de desenvolvimento: você deve ter um ambiente de desenvolvimento configurado, de preferência usando um ambiente de desenvolvimento integrado .NET como o Visual Studio.

3. Conhecimento básico de C#: Uma compreensão fundamental da programação C# é benéfica, pois usaremos C# para trabalhar com Aspose.Slides for .NET.

Agora que cobrimos os pré-requisitos, vamos analisar passo a passo o processo de adição de linhas de tendência a um gráfico.

## Importando Namespaces

Primeiro, certifique-se de importar os namespaces necessários para o seu projeto C#. Esses namespaces são essenciais para trabalhar com Aspose.Slides for .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Etapa 1: crie uma apresentação

Nesta etapa, criamos uma apresentação vazia para trabalhar.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";

// Crie um diretório se ainda não estiver presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Criando apresentação vazia
Presentation pres = new Presentation();
```

## Etapa 2: adicionar um gráfico ao slide

A seguir, adicionamos um gráfico de colunas agrupadas a um slide.

```csharp
// Criando um gráfico de colunas agrupadas
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Etapa 3: adicionar linhas de tendência ao gráfico

Agora, adicionamos vários tipos de linhas de tendência à série de gráficos.

### Adicionando uma linha de tendência exponencial

```csharp
// Adicionando linha de tendência exponencial para a série de gráficos 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Adicionando uma linha de tendência linear

```csharp
// Adicionando linha de tendência linear para a série de gráficos 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Adicionando uma linha de tendência logarítmica

```csharp
// Adicionando linha de tendência logarítmica para a série de gráficos 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Adicionando uma linha de tendência de média móvel

```csharp
// Adicionando linha de tendência de média móvel para a série de gráficos 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Adicionando uma linha de tendência polinomial

```csharp
// Adicionando linha de tendência polinomial para a série de gráficos 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Adicionando uma linha de tendência de potência

```csharp
// Adicionando linha de tendência de potência para a série de gráficos 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Etapa 4: salve a apresentação

Após adicionar linhas de tendência ao gráfico, salve a apresentação.

```csharp
// Salvando apresentação
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

É isso! Você adicionou com sucesso várias linhas de tendência ao seu gráfico usando Aspose.Slides for .NET.

## Conclusão

Aspose.Slides for .NET é uma biblioteca versátil que permite criar e manipular gráficos com facilidade. Seguindo este guia passo a passo, você pode adicionar diferentes tipos de linhas de tendência aos seus gráficos, melhorando a representação visual dos seus dados.

### Perguntas frequentes

### Onde posso encontrar a documentação do Aspose.Slides for .NET?
 Você pode acessar a documentação[aqui](https://reference.aspose.com/slides/net/).

### Como posso baixar o Aspose.Slides para .NET?
 Você pode baixar Aspose.Slides for .NET na página de download[aqui](https://releases.aspose.com/slides/net/).

### Existe um teste gratuito disponível para Aspose.Slides for .NET?
 Sim, você pode experimentar o Aspose.Slides for .NET gratuitamente visitando[esse link](https://releases.aspose.com/).

### Onde posso comprar o Aspose.Slides para .NET?
 Para adquirir o Aspose.Slides for .NET, visite a página de compra[aqui](https://purchase.aspose.com/buy).

### Preciso de uma licença temporária para Aspose.Slides for .NET?
 Você pode obter uma licença temporária para Aspose.Slides for .NET em[esse link](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
