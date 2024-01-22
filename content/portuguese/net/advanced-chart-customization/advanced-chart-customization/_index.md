---
title: Personalização avançada de gráficos em Aspose.Slides
linktitle: Personalização avançada de gráficos em Aspose.Slides
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda personalização avançada de gráficos em Aspose.Slides for .NET. Crie gráficos visualmente atraentes com orientação passo a passo.
type: docs
weight: 10
url: /pt/net/advanced-chart-customization/advanced-chart-customization/
---

A criação de gráficos visualmente atraentes e informativos é uma parte essencial da apresentação de dados em muitas aplicações. Aspose.Slides for .NET fornece ferramentas robustas para personalização de gráficos, permitindo ajustar todos os aspectos de seus gráficos. Neste tutorial, exploraremos técnicas avançadas de personalização de gráficos usando Aspose.Slides for .NET.

## Pré-requisitos

Antes de mergulhar na personalização avançada de gráficos com Aspose.Slides for .NET, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Biblioteca Aspose.Slides para .NET: Você precisa ter a biblioteca Aspose.Slides instalada e configurada corretamente em seu projeto .NET. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/net/).

2. Um ambiente de desenvolvimento .NET: você deve ter um ambiente de desenvolvimento .NET configurado, incluindo Visual Studio ou qualquer outro IDE de sua escolha.

3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# será útil, pois escreveremos código C# para funcionar com Aspose.Slides.

Agora, vamos dividir a personalização avançada do gráfico em várias etapas para guiá-lo durante o processo.

## Etapa 1: crie uma apresentação

Primeiro, crie uma nova apresentação usando Aspose.Slides.

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

Nesta etapa, iniciamos uma nova apresentação que conterá nosso gráfico.

## Etapa 2: acesse o primeiro slide

A seguir, acesse o primeiro slide da apresentação onde deseja adicionar o gráfico.

```csharp
// Acessando o primeiro slide
ISlide slide = pres.Slides[0];
```

Este trecho de código permite trabalhar com o primeiro slide da apresentação.

## Etapa 3: adicionar um gráfico de amostra

Agora, vamos adicionar um gráfico de amostra ao slide. Neste exemplo, criaremos um gráfico de linhas com marcadores.

```csharp
// Adicionando o gráfico de amostra
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Aqui especificamos o tipo de gráfico (LineWithMarkers) e sua posição e dimensões no slide.

## Etapa 4: definir o título do gráfico

Vamos definir um título para o gráfico para fornecer contexto.

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

Este código define um título para o gráfico, especificando seu texto, aparência e estilo de fonte.

## Etapa 5: personalizar linhas de grade principais

Agora, vamos personalizar as principais linhas de grade do eixo de valores.

```csharp
// Configurando o formato das linhas de grade principais para o eixo de valor
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Esta etapa configura a aparência das principais linhas de grade no eixo de valores.

## Etapa 6: personalizar linhas de grade secundárias

Da mesma forma, podemos personalizar as linhas de grade secundárias para o eixo de valores.

```csharp
// Configurando o formato das linhas de grade secundárias para o eixo de valor
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Este código ajusta a aparência das linhas de grade secundárias no eixo de valores.

## Etapa 7: Definir o formato do número do eixo de valores

Personalize o formato numérico do eixo de valores.

```csharp
// Configurando o formato do número do eixo de valor
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Esta etapa permite formatar os números exibidos no eixo de valores.

## Etapa 8: definir valores máximos e mínimos do gráfico

Defina os valores máximo e mínimo do gráfico.

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

Aqui, você especifica o intervalo de valores que o eixo do gráfico deve exibir.

## Etapa 9: personalizar as propriedades do texto do eixo de valores

Você também pode personalizar as propriedades de texto do eixo de valores.

```csharp
// Configurando propriedades de texto do eixo de valores
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Este código permite ajustar o estilo da fonte e a aparência dos rótulos dos eixos de valores.

## Etapa 10: Adicionar título do eixo de valor

Se o seu gráfico exigir um título para o eixo de valores, você poderá adicioná-lo nesta etapa.

```csharp
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

Nesta etapa, você pode definir um título para o eixo de valores.

## Etapa 11: personalizar linhas de grade principais para o eixo de categoria

Agora, vamos nos concentrar nas principais linhas de grade do eixo de categoria.

```csharp
// Configurando o formato das linhas de grade principais para o eixo de categoria
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Este código configura a aparência das principais linhas de grade no eixo da categoria.

## Etapa 12: personalizar linhas de grade secundárias para o eixo de categoria

Semelhante ao eixo de valor, você pode personalizar as linhas de grade secundárias do eixo de categoria.

```csharp
//Configurando o formato das linhas de grade secundárias para o eixo de categoria
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Aqui, você ajusta a aparência das linhas de grade secundárias no eixo da categoria.

## Etapa 13: personalizar as propriedades do texto do eixo da categoria

Personalize as propriedades de texto dos rótulos do eixo de categoria.

```csharp
// Configurando propriedades de texto do eixo de categoria
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Este código permite ajustar o estilo da fonte e a aparência dos rótulos dos eixos de categoria.

## Etapa 14: adicionar título ao eixo da categoria

Você também pode adicionar um título ao eixo de categoria, se necessário.

```csharp
// Configurando o título da categoria
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

Nesta etapa, você pode definir um título para o eixo de categoria.

## Etapa 15: personalizações adicionais

Você pode explorar outras personalizações, como legendas, parede posterior do gráfico, piso e cores da área de plotagem. Essas personalizações permitem aprimorar o apelo visual do seu gráfico.

```csharp
// Personalizações adicionais (opcional)

// Configurando propriedades de texto de legendas
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Definir mostrar legendas do gráfico sem gráfico sobreposto
chart.Legend.Overlay = true;

// Plotando a primeira série no eixo de valor secundário (se necessário)
// Chart.ChartData.Series[0].PlotOnSecondAxis = verdadeiro;

// Definir a cor da parede posterior do gráfico
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Configurando a cor do piso do gráfico
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Configurando a cor da área de plotagem
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Salve a apresentação
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Essas personalizações adicionais são opcionais e podem ser aplicadas com base em seus requisitos específicos de design de gráfico.

## Conclusão

Neste guia passo a passo, exploramos a personalização avançada de gráficos usando Aspose.Slides para .NET. Você aprendeu como criar uma apresentação, adicionar um gráfico e ajustar sua aparência, incluindo linhas de grade, rótulos de eixos e outros elementos visuais. Com as poderosas opções de personalização fornecidas pelo Aspose.Slides, você pode criar gráficos que transmitem seus dados de maneira eficaz e envolvem seu público.

 Se você tiver alguma dúvida ou encontrar algum desafio ao trabalhar com Aspose.Slides for .NET, sinta-se à vontade para explorar a documentação[aqui](https://reference.aspose.com/slides/net/) ou procure ajuda no Aspose.Slides[fórum](https://forum.aspose.com/).

## Perguntas frequentes

### Quais versões do .NET são suportadas pelo Aspose.Slides for .NET?
Aspose.Slides for .NET oferece suporte a várias versões do .NET, incluindo .NET Framework e .NET Core. Você pode consultar a documentação para obter a lista completa de versões suportadas.

### Posso criar gráficos a partir de fontes de dados, como arquivos Excel, usando Aspose.Slides for .NET?
Sim, Aspose.Slides for .NET permite criar gráficos a partir de fontes de dados externas, como planilhas do Excel. Você pode explorar a documentação para obter exemplos detalhados.

### Como posso adicionar rótulos de dados personalizados à minha série de gráficos?
 Para adicionar rótulos de dados personalizados à sua série de gráficos, você pode acessar o`DataLabels` propriedade da série e personalize os rótulos conforme necessário. Consulte a documentação para amostras de código e exemplos.

### É possível exportar o gráfico para diferentes formatos de arquivo, como PDF ou formatos de imagem?
Sim, Aspose.Slides for .NET oferece opções para exportar sua apresentação com gráficos para vários formatos, incluindo PDF e formatos de imagem. Você pode usar a biblioteca para salvar seu trabalho no formato de saída desejado.

### Onde posso encontrar mais tutoriais e exemplos para Aspose.Slides for .NET?
 Você pode encontrar diversos tutoriais, exemplos de código e documentação no Aspose.Slides[local na rede Internet](https://reference.aspose.com/slides/net/).