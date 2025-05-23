---
"date": "2025-04-15"
"description": "Aprenda a criar e personalizar gráficos usando o Aspose.Slides para .NET, incluindo a exibição de porcentagens como rótulos de dados. Siga este guia passo a passo."
"title": "Como criar e personalizar gráficos com Aspose.Slides .NET | Exibir porcentagens como rótulos"
"url": "/pt/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar e personalizar gráficos com Aspose.Slides .NET: Exibir porcentagens como rótulos

## Introdução

Apresentar dados de forma eficaz é crucial em muitas áreas, e os gráficos desempenham um papel vital, transformando informações complexas em elementos visuais claros. Criar o gráfico perfeito envolve tarefas de personalização, como exibir porcentagens em rótulos — uma tarefa facilitada com o Aspose.Slides para .NET. Esta biblioteca simplifica o processo de criação e modificação de gráficos em apresentações do PowerPoint.

Neste tutorial, você aprenderá a usar o Aspose.Slides para .NET para criar um gráfico de colunas empilhadas do zero e personalizá-lo exibindo valores percentuais como rótulos de dados. Seguindo esses passos, você aprimorará seus slides com representações de dados precisas e visualmente atraentes.

**O que você aprenderá:**
- Inicializando Aspose.Slides para .NET
- Criando um gráfico de colunas empilhadas
- Calculando e exibindo porcentagens em rótulos de dados
- Otimizando as práticas recomendadas de desempenho de gráficos

Antes de começarmos a implementação, vamos garantir que você tenha tudo pronto para começar.

## Pré-requisitos

Para seguir este tutorial com eficiência, certifique-se de ter:
- **SDK do .NET Core** instalado na sua máquina.
- Noções básicas de desenvolvimento de aplicativos C# e .NET.
- Visual Studio ou um IDE similar para escrever e executar código C#.

Você precisará do Aspose.Slides for .NET para criar gráficos, então certifique-se de que ele esteja configurado conforme descrito abaixo.

## Configurando o Aspose.Slides para .NET

Aspose.Slides para .NET é uma biblioteca poderosa que permite trabalhar com apresentações do PowerPoint programaticamente. Veja como adicioná-la ao seu projeto:

### Instalação

**CLI .NET:**
```bash
dotnet add package Aspose.Slides
```

**Console do gerenciador de pacotes:**
```powershell
Install-Package Aspose.Slides
```

**Interface do Gerenciador de Pacotes NuGet:** 
- Abra o Gerenciador de Pacotes NuGet e procure por "Aspose.Slides". Instale a versão mais recente.

### Aquisição de Licença

Para aproveitar ao máximo o Aspose.Slides, comece com um teste gratuito. Para uso prolongado, considere adquirir uma licença temporária ou comprar uma de [Aspose](https://purchase.aspose.com/buy). Siga as diretrizes para configurar sua licença no ambiente do seu projeto.

### Inicialização básica

Uma vez instalado, inicialize o `Presentation` aula para começar a criar slides:
```csharp
using Aspose.Slides;

// Inicializar instância da classe Presentation
tPresentation presentation = new Presentation();
```

Agora, vamos implementar nosso recurso de criação e personalização de gráficos usando o Aspose.Slides para .NET.

## Guia de Implementação

### Criar um gráfico de colunas empilhadas

Nosso objetivo é criar um gráfico de colunas empilhadas e personalizá-lo exibindo porcentagens como rótulos de dados. Veja como:

#### Inicializar a apresentação

Comece criando uma instância de `Presentation`:
```csharp
using Aspose.Slides;

// Inicializar instância da classe Presentation
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Adicionar um gráfico ao slide

Adicione um gráfico de colunas empilhadas ao seu primeiro slide nas coordenadas e dimensões especificadas:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Esta linha cria uma `StackedColumn` gráfico na posição (20, 20) com largura e altura de 400.

#### Calcular valores totais para cálculo de porcentagem

Para exibir porcentagens, calcule o valor total de cada categoria em todas as séries:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Some os valores de todas as séries para cada categoria
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Personalize rótulos de dados para mostrar valores percentuais

Em seguida, itere por cada série e personalize os rótulos de dados:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Calcular porcentagem
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Texto limpo para evitar sobreposições
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Configurar formato de rótulo para ocultar rótulos de dados padrão
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Esta seção calcula a porcentagem para cada ponto de dados e a define como um rótulo personalizado, garantindo que não haja sobreposição com rótulos padrão.

#### Salvar a apresentação

Por fim, salve sua apresentação para visualizar o resultado:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Aplicações práticas

Exibir porcentagens em gráficos pode ser particularmente útil em cenários como:
1. **Relatórios financeiros:** Mostrar distribuições de portfólio ou retornos de investimento como porcentagens.
2. **Análise de vendas:** Represente dados de participação de mercado por porcentagem para destacar o desempenho em todas as regiões.
3. **Resultados da pesquisa:** Exiba as respostas da pesquisa como porcentagens para melhor comparação visual.
4. **Gerenciamento de projetos:** Use gráficos de pizza com porcentagens para ilustrar a alocação de recursos.
5. **Educação:** Explique conceitos estatísticos usando recursos visuais claros baseados em porcentagens.

A integração desses gráficos personalizados em sistemas como CRM ou ERP pode aprimorar painéis e relatórios, auxiliando nos processos de tomada de decisão.

## Considerações de desempenho

Ao trabalhar com Aspose.Slides para .NET, especialmente com grandes conjuntos de dados:
- **Gerenciamento de memória:** Descarte os objetos de apresentação corretamente para liberar memória. Use `using` declarações quando aplicável.
- **Tratamento eficiente de dados:** Execute cálculos fora dos loops sempre que possível para reduzir a sobrecarga computacional.
- **Balanceamento de carga:** Para aplicativos da Web, garanta que os recursos do servidor sejam provisionados adequadamente para solicitações simultâneas de geração de gráficos.

## Conclusão

Este tutorial abordou a criação e personalização de gráficos usando o Aspose.Slides para .NET, exibindo valores percentuais como rótulos. Dominar essas técnicas permite aprimorar suas apresentações com representações de dados detalhadas e visualmente atraentes.

Como próximo passo, explore outros tipos de gráficos e opções de personalização disponíveis no Aspose.Slides. Experimente diferentes conjuntos de dados para transformá-los em visuais poderosos que comuniquem insights com clareza.

## Seção de perguntas frequentes

**T1: Como lidar com grandes conjuntos de dados ao criar gráficos com o Aspose.Slides para .NET?**
R1: Para grandes conjuntos de dados, otimize os cálculos e use técnicas eficientes de gerenciamento de memória. Divida as tarefas de processamento para evitar sobrecarga de memória.

**P2: Posso usar o Aspose.Slides para .NET em um aplicativo web?**
R2: Sim, pode ser integrado a aplicações ASP.NET. Garanta a alocação adequada de recursos do servidor para um desempenho ideal.

**P3: É possível exportar gráficos criados com o Aspose.Slides para outros formatos?**
R3: Com certeza! Você pode exportar apresentações contendo seus gráficos personalizados para vários formatos, como PDF e arquivos de imagem, usando os recursos da biblioteca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}