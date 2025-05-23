---
"description": "Aprenda a aprimorar seus gráficos do PowerPoint usando o Aspose.Slides para .NET. Personalize marcadores de pontos de dados com imagens. Crie apresentações envolventes."
"linktitle": "Opções de marcadores de gráfico no ponto de dados"
"second_title": "API de processamento de PowerPoint Aspose.Slides .NET"
"title": "Usando opções de marcadores de gráfico em pontos de dados no Aspose.Slides .NET"
"url": "/pt/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Usando opções de marcadores de gráfico em pontos de dados no Aspose.Slides .NET


Ao trabalhar com apresentações e visualização de dados, o Aspose.Slides para .NET oferece uma ampla gama de recursos poderosos para criar, personalizar e manipular gráficos. Neste tutorial, exploraremos como usar opções de marcadores de gráfico em pontos de dados para aprimorar suas apresentações de gráficos. Este guia passo a passo guiará você pelo processo, desde os pré-requisitos e a importação de namespaces até a divisão de cada exemplo em várias etapas.

## Pré-requisitos

Antes de começarmos a usar as opções de marcadores de gráfico em pontos de dados, certifique-se de ter os seguintes pré-requisitos em vigor:

- Aspose.Slides para .NET: Certifique-se de ter o Aspose.Slides para .NET instalado. Você pode baixá-lo do site [site](https://releases.aspose.com/slides/net/).

- Apresentação de exemplo: para este tutorial, usaremos uma apresentação de exemplo chamada "Test.pptx". Você deve ter essa apresentação no seu diretório de documentos.

Agora, vamos começar importando os namespaces necessários.

## Importar namespaces

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Importamos os namespaces necessários e inicializamos nossa apresentação. Agora, vamos usar as opções de marcadores de gráfico em pontos de dados.

## Etapa 1: Criando o gráfico padrão

```csharp

// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Criando o gráfico padrão
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Criamos um gráfico padrão do tipo "LineWithMarkers" no slide em um local e tamanho especificados.

## Etapa 2: Obtendo o índice da planilha de dados do gráfico padrão

```csharp
// Obtendo o índice da planilha de dados do gráfico padrão
int defaultWorksheetIndex = 0;
```

Aqui, obtemos o índice da planilha de dados do gráfico padrão.

## Etapa 3: Obtendo a planilha de dados do gráfico

```csharp
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Buscamos a pasta de trabalho de dados do gráfico para trabalhar com dados do gráfico.

## Etapa 4: Modificando a série de gráficos

```csharp
// Excluir série de demonstração
chart.ChartData.Series.Clear();

// Adicionar nova série
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Nesta etapa, removemos qualquer série de demonstração existente e adicionamos uma nova série chamada "Série 1" ao gráfico.

## Etapa 5: Definindo o preenchimento da imagem para pontos de dados

```csharp
// Defina a imagem para os marcadores
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Pegue a primeira série de gráficos
IChartSeries series = chart.ChartData.Series[0];

// Adicionar novos pontos de dados com preenchimento de imagem
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Definimos marcadores de imagem para pontos de dados, permitindo que você personalize como cada ponto de dados aparece no gráfico.

## Etapa 6: Alterando o tamanho do marcador da série do gráfico

```csharp
// Alterando o tamanho do marcador da série do gráfico
series.Marker.Size = 15;
```

Aqui, ajustamos o tamanho do marcador da série do gráfico para torná-lo visualmente atraente.

## Etapa 7: Salvando a apresentação

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Por fim, salvamos a apresentação com as novas configurações do gráfico.

## Conclusão

O Aspose.Slides para .NET permite que você crie apresentações gráficas impressionantes com diversas opções de personalização. Neste tutorial, focamos no uso de opções de marcadores de gráfico em pontos de dados para aprimorar a representação visual dos seus dados. Com o Aspose.Slides para .NET, você pode levar suas apresentações a um novo patamar, tornando-as mais envolventes e informativas.

Se você tiver alguma dúvida ou precisar de ajuda com o Aspose.Slides para .NET, sinta-se à vontade para visitar o [Documentação do Aspose.Slides](https://reference.aspose.com/slides/net/) ou entre em contato com o [Comunidade Aspose](https://forum.aspose.com/) para suporte.

## Perguntas Frequentes (FAQs)

### Posso usar imagens personalizadas como marcadores para pontos de dados no Aspose.Slides para .NET?
Sim, você pode usar imagens personalizadas como marcadores para pontos de dados no Aspose.Slides para .NET, conforme demonstrado neste tutorial.

### Como posso alterar o tipo de gráfico no Aspose.Slides para .NET?
Você pode alterar o tipo de gráfico especificando um diferente `ChartType` ao criar o gráfico, como "Barra", "Pizza" ou "Área".

### O Aspose.Slides para .NET é compatível com as versões mais recentes do PowerPoint?
O Aspose.Slides para .NET foi projetado para funcionar com vários formatos do PowerPoint e é atualizado regularmente para manter a compatibilidade com as versões mais recentes do PowerPoint.

### Onde posso encontrar mais tutoriais e recursos para o Aspose.Slides para .NET?
Você pode explorar tutoriais e recursos adicionais no [Documentação do Aspose.Slides](https://reference.aspose.com/slides/net/).

### Existe uma versão de teste do Aspose.Slides para .NET disponível?
Sim, você pode experimentar o Aspose.Slides para .NET baixando uma versão de teste gratuita em [aqui](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}