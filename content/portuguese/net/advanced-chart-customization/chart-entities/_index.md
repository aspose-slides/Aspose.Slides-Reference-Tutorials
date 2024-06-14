---
title: Criando lindos gráficos com Aspose.Slides para .NET
linktitle: Entidades e formatação do gráfico
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como criar gráficos impressionantes com Aspose.Slides for .NET. Eleve seu jogo de visualização de dados com nosso guia passo a passo.
type: docs
weight: 13
url: /pt/net/advanced-chart-customization/chart-entities/
---

No mundo atual, orientado por dados, a visualização eficaz dos dados é fundamental para transmitir informações ao seu público. Aspose.Slides for .NET é uma biblioteca poderosa que permite criar apresentações e slides impressionantes, incluindo gráficos atraentes. Neste tutorial, orientaremos você no processo de criação de belos gráficos usando Aspose.Slides for .NET. Dividiremos cada exemplo em várias etapas para ajudá-lo a compreender e implementar entidades e formatação de gráficos. Então vamos começar!

## Pré-requisitos

Antes de começarmos a criar belos gráficos com Aspose.Slides for .NET, você precisará garantir que possui os seguintes pré-requisitos:

1.  Aspose.Slides for .NET: Certifique-se de ter a biblioteca Aspose.Slides for .NET instalada. Você pode baixá-lo no[local na rede Internet](https://releases.aspose.com/slides/net/).

2. Ambiente de desenvolvimento: você deve ter um ambiente de desenvolvimento funcional com Visual Studio ou qualquer outro IDE que suporte desenvolvimento .NET.

3. Conhecimento básico de C#: familiaridade com programação C# é essencial para este tutorial.

Agora que classificamos nossos pré-requisitos, vamos criar belos gráficos com Aspose.Slides para .NET.

## Importar namespaces

Primeiro, você precisa importar os namespaces necessários para trabalhar com Aspose.Slides for .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Etapa 1: crie uma apresentação

Começamos criando uma nova apresentação para trabalhar. Esta apresentação servirá de tela para nosso gráfico.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";

// Crie um diretório se ainda não estiver presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Instanciando apresentação
Presentation pres = new Presentation();
```

## Etapa 2: acesse o primeiro slide

Vamos acessar o primeiro slide da apresentação onde colocaremos nosso gráfico.

```csharp
// Acessando o primeiro slide
ISlide slide = pres.Slides[0];
```

## Etapa 3: adicionar um gráfico de amostra

Agora, adicionaremos um gráfico de amostra ao nosso slide. Neste exemplo, criaremos um gráfico de linhas com marcadores.

```csharp
// Adicionando o gráfico de amostra
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Etapa 4: definir o título do gráfico

Daremos um título ao nosso gráfico, tornando-o mais informativo e visualmente atraente.

```csharp
// Configurando o título do gráfico
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## Etapa 5: personalizar linhas de grade do eixo vertical

Nesta etapa, personalizaremos as linhas de grade do eixo vertical para tornar nosso gráfico mais atraente visualmente.

```csharp
// Configurando o formato das linhas de grade principais para o eixo de valor
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Configurando o formato das linhas de grade secundárias para o eixo de valor
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Configurando o formato do número do eixo de valor
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Etapa 6: definir a faixa do eixo vertical

Nesta etapa, definiremos os valores máximo, mínimo e unitário para o eixo vertical.

```csharp
// Definir valores máximos e mínimos do gráfico
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Etapa 7: personalizar o texto do eixo vertical

Agora personalizaremos a aparência do texto no eixo vertical.

```csharp
// Configurando propriedades de texto do eixo de valores
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Definir título do eixo de valor
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## Etapa 8: personalizar linhas de grade do eixo horizontal

Agora, vamos personalizar as linhas de grade do eixo horizontal.

```csharp
// Configurando o formato das linhas de grade principais para o eixo de categoria
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Configurando o formato das linhas de grade secundárias para o eixo de categoria
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Configurando propriedades de texto do eixo de categoria
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Etapa 9: personalizar rótulos de eixo horizontal

Nesta etapa, ajustaremos a posição e a rotação dos rótulos dos eixos horizontais.

```csharp
// Configurando a posição do rótulo do eixo da categoria
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Configurando o ângulo de rotação do rótulo do eixo da categoria
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Etapa 10: personalizar legendas

Vamos aprimorar as legendas em nosso gráfico para melhor legibilidade.

```csharp
// Configurando propriedades de texto de legendas
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Definir mostrar legendas do gráfico sem gráfico sobreposto
chart.Legend.Overlay = true;
```

## Etapa 11: personalizar o plano de fundo do gráfico

Personalizaremos as cores de fundo do gráfico, da parede posterior e do piso.

```csharp
// Definir a cor da parede posterior do gráfico
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Configurando a cor da área de plotagem
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Etapa 12: salve a apresentação

Por fim, vamos salvar nossa apresentação com o gráfico formatado.

```csharp
// Salvar apresentação
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Criar gráficos bonitos e informativos em suas apresentações agora é mais fácil do que nunca com Aspose.Slides for .NET. Neste tutorial, cobrimos as etapas essenciais para personalizar vários aspectos de um gráfico, tornando-o visualmente atraente e informativo. Com essas técnicas, você pode criar gráficos impressionantes que transmitem seus dados de maneira eficaz ao seu público.

Comece a experimentar o Aspose.Slides for .NET e leve a visualização de seus dados para o próximo nível!

## perguntas frequentes

### 1. O que é Aspose.Slides para .NET?

Aspose.Slides for .NET é uma biblioteca poderosa que permite aos desenvolvedores .NET criar, manipular e converter apresentações do Microsoft PowerPoint. Ele oferece uma ampla gama de recursos para trabalhar com slides, formas, gráficos e muito mais.

### 2. Onde posso baixar o Aspose.Slides para .NET?

 Você pode baixar Aspose.Slides para .NET do site[aqui](https://releases.aspose.com/slides/net/).

### 3. Existe uma avaliação gratuita disponível para Aspose.Slides for .NET?

 Sim, você pode obter uma avaliação gratuita do Aspose.Slides for .NET em[aqui](https://releases.aspose.com/).

### 4. Como posso obter uma licença temporária do Aspose.Slides for .NET?

 Se precisar de uma licença temporária, você pode obtê-la em[esse link](https://purchase.aspose.com/temporary-license/).

### 5. Existe uma comunidade ou fórum de suporte para Aspose.Slides for .NET?

 Sim, você pode encontrar a comunidade Aspose.Slides e o fórum de suporte[aqui](https://forum.aspose.com/).
