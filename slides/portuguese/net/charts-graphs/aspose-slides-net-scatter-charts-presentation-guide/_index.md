---
"date": "2025-04-15"
"description": "Aprenda a aprimorar suas apresentações com gráficos de dispersão usando o Aspose.Slides para .NET. Siga este guia completo para criar e personalizar gráficos de forma eficaz."
"title": "Adicione gráficos de dispersão a apresentações usando Aspose.Slides .NET - Um guia passo a passo"
"url": "/pt/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Adicionar gráficos de dispersão a apresentações usando Aspose.Slides .NET: um guia passo a passo

## Introdução
Deseja aprimorar suas apresentações integrando gráficos de dispersão sem esforço? Com o poder do Aspose.Slides para .NET, criar e personalizar gráficos se torna muito fácil. Este tutorial guiará você na adição de gráficos de dispersão aos seus slides usando o Aspose.Slides para .NET. Ao dominar essas técnicas, você apresentará dados com mais eficácia e criará apresentações visualmente atraentes.

**O que você aprenderá:**
- Configurando o Aspose.Slides para .NET em seu projeto
- Criando uma nova apresentação e acessando seu primeiro slide
- Adicionar gráficos de dispersão com linhas suaves aos slides
- Limpando séries existentes e adicionando novas aos gráficos
- Modificando pontos de dados e estilos de marcadores para visualização aprimorada
- Salvando a apresentação em um diretório especificado

Vamos começar revisando os pré-requisitos.

## Pré-requisitos
Antes de implementar o Aspose.Slides para .NET, certifique-se de ter o seguinte:
- **Biblioteca Aspose.Slides para .NET**: Versão 23.7 ou posterior.
- **Ambiente de Desenvolvimento**: Visual Studio 2019 ou mais recente com .NET Framework 4.6.1+ ou .NET Core/5+.
- **Conhecimento básico de C#**: Familiaridade com programação orientada a objetos em C#.

## Configurando o Aspose.Slides para .NET
Para começar a usar o Aspose.Slides, você precisa instalar a biblioteca no seu projeto. Veja como:

**Usando o .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Usando o Console do Gerenciador de Pacotes:**
```powershell
Install-Package Aspose.Slides
```

**Interface do Gerenciador de Pacotes NuGet:**
- Procure por "Aspose.Slides" e instale a versão mais recente.

### Aquisição de Licença
Você pode começar com um teste gratuito ou solicitar uma licença temporária para explorar todos os recursos. Para comprar, siga estes passos:
1. Visita [Compre Aspose.Slides](https://purchase.aspose.com/buy) para comprar uma licença completa.
2. Para uma licença temporária, visite [Página de Licença Temporária](https://purchase.aspose.com/temporary-license/).

Depois de obter seu arquivo de licença, adicione-o ao seu projeto usando:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Guia de Implementação
Dividiremos a implementação em seções lógicas com base nos recursos.

### Criar apresentação e adicionar slide
Esta seção demonstra como criar uma apresentação e acessar seu primeiro slide.

#### Visão geral
Comece criando uma instância do `Presentation` class, que representa seu arquivo do PowerPoint. O acesso aos slides é simples usando este modelo de objeto.

#### Etapas de implementação
**Etapa 1: Inicializar a apresentação**
```csharp
using Aspose.Slides;

// Criar uma nova apresentação
t Presentation pres = new Presentation();
```
Este código inicializa um novo documento de apresentação.

**Etapa 2: Acesse o primeiro slide**
```csharp
// Acesse o primeiro slide da apresentação
ISlide slide = pres.Slides[0];
```
Aqui, `pres.Slides[0]` acessa o primeiro slide. 

### Adicionar gráfico de dispersão ao slide
Agora vamos adicionar um gráfico de dispersão à sua apresentação.

#### Visão geral
Adicionar gráficos pode ajudar a representar dados visualmente em apresentações. O Aspose.Slides simplifica a incorporação de vários tipos de gráficos, incluindo gráficos de dispersão.

#### Etapas de implementação
**Etapa 1: Criar e adicionar gráfico de dispersão**
```csharp
using Aspose.Slides.Charts;

// Crie e adicione um gráfico de dispersão padrão com linhas suaves
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Este snippet adiciona um gráfico de dispersão na posição e tamanho especificados.

### Limpar e adicionar séries aos dados do gráfico
#### Visão geral
Talvez seja necessário personalizar seu gráfico limpando séries existentes e adicionando novas. Esta seção aborda essa funcionalidade.

#### Etapas de implementação
**Etapa 1: Acesse a pasta de trabalho de dados do gráfico**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Limpar qualquer série pré-existente
chart.ChartData.Series.Clear();
```
Este código limpa os dados existentes para começar do zero com novas séries.

**Etapa 2: Adicionar nova série**
```csharp
// Adicione uma nova série chamada "Série 1"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Adicione outra série chamada "Série 2"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Essas etapas adicionam duas novas séries ao gráfico.

### Modificar os pontos de dados da primeira série e o estilo do marcador
#### Visão geral
Personalize pontos de dados e estilos de marcadores para melhor visualização dos seus gráficos de dispersão.

#### Etapas de implementação
**Etapa 1: acessar e adicionar pontos de dados**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Adicione os pontos de dados (1, 3) e (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Etapa 2: Modifique o estilo do marcador**
```csharp
// Alterar o tipo de série e modificar o estilo do marcador
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Modificar pontos de dados da segunda série e estilo do marcador
#### Visão geral
Da mesma forma, personalize a segunda série para atender às suas necessidades de apresentação.

#### Etapas de implementação
**Etapa 1: acessar e adicionar vários pontos de dados**
```csharp
// Acesse a segunda série de gráficos
series = chart.ChartData.Series[1];

// Adicionar vários pontos de dados
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Etapa 2: Modifique o estilo do marcador**
```csharp
// Alterar o tamanho do marcador e o símbolo para a segunda série
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Salvar apresentação
Por fim, salve sua apresentação em um diretório especificado.

#### Etapas de implementação
**Etapa 1: definir diretório**
Certifique-se de que o diretório de saída exista. Caso contrário, crie-o:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Salvar a apresentação
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Este código salva seu arquivo de apresentação em um local especificado.

## Conclusão
Agora você adicionou gráficos de dispersão às suas apresentações com sucesso usando o Aspose.Slides para .NET. Continue explorando os recursos e personalizações adicionais disponíveis na biblioteca para aprimorar suas habilidades de visualização de dados.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}