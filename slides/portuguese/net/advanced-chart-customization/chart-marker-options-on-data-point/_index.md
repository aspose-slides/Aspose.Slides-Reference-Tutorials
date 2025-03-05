---
title: Usando opções de marcador de gráfico em pontos de dados em Aspose.Slides .NET
linktitle: Opções de marcador de gráfico em ponto de dados
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como aprimorar seus gráficos do PowerPoint usando Aspose.Slides for .NET. Personalize marcadores de pontos de dados com imagens. Crie apresentações envolventes.
type: docs
weight: 11
url: /pt/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

Ao trabalhar com apresentações e visualização de dados, Aspose.Slides for .NET oferece uma ampla gama de recursos poderosos para criar, personalizar e manipular gráficos. Neste tutorial, exploraremos como usar opções de marcadores de gráfico em pontos de dados para aprimorar suas apresentações de gráficos. Este guia passo a passo orientará você durante o processo, começando pelos pré-requisitos e importando namespaces, até dividir cada exemplo em várias etapas.

## Pré-requisitos

Antes de começarmos a usar opções de marcadores de gráfico em pontos de dados, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Aspose.Slides for .NET: Certifique-se de ter o Aspose.Slides for .NET instalado. Você pode baixá-lo no[local na rede Internet](https://releases.aspose.com/slides/net/).

- Exemplo de apresentação: Para este tutorial, usaremos um exemplo de apresentação chamado "Test.pptx". Você deve ter esta apresentação em seu diretório de documentos.

Agora, vamos começar importando os namespaces necessários.

## Importar namespaces

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Importamos os namespaces necessários e inicializamos nossa apresentação. Agora, vamos usar as opções de marcador de gráfico em pontos de dados.

## Etapa 1: Criando o gráfico padrão

```csharp

// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Criando o gráfico padrão
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

Buscamos a pasta de trabalho de dados do gráfico para trabalhar com os dados do gráfico.

## Etapa 4: modificando a série de gráficos

```csharp
// Excluir série de demonstração
chart.ChartData.Series.Clear();

// Adicionar nova série
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Nesta etapa, removemos qualquer série de demonstração existente e adicionamos uma nova série chamada “Série 1” ao gráfico.

## Etapa 5: configuração do preenchimento de imagem para pontos de dados

```csharp
// Defina a imagem para os marcadores
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Veja a primeira série de gráficos
IChartSeries series = chart.ChartData.Series[0];

// Adicione novos pontos de dados com preenchimento de imagem
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

Definimos marcadores de imagem para pontos de dados, permitindo personalizar como cada ponto de dados aparece no gráfico.

## Etapa 6: alterar o tamanho do marcador da série do gráfico

```csharp
// Alterando o tamanho do marcador da série do gráfico
series.Marker.Size = 15;
```

Aqui, ajustamos o tamanho do marcador da série do gráfico para torná-lo visualmente atraente.

## Etapa 7: salvando a apresentação

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Por fim, salvamos a apresentação com as novas configurações do gráfico.

## Conclusão

Aspose.Slides for .NET permite que você crie apresentações de gráficos impressionantes com várias opções de personalização. Neste tutorial, nos concentramos no uso de opções de marcadores de gráfico em pontos de dados para aprimorar a representação visual de seus dados. Com Aspose.Slides for .NET, você pode levar suas apresentações para o próximo nível, tornando-as mais envolventes e informativas.

Se você tiver alguma dúvida ou precisar de ajuda com Aspose.Slides for .NET, sinta-se à vontade para visitar o[Documentação do Aspose.Slides](https://reference.aspose.com/slides/net/) ou entre em contato com[Aspor comunidade](https://forum.aspose.com/) para suporte.

## Perguntas frequentes (FAQ)

### Posso usar imagens personalizadas como marcadores para pontos de dados no Aspose.Slides for .NET?
Sim, você pode usar imagens personalizadas como marcadores para pontos de dados no Aspose.Slides for .NET, conforme demonstrado neste tutorial.

### Como posso alterar o tipo de gráfico no Aspose.Slides for .NET?
 Você pode alterar o tipo de gráfico especificando um diferente`ChartType` ao criar o gráfico, como "Barra", "Pizza" ou "Área".

### O Aspose.Slides for .NET é compatível com as versões mais recentes do PowerPoint?
Aspose.Slides for .NET foi projetado para funcionar com vários formatos de PowerPoint e é atualizado regularmente para manter a compatibilidade com as versões mais recentes do PowerPoint.

### Onde posso encontrar mais tutoriais e recursos para Aspose.Slides for .NET?
 Você pode explorar tutoriais e recursos adicionais no[Documentação do Aspose.Slides](https://reference.aspose.com/slides/net/).

### Existe uma versão de teste do Aspose.Slides for .NET disponível?
 Sim, você pode experimentar o Aspose.Slides for .NET baixando uma versão de teste gratuita em[aqui](https://releases.aspose.com/).