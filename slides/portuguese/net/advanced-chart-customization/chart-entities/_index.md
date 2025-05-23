---
"description": "Aprenda a criar gráficos impressionantes com o Aspose.Slides para .NET. Eleve seu nível de visualização de dados com nosso guia passo a passo."
"linktitle": "Entidades e formatação do gráfico"
"second_title": "API de processamento de PowerPoint Aspose.Slides .NET"
"title": "Criando belos gráficos com Aspose.Slides para .NET"
"url": "/pt/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Criando belos gráficos com Aspose.Slides para .NET


No mundo atual, impulsionado por dados, a visualização eficaz de dados é fundamental para transmitir informações ao seu público. O Aspose.Slides para .NET é uma biblioteca poderosa que permite criar apresentações e slides impressionantes, incluindo gráficos atraentes. Neste tutorial, mostraremos o processo de criação de gráficos incríveis usando o Aspose.Slides para .NET. Dividiremos cada exemplo em várias etapas para ajudar você a entender e implementar as entidades e a formatação dos gráficos. Então, vamos começar!

## Pré-requisitos

Antes de começarmos a criar belos gráficos com o Aspose.Slides para .NET, você precisa garantir que tenha os seguintes pré-requisitos:

1. Aspose.Slides para .NET: Certifique-se de ter a biblioteca Aspose.Slides para .NET instalada. Você pode baixá-la do site [site](https://releases.aspose.com/slides/net/).

2. Ambiente de desenvolvimento: você deve ter um ambiente de desenvolvimento funcional com o Visual Studio ou qualquer outro IDE que suporte desenvolvimento .NET.

3. Conhecimento básico de C#: familiaridade com programação em C# é essencial para este tutorial.

Agora que nossos pré-requisitos estão resolvidos, vamos criar belos gráficos com o Aspose.Slides para .NET.

## Importar namespaces

Primeiro, você precisa importar os namespaces necessários para trabalhar com o Aspose.Slides para .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Etapa 1: Crie uma apresentação

Começamos criando uma nova apresentação para trabalhar. Essa apresentação servirá como tela para o nosso gráfico.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";

// Crie um diretório se ele ainda não estiver presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Instanciando apresentação
Presentation pres = new Presentation();
```

## Etapa 2: Acesse o primeiro slide

Vamos acessar o primeiro slide da apresentação onde colocaremos nosso gráfico.

```csharp
// Acessando o primeiro slide
ISlide slide = pres.Slides[0];
```

## Etapa 3: Adicionar um gráfico de amostra

Agora, adicionaremos um gráfico de exemplo ao nosso slide. Neste exemplo, criaremos um gráfico de linhas com marcadores.

```csharp
// Adicionando o gráfico de amostra
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Etapa 4: definir título do gráfico

Daremos um título ao nosso gráfico, tornando-o mais informativo e visualmente atraente.

```csharp
// Título do gráfico de configuração
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

## Etapa 5: personalizar as linhas de grade do eixo vertical

Nesta etapa, personalizaremos as linhas de grade do eixo vertical para tornar nosso gráfico mais atraente visualmente.

```csharp
// Definindo o formato das linhas de grade principais para o eixo de valor
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Definindo o formato das linhas de grade secundárias para o eixo de valor
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Definindo o formato do número do eixo de valor
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Etapa 6: Definir o intervalo do eixo vertical

Nesta etapa, definiremos os valores máximo, mínimo e unitários para o eixo vertical.

```csharp
// Definindo valores máximos e mínimos do gráfico
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
// Definindo propriedades de texto do eixo de valor
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Definindo o título do eixo de valor
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

## Etapa 8: personalizar as linhas de grade do eixo horizontal

Agora, vamos personalizar as linhas de grade para o eixo horizontal.

```csharp
// Definindo o formato das linhas de grade principais para o eixo de categoria
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Definindo o formato das linhas de grade secundárias para o eixo de categoria
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Definindo propriedades de texto do eixo de categoria
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Etapa 9: personalizar rótulos do eixo horizontal

Nesta etapa, ajustaremos a posição e a rotação dos rótulos do eixo horizontal.

```csharp
// Definindo a posição do rótulo do eixo da categoria
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Definindo o ângulo de rotação do rótulo do eixo da categoria
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Etapa 10: personalizar legendas

Vamos melhorar as legendas em nosso gráfico para melhor legibilidade.

```csharp
// Definindo propriedades de texto de legendas
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Definir legendas de gráficos de exibição sem sobreposição de gráficos
chart.Legend.Overlay = true;
```

## Etapa 11: personalizar o plano de fundo do gráfico

Personalizaremos as cores de fundo do gráfico, da parede posterior e do piso.

```csharp
// Definindo a cor da parede de fundo do gráfico
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Definindo a cor da área de plotagem
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Etapa 12: Salve a apresentação

Por fim, vamos salvar nossa apresentação com o gráfico formatado.

```csharp
// Salvar apresentação
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Criar gráficos bonitos e informativos em suas apresentações agora é mais fácil do que nunca com o Aspose.Slides para .NET. Neste tutorial, abordamos os passos essenciais para personalizar vários aspectos de um gráfico, tornando-o visualmente atraente e informativo. Com essas técnicas, você pode criar gráficos impressionantes que transmitem seus dados ao seu público de forma eficaz.

Comece a experimentar o Aspose.Slides para .NET e leve sua visualização de dados para o próximo nível!

## Perguntas frequentes

### 1. O que é Aspose.Slides para .NET?

Aspose.Slides para .NET é uma biblioteca poderosa que permite que desenvolvedores .NET criem, manipulem e convertam apresentações do Microsoft PowerPoint. Ela oferece uma ampla gama de recursos para trabalhar com slides, formas, gráficos e muito mais.

### 2. Onde posso baixar o Aspose.Slides para .NET?

Você pode baixar o Aspose.Slides para .NET no site [aqui](https://releases.aspose.com/slides/net/).

### 3. Existe uma avaliação gratuita disponível do Aspose.Slides para .NET?

Sim, você pode obter uma avaliação gratuita do Aspose.Slides para .NET em [aqui](https://releases.aspose.com/).

### 4. Como posso obter uma licença temporária para o Aspose.Slides para .NET?

Se você precisar de uma licença temporária, poderá obtê-la em [este link](https://purchase.aspose.com/temporary-license/).

### 5. Existe uma comunidade ou fórum de suporte para o Aspose.Slides para .NET?

Sim, você pode encontrar a comunidade e o fórum de suporte do Aspose.Slides [aqui](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}