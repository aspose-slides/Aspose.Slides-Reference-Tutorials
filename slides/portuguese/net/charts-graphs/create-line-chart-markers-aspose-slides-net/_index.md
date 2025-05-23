---
"date": "2025-04-15"
"description": "Aprenda a criar gráficos de linhas com marcadores usando o Aspose.Slides para .NET. Este guia passo a passo aborda a configuração, a criação e a personalização do gráfico."
"title": "Como criar um gráfico de linhas com marcadores em C# usando Aspose.Slides para .NET"
"url": "/pt/net/charts-graphs/create-line-chart-markers-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar um gráfico de linhas com marcadores em C# usando Aspose.Slides para .NET

## Introdução
Criar gráficos de linhas visualmente atraentes e informativos é essencial para uma apresentação de dados eficaz em C#. **Aspose.Slides para .NET** simplifica o processo de adição de gráficos com aparência profissional, incluindo aqueles com marcadores. Este tutorial guiará você na criação de um gráfico de linhas com marcadores padrão usando o Aspose.Slides para .NET.

Neste tutorial, você aprenderá:
- Configurando seu ambiente para usar o Aspose.Slides para .NET.
- Criar e personalizar uma apresentação com um gráfico de linhas que inclui marcadores.
- Configurando propriedades do gráfico, como categorias, séries e pontos de dados.
- Salvando o arquivo de apresentação final.

Vamos começar revisando os pré-requisitos necessários antes de implementar nossa solução.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
- **Bibliotecas necessárias:** Aspose.Slides para .NET instalado em seu ambiente de desenvolvimento via NuGet.
- **Requisitos de configuração do ambiente:** Um ambiente de desenvolvimento C# funcional, como o Visual Studio e o .NET Framework instalado na sua máquina.
- **Pré-requisitos de conhecimento:** Conhecimento básico de programação em C# e familiaridade com a criação de apresentações programaticamente.

## Configurando o Aspose.Slides para .NET
### Informações de instalação
Para começar a usar o Aspose.Slides para .NET, adicione-o ao seu projeto por meio de um dos seguintes métodos:

**Usando o .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Por meio do Console do Gerenciador de Pacotes no Visual Studio:**
```powershell
Install-Package Aspose.Slides
```

**Interface do Gerenciador de Pacotes NuGet:**
- Abra sua solução no Visual Studio.
- Vá para "Gerenciar pacotes NuGet para solução..."
- Procure por "Aspose.Slides" e instale a versão mais recente.

### Aquisição de Licença
Antes de usar o Aspose.Slides, obtenha uma licença de teste ou compre:
1. **Teste gratuito:** Visita [Página de teste gratuito do Aspose](https://releases.aspose.com/slides/net/) para começar rapidamente.
2. **Licença temporária:** Para acesso estendido, visite o [Página de Licença Temporária](https://purchase.aspose.com/temporary-license/).
3. **Comprar:** Para usar o Aspose.Slides em produção, adquira uma licença em [Aspose Compra](https://purchase.aspose.com/buy).

### Inicialização básica
Depois de configurar seu projeto e obter as licenças necessárias, inicialize o Aspose.Slides da seguinte maneira:
```csharp
using Aspose.Slides;
// Crie uma instância da classe Presentation
Presentation pres = new Presentation();
```
Agora que configuramos nosso ambiente, vamos prosseguir para criar um gráfico de linhas com marcadores.

## Guia de Implementação
### Criando o gráfico de linhas com marcadores
Nesta seção, você aprenderá cada etapa necessária para criar e configurar um gráfico de linhas com marcadores padrão em sua apresentação usando o Aspose.Slides para .NET.

#### Etapa 1: Criar um objeto de apresentação
Comece criando uma instância do `Presentation` aula:
```csharp
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
```
Aqui, acessamos o primeiro slide de uma apresentação recém-criada.

#### Etapa 2: adicione um gráfico de linhas com marcadores
Em seguida, adicione um gráfico de linhas com marcadores ao seu slide:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
```
Este código adiciona um novo gráfico do tipo `LineWithMarkers` nas coordenadas `(10, 10)` com dimensões `400x400`.

#### Etapa 3: limpar séries e categorias existentes
Antes de adicionar dados, limpe todas as séries ou categorias existentes:
```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```
Isso garante que nosso gráfico comece do zero.

#### Etapa 4: Configurar a pasta de trabalho de dados do gráfico
Acesse o `ChartDataWorkbook` para gerenciar os dados do seu gráfico:
```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```
Este objeto é crucial para gerenciar células que contêm dados de séries e categorias.

#### Etapa 5: Adicionar séries e categorias
Adicione uma nova série ao gráfico e preencha-o com pontos de dados:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
IChartSeries series = chart.ChartData.Series[0];

// Definir categorias e pontos de dados correspondentes
chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "C1"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 1, 24));
chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "C2"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 1, 23));
chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "C3"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 1, -10));
chart.ChartData.Categories.Add(fact.GetCell(0, 4, 0, "C4"));

// Adicione um ponto de dados nulo para demonstrar o tratamento de valores ausentes
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 1, (double?)null));
```
Aqui, preenchemos o gráfico com categorias e dados de série correspondentes. Observe como um `null` o valor é tratado como uma demonstração.

#### Etapa 6: Adicionar outra série
Repita o processo para adicionar outra série:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 2, "Series 2"), chart.Type);
IChartSeries series2 = chart.ChartData.Series[1];

series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 2, 30));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 2, 10));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 2, 60));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 2, 40));
```

#### Etapa 7: Habilitar e configurar a legenda
Habilite a legenda do gráfico para melhorar a legibilidade:
```csharp
chart.HasLegend = true;
chart.Legend.Overlay = false;
```
Isso garante que a legenda fique visível e não sobreposta no gráfico.

#### Etapa 8: Salve a apresentação
Por fim, salve sua apresentação com o gráfico recém-adicionado:
```csharp
pres.Save("DefaultMarkersInChart.pptx");
}
```
### Dicas para solução de problemas
- **Erros de vinculação de dados:** Garanta que os pontos de dados correspondam corretamente às categorias.
- **Gráfico não exibido:** Verifique se `chart.HasLegend` e outras propriedades são definidas adequadamente.

## Aplicações práticas
1. **Relatórios de negócios:** Use gráficos de linhas com marcadores para monitorar o desempenho das vendas ao longo do tempo, mostrando tendências na receita mensal.
2. **Análise Financeira:** Visualize os movimentos dos preços das ações com marcadores padrão para destacar picos e vales.
3. **Pesquisa científica:** Apresentar resultados experimentais onde os pontos de dados precisam de demarcação clara para análise.

## Considerações de desempenho
- Otimize limitando o número de séries e categorias de dados ao lidar com grandes conjuntos de dados.
- Use técnicas de gerenciamento de memória, como descartar objetos prontamente no .NET, para reduzir o uso de recursos.

## Conclusão
Neste tutorial, você aprendeu a criar um gráfico de linhas com marcadores usando o Aspose.Slides para .NET. Seguindo esses passos, você pode aprimorar suas apresentações com gráficos detalhados e com aparência profissional. Considere explorar outros recursos do Aspose.Slides para enriquecer ainda mais suas apresentações de slides.

### Próximos passos
- Experimente diferentes tipos de gráficos disponíveis no Aspose.Slides.
- Personalize a aparência dos gráficos para melhor impacto visual.
- Explore documentação adicional no Aspose.Slides para funcionalidades mais avançadas.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}