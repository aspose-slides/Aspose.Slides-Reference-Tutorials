---
"date": "2025-04-15"
"description": "Aprenda a criar gráficos de rosca dinâmicos e visualmente atraentes em apresentações do PowerPoint usando a poderosa biblioteca Aspose.Slides para .NET."
"title": "Como criar um gráfico de rosca no PowerPoint usando Aspose.Slides para .NET"
"url": "/pt/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar um gráfico de rosca no PowerPoint usando Aspose.Slides para .NET
Criar gráficos visualmente envolventes é essencial para uma apresentação de dados eficaz. Gráficos de rosca são perfeitos para ilustrar partes de um todo, tornando-os ideais para visualização de dados com base em porcentagens. Este tutorial guiará você na criação de um gráfico de rosca dinâmico no PowerPoint usando a poderosa biblioteca Aspose.Slides para .NET.

## Introdução
Apresentações frequentemente exigem representações visuais de conjuntos de dados complexos, enquanto gráficos de barras ou linhas tradicionais podem ser insuficientes. O gráfico de rosca surge como uma ferramenta versátil para comunicar dados percentuais com eficácia, estilo e clareza. Neste tutorial, exploraremos como o Aspose.Slides para .NET simplifica o processo de criação desses gráficos diretamente no PowerPoint.

**O que você aprenderá:**
- Configurando o Aspose.Slides para .NET
- Instruções passo a passo para criar um gráfico de rosca
- Adicionando séries e categorias ao seu gráfico
- Configurando rótulos de dados para maior clareza
- Salvando a apresentação final

Vamos ver como você pode aproveitar o Aspose.Slides for .NET para aprimorar suas apresentações com gráficos de rosca personalizados.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte em mãos:
- **Biblioteca Aspose.Slides para .NET**: Disponível via NuGet ou download direto.
- **Ambiente de Desenvolvimento**O Visual Studio é recomendado para projetos .NET.
- Conhecimento básico de C# e familiaridade com a estrutura do PowerPoint.

## Configurando o Aspose.Slides para .NET
Para começar a criar gráficos, primeiro você precisa configurar a biblioteca Aspose.Slides no seu projeto. Veja aqui algumas maneiras de instalá-la:

**Usando o .NET CLI:**

```bash
dotnet add package Aspose.Slides
```

**Usando o Console do Gerenciador de Pacotes:**

```powershell
Install-Package Aspose.Slides
```

**Por meio da interface do usuário do Gerenciador de Pacotes NuGet:**
Procure por "Aspose.Slides" e instale a versão mais recente.

Após a instalação, você pode começar a configurar seu projeto. Se você é novo no Aspose.Slides, considere obter uma licença temporária ou um teste gratuito para explorar todos os seus recursos sem limitações.

### Inicialize seu projeto
Veja como você pode inicializar o Aspose.Slides em seu aplicativo:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Crie uma instância da classe Presentation
        Presentation presentation = new Presentation();
        
        // Seu código para manipular a apresentação vai aqui
        
        // Salvar a apresentação
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Guia de Implementação
### Criando um gráfico de rosca
#### Visão geral
Primeiro, criaremos um gráfico de rosca vazio em um slide do PowerPoint. Isso servirá como base para adicionar dados e personalizar sua aparência.

**Etapa 1: adicione um gráfico de rosca**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Adicione um gráfico de rosca ao primeiro slide na posição (10, 10) com tamanho (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Limpar séries e categorias existentes
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Desabilite a legenda para uma aparência mais limpa
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explicação:**
- **adicionar gráfico**: Insere um novo gráfico de rosca no slide.
- **obterChartDataWorkbook**: Fornece acesso às células de dados no gráfico para manipulação.

### Adicionando Séries e Categorias
#### Visão geral
Em seguida, preencheremos seu gráfico com dados significativos adicionando séries e categorias.

**Etapa 2: Adicionar séries de dados**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Adicionar série
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Personalizando o furo do donut e o ângulo inicial
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Adicionar categorias
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Formatando o preenchimento e a linha do ponto de dados
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explicação:**
- **adicionar**: Insere novas séries e categorias no gráfico.
- **definirDoughnutHoleSize**Configura o tamanho do furo do donut, melhorando seu apelo visual.

### Configurando rótulos de dados
#### Visão geral
Os rótulos de dados fornecem contexto aos dados do seu gráfico. Vamos melhorar a legibilidade personalizando-os.

**Etapa 3: personalizar rótulos de dados**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Personalizando rótulos de dados
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explicação:**
- **Rótulo de dados IDataLabel**: Personaliza os rótulos de dados para maior clareza e apresentação.
- **setCenterText**, **mostrarPorcentagem**: Melhore a legibilidade dos rótulos centralizando o texto e mostrando porcentagens.

## Conclusão
Seguindo este guia, você aprendeu a criar um gráfico de rosca dinâmico no PowerPoint usando o Aspose.Slides para .NET. Esta poderosa biblioteca permite ampla personalização, permitindo que você adapte seus gráficos precisamente às necessidades da sua apresentação.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}