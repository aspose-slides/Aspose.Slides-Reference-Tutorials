---
"date": "2025-04-15"
"description": "Aprenda a criar gráficos de rosca dinâmicos usando o Aspose.Slides para .NET. Siga este guia para obter instruções passo a passo, incluindo configuração e recursos avançados."
"title": "Guia passo a passo&#58; como criar um gráfico de rosca com Aspose.Slides .NET | Gráficos e tabelas"
"url": "/pt/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Guia passo a passo: Crie um gráfico de rosca com Aspose.Slides .NET

## Introdução

Imagine que você precisa apresentar os resultados da análise de dados para sua equipe ou clientes e precisa de uma maneira envolvente de visualizar as informações. Eis o gráfico de rosca: uma ferramenta versátil que transforma números brutos em insights de fácil assimilação. Com o Aspose.Slides para .NET, criar um gráfico de rosca personalizado nos slides da sua apresentação é simples e eficiente. Este guia o guiará pelo uso do Aspose.Slides para criar um gráfico de rosca visualmente atraente, completo com configurações de série personalizadas.

**O que você aprenderá:**
- Configurando seu ambiente de desenvolvimento com Aspose.Slides para .NET
- Criação e personalização de gráficos de rosca em apresentações
- Implementando recursos avançados, como nomes de categorias e linhas de liderança
- Otimizando o desempenho para grandes conjuntos de dados

Vamos analisar os pré-requisitos necessários para começar.

## Pré-requisitos

Antes de implementar este recurso, certifique-se de que seu ambiente de desenvolvimento esteja configurado corretamente. Este tutorial pressupõe conhecimento básico de programação .NET e familiaridade com o Visual Studio ou um IDE similar.

### Bibliotecas e versões necessárias
- **Aspose.Slides para .NET**: Garanta a compatibilidade com a versão mais recente verificando sua [documentação oficial](https://reference.aspose.com/slides/net/).

### Requisitos de configuração do ambiente
- Um ambiente .NET funcional.
- Acesso a um editor de código, como o Visual Studio.

### Pré-requisitos de conhecimento
- Noções básicas de C# e .NET framework.
- Familiaridade com conceitos de software de apresentação (opcional, mas útil).

## Configurando o Aspose.Slides para .NET

Para começar a usar o Aspose.Slides no seu projeto, você precisa instalá-lo via NuGet. Aqui estão os métodos disponíveis:

**Usando o .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Usando o Gerenciador de Pacotes:**
```powershell
Install-Package Aspose.Slides
```

**Interface do Gerenciador de Pacotes NuGet:**
Procure por "Aspose.Slides" e instale a versão mais recente.

### Etapas de aquisição de licença

1. **Teste grátis**: Comece com um [teste gratuito](https://releases.aspose.com/slides/net/) para explorar funcionalidades básicas.
2. **Licença Temporária**: Obtenha uma licença temporária se precisar de acesso a todos os recursos para fins de avaliação visitando [aqui](https://purchase.aspose.com/temporary-license/).
3. **Comprar**:Para uso comercial, adquira uma licença do [Site Aspose](https://purchase.aspose.com/buy).

Uma vez instalado e licenciado, inicialize o Aspose.Slides no seu projeto:
```csharp
using Aspose.Slides;

// Inicializar Aspose.Slides para .NET
var presentation = new Presentation();
```

## Guia de Implementação

### Criando uma nova apresentação e adicionando um gráfico de rosca

#### Visão geral
Começaremos criando uma nova apresentação e adicionando um gráfico de rosca ao primeiro slide. Esta seção aborda como carregar uma apresentação existente, acessar slides e inserir gráficos.

**Etapa 1: Carregar ou criar uma apresentação**
Primeiro, especifique seu diretório de documentos e carregue uma apresentação existente:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Se você não tiver um arquivo existente, crie um novo com `new Presentation()`.

**Etapa 2: Acesse o primeiro slide**
Acesse o primeiro slide onde adicionaremos nosso gráfico:
```csharp
ISlide slide = pres.Slides[0];
```

**Etapa 3: adicione um gráfico de rosca**
Adicione um gráfico de rosca nas coordenadas e dimensões especificadas:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configurando a pasta de trabalho de dados

#### Visão geral
Esta seção explica como configurar a pasta de trabalho de dados associada ao seu gráfico de rosca.

**Etapa 4: acessar e limpar dados existentes**
Acesse a pasta de trabalho de dados do gráfico. Em seguida, limpe todas as séries ou categorias existentes:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Etapa 5: Desabilitar Legenda e Adicionar Série**
Desative a legenda para manter o gráfico limpo e adicione até 15 séries com configurações personalizadas:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Adicionando categorias e pontos de dados

#### Visão geral
Agora, vamos preencher o gráfico com categorias e pontos de dados para cada série.

**Etapa 6: Adicionar categorias**
Faça um loop para adicionar 15 categorias:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Etapa 7: preencher pontos de dados**
Adicione pontos de dados para cada série dentro da categoria atual:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Personalizar a aparência
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Configurar formato de etiqueta para a última série
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Configurar exibição de rótulos
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Salvando a apresentação

**Etapa 8: Salve o arquivo**
Por fim, salve sua apresentação em um diretório especificado:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}