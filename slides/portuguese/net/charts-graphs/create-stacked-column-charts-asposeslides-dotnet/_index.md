---
"date": "2025-04-15"
"description": "Aprenda a criar gráficos de colunas empilhadas com base em porcentagem visualmente atraentes usando o Aspose.Slides para .NET. Siga este guia passo a passo para uma visualização clara dos dados."
"title": "Como criar gráficos de colunas empilhadas com base em porcentagem no .NET usando Aspose.Slides"
"url": "/pt/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar um gráfico de colunas empilhadas baseado em porcentagem usando Aspose.Slides para .NET

## Introdução

No âmbito da visualização de dados, apresentar informações de forma clara e eficaz é crucial para uma tomada de decisão impactante. Para exibir conjuntos de dados complexos de forma intuitiva, gráficos de colunas empilhadas com base em porcentagem são ideais. Este guia o orientará na criação desses gráficos usando o Aspose.Slides para .NET, uma biblioteca robusta projetada para manipular arquivos de apresentação.

Seguindo este tutorial, você aprenderá:
- Configurando dados do gráfico e configurando formatos numéricos.
- Adicionando séries e personalizando sua aparência.
- Formatação de rótulos para melhorar a legibilidade.

Pronto para começar? Vamos começar com os pré-requisitos necessários!

## Pré-requisitos

Antes de criar seus gráficos de colunas empilhadas com base em porcentagem, certifique-se de que seu ambiente esteja configurado corretamente. Você precisará de:

### Bibliotecas, versões e dependências necessárias
- **Aspose.Slides para .NET**: Certifique-se de que esta biblioteca esteja instalada.

### Requisitos de configuração do ambiente
- Um ambiente de desenvolvimento com o .NET SDK instalado.
- Visual Studio ou qualquer IDE compatível para executar código C#.

### Pré-requisitos de conhecimento
- Noções básicas de programação em C#.
- Familiaridade com configuração de projetos .NET e gerenciamento de pacotes.

## Configurando o Aspose.Slides para .NET

Para começar a criar gráficos com o Aspose.Slides, primeiro instale a biblioteca usando um destes métodos:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Gerenciador de Pacotes**
```powershell
Install-Package Aspose.Slides
```

**Interface do usuário do gerenciador de pacotes NuGet**
- Procure por "Aspose.Slides" e instale a versão mais recente.

### Etapas de aquisição de licença

Comece com um teste gratuito baixando uma licença temporária em [Site da Aspose](https://purchase.aspose.com/temporary-license/). Para uso contínuo, considere comprar uma licença completa. 

Uma vez configurado, inicie o Aspose.Slides no seu projeto:
```csharp
using Aspose.Slides;
```

## Guia de Implementação

Com o ambiente pronto, vamos dividir a criação de um gráfico de colunas empilhadas baseado em porcentagem em etapas.

### Criando e Configurando o Gráfico

#### Visão geral
Crie uma instância do `Presentation` classe, essencial para trabalhar com slides. Em seguida, adicione e configure um gráfico de colunas empilhadas no seu slide.

#### Adicionando um gráfico de colunas empilhadas
```csharp
// Crie uma instância da classe Presentation
document = new Presentation();

// Obter referência ao primeiro slide
slide = document.Slides[0];

// Adicionar gráfico PercentsStackedColumn na posição (20, 20) com tamanho (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Configurando o formato do número
Certifique-se de que seus dados sejam exibidos como porcentagens:
```csharp
// Configurar formato numérico para o eixo vertical
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Definir formato numérico para porcentagem
```

#### Adicionando séries de dados e pontos
Limpar dados de séries existentes e adicionar novos:
```csharp
// Limpar todos os dados de série existentes
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Pasta de trabalho de dados do gráfico de acesso
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Adicionar uma nova série de dados "Vermelhos"
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Defina a cor de preenchimento da série como Vermelho
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Configurar propriedades de formato de rótulo para a série "Reds"
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Definir formato de porcentagem
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Adicione outra série "Blues"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Defina a cor de preenchimento da série como Azul
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Definir formato de porcentagem
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Salvando a apresentação
Salve sua apresentação em um arquivo:
```csharp
// Salvar a apresentação no formato PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Dicas para solução de problemas
- Certifique-se de que todos os namespaces sejam importados corretamente.
- Verifique se há erros de digitação em nomes de propriedades e chamadas de métodos.
- Verifique se os caminhos para salvar arquivos existem e se têm as permissões corretas.

## Aplicações práticas

Aqui estão alguns cenários em que gráficos de colunas empilhadas baseados em porcentagem podem ser valiosos:
1. **Análise de Vendas**: Visualize o desempenho do produto em diferentes regiões como uma proporção das vendas totais.
2. **Alocação Orçamentária**: Mostre como os departamentos alocam seu orçamento em relação aos gastos gerais da empresa.
3. **Pesquisa de mercado**: Compare as preferências do consumidor por diversas categorias de produtos ao longo do tempo.
4. **Dados Educacionais**: Exibir distribuição das notas dos alunos em diferentes disciplinas.
5. **Estatísticas de saúde**: Representa dados demográficos de pacientes em diversas condições de saúde.

## Considerações de desempenho

Para um desempenho ideal, considere:
- Limitar o número de pontos de dados ao necessário.
- Pré-carregamento de dados para minimizar o processamento em tempo de execução.
- Usando práticas eficientes de gerenciamento de memória com Aspose.Slides para .NET.

## Conclusão

Parabéns! Você aprendeu a criar um gráfico de colunas empilhadas baseado em porcentagem usando o Aspose.Slides para .NET. Esta ferramenta aprimora apresentações, tornando dados complexos mais compreensíveis e visualmente atraentes.

Próximos passos? Explore outros tipos de gráficos disponíveis no Aspose.Slides ou integre essa funcionalidade em aplicativos maiores. Boa programação!

## Seção de perguntas frequentes

**P1: Posso usar o Aspose.Slides gratuitamente?**
R1: Sim, você pode começar com um teste gratuito para testar os recursos do Aspose.Slides.

**P2: Quais tipos de gráficos são suportados pelo Aspose.Slides para .NET?**
R2: Ele suporta vários gráficos, como pizza, barras, colunas, linhas e muito mais.

**T3: Como começar a usar o Aspose.Slides para .NET?**
R3: Instale a biblioteca usando o NuGet ou a CLI .NET conforme descrito acima. Siga nossa documentação para criar seu primeiro gráfico.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}